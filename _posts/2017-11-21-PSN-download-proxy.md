---
layout: post
title: Setting up a local proxy to speed up PSN downloads
---

With the PSN sale this week, a lot of people will be buying games and downloading them. Download speeds on PSN have gotten better (depending on the area, at least it is for me), but it is still kind of slow compared to Steam, Origin, etc and does not use the full bandwidth of your internet plan from your ISP. I came across this [post](https://www.reddit.com/r/PS4/comments/522ttn/ps4_downloads_are_notoriously_slow_i_might_have/d7gvuvh/) from last year detailng the technical reasons why this is the case. 

As always, the easy fix is always in the comments. The top reply has instructions on how to use ccproxy but I wanted to do a quick writeup on using squid for Windows since it's a trusted open source software on all platforms (macOS, linux or Windows). For macOS, there is squidman, and for pc there is [squid](http://squid.diladele.com/). I will forego linux since I figure if you're using linux, you already know what you're doing.

Instructions:

1. Download the msi installer for Windows ([latest version](http://packages.diladele.com/squid/3.5.27/squid.msi)) and install it
2. Open powershell and run this command: `test-netconnection localhost -port 3128`.
You are looking for the tcptestsucceeded to be true. This means the squid service is running.
3. Run `ipconfig` to find your IP address. It will probably be 192.168.1.x or 192.168.0.x on most networks.
4. Go to your PS4 and open settings->network->set up internet connection->wifi/lan (choose as needed)->custom
5. Accept defaults for all until you get to proxy. Enter the IP address of your pc, and the port number is 3128.

That's it. Now test your new download speeds! Configuring your pc with a static IP would be helpful if you tend to use this a lot, but I would say leave it alone while playing games normally so it won't affect your online play. Swap the network settings to use your pc when you play to download large games.
