---
layout: post
author: mossbeasts
tags: computers
---
The following is loosely adapted from a series of notes I posted on my OCF site about a year ago. I'm assuming that you're using NetworkManager to do this, and that you'd like to use the CLI as much as possible (like year-ago-me, who was too stubborn to instal a gui-based program to do it.

## Troubleshooting steps
- changing the capitalization of mschapv2 seems to be a widely-recommended place to start. "mschapv2" works for me; "MSCHAPV2" doesn't. This is the opposite of the recommendations in the arch wiki - I assume that either someone left their capslock on, or there's been an update.
- I would sometimes randomly get dhcp failures (they've since stopped, not thanks to anything I did). I found that restarting iwd, NetworkManager, and nm-applet usually worked. Editing /etc/NetworkManager/system-connections/eduroam.nmconnection, saving the change, and then deleting it *also* worked, though it was more work. Not sure what the reason behind that was, or why it stopped.
- PEAP worked on linux mint; ttls works on arch. A later update: both work on arch, though I got some weird intermittent lag with PEAP. I'm currently using ttls.
- try regenerating your eduroam password until you get one without any symbols like " or &. NetworkManager didn't like them. This is assuming, of course, that your institution doesn't allow you to set your own eduroam password. (Mine does not, unfortunately.)
- There is, theoretically, a way to do this all with iwd, if NetworkManager is not your thing. I never managed to get it working; I've read blog posts by people who have. Let me know which one works for you.
- If you've got any friends who've got eduroam working, see if you can steal a copy of their config (minus identifying information, of course). It should give you a good place to start.
