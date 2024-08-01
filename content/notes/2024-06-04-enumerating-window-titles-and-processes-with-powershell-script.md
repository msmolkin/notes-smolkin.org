---
title: 2024-06-04
tags:
  - blog
date: 2024-06-04
slug: 2024-06-04-enumerating-window-titles-and-processes-with-powershell-script
---
3:15pm -07:00 (1717539357702)
# PowerShell Script: Enumerating Window Titles and Processes
My window titles were too long, so I couldn't see what was what. Just spent about 20 minutes trying to make it look good, rather than opening each one (that was causing me a headache, as all the windows looked the same and their titles all looked the same, so I kept opening the same window over and over).

google "Windows view all open window titles"
after 15 minutes:
##### [Find all window titles of application through command line](https://superuser.com/questions/1328345/find-all-window-titles-of-application-through-command-line)
A suitable name could be `GetWindowsTitles.ps1`.
```powershell
Add-Type  @"
    using System;
    using System.Runtime.InteropServices;
    using System.Text;    
    public class Win32 {
        public delegate void ThreadDelegate(IntPtr hWnd, IntPtr lParam);
        
        [DllImport("user32.dll")]
        public static extern bool EnumThreadWindows(int dwThreadId, 
            ThreadDelegate lpfn, IntPtr lParam);
        
        [DllImport("user32.dll", CharSet=CharSet.Auto, SetLastError=true)]
        public static extern int GetWindowText(IntPtr hwnd, 
            StringBuilder lpString, int cch);
        
        [DllImport("user32.dll", CharSet=CharSet.Auto, SetLastError=true)]
        public static extern Int32 GetWindowTextLength(IntPtr hWnd);

        [DllImport("user32.dll")]
        public static extern bool IsIconic(IntPtr hWnd);

        [DllImport("user32.dll")]
        public static extern bool IsWindowVisible(IntPtr hWnd);

        public static string GetTitle(IntPtr hWnd) {
            var len = GetWindowTextLength(hWnd);
            StringBuilder title = new StringBuilder(len + 1);
            GetWindowText(hWnd, title, title.Capacity);
            return title.ToString();
        }
    }
"@

$windows = New-Object System.Collections.ArrayList
Get-Process | Where { $_.MainWindowTitle } | foreach {
    $_.Threads.ForEach({
        [void][Win32]::EnumThreadWindows($_.Id, {
            param($hwnd, $lparam)
            if ([Win32]::IsIconic($hwnd) -or [Win32]::IsWindowVisible($hwnd)) {
                $windows.Add([Win32]::GetTitle($hwnd))
            }}, 0)
        })}

$sortedWindows = $windows | sort
Write-Output $sortedWindows
```

# Using Groq + Llama 3 to make the code work
If running scripts is disabled on the system, you can't run the script directly. However, you can still execute the PowerShell code by copying and pasting the code into the PowerShell console.

Here's how to do it:

1. Open the PowerShell console: You can do this by searching for "PowerShell" in the Start menu (Windows key + R) and running the PowerShell executable.
2. Copy the code: Select the entire code block and copy it to the clipboard.
3. Open the PowerShell console: Open the PowerShell console as described above.
4. Paste the code: Right-click in the PowerShell console and select "Paste" or press Ctrl+V to paste the code.
5. Execute the code: Press Enter to execute the code.

Alternatively, you can also use the `Set-ExecutionPolicy` cmdlet to temporarily allow running scripts. Here's how:

1. Open the PowerShell console.
2. Run the following command to set the execution policy to "Unrestricted" (not recommended for production systems):
```
Set-ExecutionPolicy -Scope CurrentUser -ExecutionPolicy Unrestricted
```
3. Run the script as usual:
```
.\GetWindowsTitles.ps1
```
Remember to set the execution policy back to its original value after running the script.

Please note that running scripts with an execution policy other than "Restricted" can pose a security risk. It's essential to understand the implications of changing the execution policy and only do so when necessary.

This whole post took me about 30 minutes. I didn't do much editing to the article, so the time was taken up almost completely by the "research" (in quotes because I think I'm just slow and it's not real research).