+++
title = "Summer 2025 Review"
date = "2025-08-16"
+++

I have been away from my setup for the past two months. I've only been programming on my laptop without a monitor, desk, or chair. I have mainly just been programming in a bed.

I say this because it let's you understand why, after a long day of travelling, when I finally reunited with my setup, I wasted no time in getting to prorgamming.

The past hour and a hlaf of programming has been blissful, let me tell you. I was enjoying programming with just my laptop these past two months because my virtual setup had kept getting better with neovim and tmux and karabiner etc. but golly. Suddenly combining my virtual improvements with the luxuries of a standard ikea desk, costco chair, and 24 inch dell monitor, I have not felt this much joy in programming in so long. I am being very serious when I say I forgot how large a 24 inch monitor was. I have been so used to my little 14 inch laptop.

Now with that appreciation for my boring setup that I have never felt so grateful for, I need to talk to you about sockets.

So essentially I logged on and I needed to program something, I thought well I don't have too many hours before I need to fall asleep so I'll work on Vantage Fit tomorrow, and I wanted to do something a little cooler than writing out the steps for different algorithms for algo-vis.

So I decided I'm going to try to figure out the cpu intensity of Jarvis. Right now my little voice assistant is incredibly cpu intensive. When I run the python script it takes up a whole cpu just to idle. Mind you, this is after I tried to integrate a system where it listens for a custom keyboard shortcut and then runs the acutal heavy part of the program. This system did help a litte but we are still using a lot of cpu just for the python program to idle. 

The issue is that python is simply too slow and cumbersome.

So, I had writen a program in pure C. This is a simple keyboard listener that listens for a specific keyboard shortcut that I would use to activate Jarvis and allow him to listen to my voice command.

Now what I had noticed is this C program, sure enough, is super effecient. It uses hardly any cpu and is incredibly responsive.

So then I started doing some research. I wanted to see if thre was a way to use the C program to startup the python program and not have any latency from the python program starting up.

And then I realized I could use sockets. Now I've used sockets in the past but very briefly.

But, this was perfect for me cause I was planning on having jarvis act like a server with an api in the future anyway so setting up a server now to run the main voice command program would actually set me up perfectly for later.

Now let me tell you, setting it up was a breeze. I just had to send a message on the socket from the C program whenever it noticed the keyboard shortcut and then the python program would just idle, listening on the socket, and when there was a message it would handle the voice command: Jarvis would listen to me, the speech to text model would go off, the command would be categorized, the command would be executed, any text to speech would take place and then it would go back to idling and I could call it again at the press of a button.

Now the truly magical thing to me was the perfomance advantage. Boy howdy, integrating sockets made it so the python program no longer was eating up cpu, it only used cpu in the five seconds where Jarvis was listening and responding and when it's idle, it no longer uses almost any cpu. 

Super happy with the performance gains. I can now just run Jarvis on my computer all the time without any extra cpu usage. I can now comfortably continue to add new commands to Jarvis.

