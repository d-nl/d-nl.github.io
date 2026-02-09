---
title: "VPS - Installing nginx"
excerpt: "Write-up on first experiences setting up a VPS as a reverse-proxy. <br/><img src='/images/nginx1.png' style='width:500px; height:auto;' />"
collection: VPS
---

Hello! This is one of my first homelabs, focusing on utilizing a remote VPS I purchased as a reverse-proxy for miscellaneous applications, mainly for note-taking and IP tunnels.

As the VPS runs Ubuntu, I mainly utilized nginx and docker to set up these applications, and then simply served them at the VPS's IP address with a self-signed certificate. These are mostly for personal use, and I figured the process was interesting to write up. 

Funnily enough, the similarities between Docker and Microsoft's Azure CLI became extremely apparent after I managed to get the former running.

![Screenshot of me installing nginx on the VPS](/images/nginx1.png){: width="500px" height=auto}
The above screenshot is a log file outputted from PuTTY, the application I used to connect to the VPS from a Windows client. Once on, I decided to install nginx, the open-source web server of choice for Linux. In hindsight, I could've used Caddy, which is much more approachable.
