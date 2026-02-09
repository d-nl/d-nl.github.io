---
title: "VPS - Installing nginx"
excerpt: "Write-up on first experiences setting up a VPS as a reverse-proxy. <br/><img src='/images/nginx1.png' style='width:500px; height:auto;' />"
collection: VPS
---

Hello! This is one of my first homelabs, focusing on utilizing a VPS I bought as a reverse-proxy for miscellaneous applications, mainly for note-taking and IP tunnels.

I mainly utilized nginx and docker to set up these applications, and then serve them at the VPS's IP address with a self-signed certificate. These are mostly for personal use, but I figured the process was interesting to write up.

![Screenshot of me installing nginx on the VPS](/images/nginx1.jpg){: .align-right width="500px" height=auto}
