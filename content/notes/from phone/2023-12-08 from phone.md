Today, I learned electrical engineering:

Of course, I don’t mean to insult all the very smart people who study this as their discipline, I just learned the basics of it that were required to do what I needed.

I went to go help someone sign up for a new system online, and I decided to use her portable charger to charge my phone while I was there. She told me that this is a second one, because the one that she had earlier fell while they were moving the other day. The battery pack opened somewhat, so there was a bulge, and I guess somethings weren’t working anymore. I figured the problem is probably just that some things shifted, so I asked what she’s planning on doing with the old one. “Garbage,“ came the response.

“Can I have it then?”

On my way home, I noticed that this battery pack uses standard Phillips head screws, so it shouldn’t be too hard to take apart and take a look at it.

As soon as I got home, I took a small screwdriver that we’ve had for maybe 15 years. This thing is bent, but it has outlasted several other miniature screwdrivers in that it never got lost, and it never actually broke. I’ve been using it nearly forever since I was a little kid and wasn’t really tinkering with tools and much for fear of getting yelled at if I broke something. Four screws on the four corners; one of them was a little tough to deal with, and I don’t know whether that’s because the screw was broken already or because I haven’t opened screws often and therefore maybe I wasn’t applying enough pressure when beginning to unscrew it.

I opened it, and I didn’t see much problem. All I saw was that it seems one of the leads connecting to the QI wireless charging, seems to have come undone, and I couldn’t figure out exactly where it goes. After a few minutes of fiddling, I realized there were two screws on the inside that connected the PCI board to the other side of the container

I took off the screws, and I took a spare wireless charging enabled phone that I had, and turned on sound  on the phone and pressed the power button on the Power Bank. Then I went to connect the disconnected lead to various metal attachments on the PCI board, beginning with the one that I thought most likely, to see if the wireless charging would work. Given that the light turned on when I pressed the power button, I assumed that everything else was still intact. I really only had two possibilities in mind, and the first one was right.

Now, all that’s left to do is solder it on.

In comes ChatGPT, and here’s my conversation with GPT-4 (remember, this is now with the gpt-4-1123-preview, which they have made a little bit dumber than GPT4 and which has a higher context window—even though I really didn’t need the context window in this case):

> How do you solder a lead to a board?
> 
>ChatGPT
>To solder a lead to a board, follow these steps:
>1. **Prepare the Soldering Iron**: Heat it up to the appropriate temperature.
>1. **Clean the Tip**: Wipe the soldering iron tip on a damp sponge.
>2. **Tin the Tip**: Apply a small amount of solder to the tip.
>3. **Place the Lead**: Insert the lead through the appropriate hole in the board.
>4. **Apply Heat**: Touch the tip to the lead and the pad on the board, heating both.
>5. **Apply Solder**: Feed solder to the joint, not the iron tip, until it flows around the lead and pad.
>6. **Remove the Iron**: Lift the iron away while keeping the lead still.
>7. **Inspect the Joint**: Ensure it's shiny and well-connected.

How do you reconnect a lead to a board if it came off along with the solder?

>To reconnect a lead to a board where it came off along with the solder, follow these steps:

>1. **Clean the Area**: Remove any old solder from the pad on the board using solder wick or a solder sucker.
>2. **Prepare the Lead**: If the lead is damaged, trim and strip it (if it's a wire) or straighten it (if it's a component leg).
>3. **Tin the Lead and Pad**: Apply a small amount of fresh solder to the lead and the pad on the board.
>4. **Position the Lead**: Hold the lead in place on the board.
>5. **Heat and Solder**: Apply the soldering iron to both the lead and pad, then feed solder until it forms a good joint.
>6. **Cool the Joint**: Remove the iron and allow the solder to cool naturally without moving the lead.
>7. **Inspect**: Ensure the joint is shiny and well-connected, with no cold solder or bridges to adjacent pads.

Now, I don’t have a soldering iron here in San Francisco, but there are plenty who do. Too bad they all charge 20 bucks to fix a tiny issue. Off to Home Depot to get a cheap soldering iron.

Before (I didn’t take any photos before opening the case, but here’s one clearly showing the problem):
![[IMG_9013.jpeg]]

After:


And once I do get around to actually fixing the power bank, I’ll add in here whether I had to adjust anything if the case didn’t click shut once I had finished. The fact that it popped open actually helped me because it made it easier to see what exactly I had to do to open it up.