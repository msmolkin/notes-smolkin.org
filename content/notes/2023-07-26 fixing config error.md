---
title: "2023-07-26"
tags:
- blog
---
2:14pm -07:00 (1690406083618)
Pretty cool. What happened:
```
 1003  git add i18n
 1004  status
 1005  git commit -am "Remove external links" -m " - Changed copyright message to remove external links" -m " - This may get Jacky Zhao [the author] a bit annoyed at me, but I didn't see any terms that said I had to include a link to his page on every single page of my website. I added an attribution to the hello world file"
 1006  git log --oneline
 1007  git checkout bb38779 -- data/config.yaml
 1008  git checkout data/config.yaml
 1009  status
 1010  git checkout config.yaml
 1011  git checkout data/config.yaml
 1012  git checkout HEAD data/config.yaml
 1013  history | tail -n 10 | pbcopy
```
What it means:
I figured out how to modify the part on the bottom of every page that has a link
I changed the config file that does it, in every language
I pushed them
Then figured out what the issue was that's preventing pushing: improperly formatted template file
To confirm, nice and cleanly checked out the offending file from back when it was correct
Confirmed the proper formatting
Then checked out my edited file, updated it with proper formatting
Now just need to save it, commit, and push
And I'll include this note in the push. So, if this article shows up on my site, we'll know that it went through.

I like these nice and clean notes. No fluff. I can add ads if I want, but the main page is simple and clean for people to view.