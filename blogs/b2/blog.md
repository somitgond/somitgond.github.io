## Xsetroot Problem:  
Description: I encountered a problem when setting background with xsetroot. I don't use feh, nitrogen, xwallpaper or any other background setter application. I wanted to find a minimal program that can be used to set my background as a solid color. I ran the code ``` xsetroot -solid black ```. But the background doesn't change. The background remains gray in color.   

Background: For your information I am currently on Debian 12 using dwm, st, slstatus, xcompmgr etc. I am trying to find minimal programs i.e programs that use less RAM and CPU. I have used feh, nitrogen, xwallpaper as wallpaper setting application. I don't have any specific requirements regarding desktop background, it can be anything other than solid black.  

What is xsetroot: You can read its manual page [here](https://www.x.org/archive/X11R7.5/doc/man/man1/xsetroot.1.html) or just from searching on the internet. So, xsetroot is root window parameter setting utility for X as stated in the manual. One of its main feature is that you can set the background of the root window.  

## The Solution:  
The quest to find the solution to the problem:
1. As usual I started with scrouing the internet for the solution I found some leads, that i am not the only one suffering from the problem.
2. Basically what I came to know is that some other application is setting the root window background after xsetroot. 
3. Now how to find that application. 
    - I checked any sytemd service which can be causing the issue. After enabling and disabling a bunch of services. I didn't find anything. The problem still persisted.
    - Then I check if any autostart application was causing the issue.
    - Then finally I turned off my compositor manager. Guess what? It was causing the issue. 
So, We finally found the solution to our problem. The compositor was redrawing on the root window.

Afterwards I did additional search on the internet and I found many people has already discovered it :), Guess I need to sharpen my OSINT skills :(

PS: For those who don't know about compositor read about it [here](https://en.wikipedia.org/wiki/Compositing_window_manager).


