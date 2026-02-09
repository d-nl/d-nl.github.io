---
title: "VPS - Installing nginx"
excerpt: "Write-up on first experiences setting up a VPS as a reverse-proxy. <br/><img src='/images/nginx1.png' style='width:500px; height:auto;' />"
collection: VPS
---

Hello! This is one of my first homelabs, focusing on utilizing a remote VPS I purchased as a reverse-proxy for miscellaneous applications, mainly for note-taking and IP tunnels.

As the VPS runs Ubuntu, I mainly utilized nginx and docker to set up these applications, and then simply served them at the VPS's IP address with a self-signed certificate. These are mostly for personal use, and I figured the process was interesting to write up. Some initials parts of the VPS have been omitted, such as the user creation of *alma21* (my username) and sudo permission assignment over using admin.

Funnily enough, the similarities between Docker and Microsoft's Azure CLI became extremely apparent after I managed to get the former running.

![Screenshot of me installing nginx on the VPS](/images/nginx1.png){: width="500px" height=auto}

The above screenshot is a log file outputted from PuTTY, the application I used to connect to the VPS from a Windows client. After familiarizing myself with the system, I decided to install nginx, the open-source web server of choice for Linux. In hindsight, I could've used Caddy, which is much more approachable.

![Screenshot of me verifying nginx installation, opening the firewall, and updating](/images/nginx2.png){: width="500px" height=auto}
![Default nginx page](/images/defaultsite.jpg){: .align-right width="500px" height=auto}
In this screenshot, I verify nginx is active using *systemctl*. I then allow nginx to be accessed through the firewall, allowing me to see it from my personal PC. I also update apt, just in case.

![Screenshot of me installing Docker](/images/nginx3.png){: width="500px" height=auto}
![Screenshot of me installing Docker](/images/nginx4.png){: .align-right width="500px" height=auto}

After some messing around, I eventually install Docker, which I will depend on for hosting applications, and then serve them through nginx. I verify Docker's working using a process called "Hello World."

![Screenshot of me installing Docker](/images/nginx5.png){: width="500px" height=auto}

I make sure my firewall is open for 80 and 443, http and https. Offscreen, I install certbot to self-sign my VPS's certificate, so I can use HTTPS and be a little more secure.

![Screenshot of me installing Docker](/images/nginx6.png){: width="500px" height=auto}

I then begin to edit the /etc/nginx/sites-available/default file, which is how I can serve a reverse proxy through nginx, simply by pointing the open 443 port to the application's local port (you can also see how I've set up the ssl certificate in this file). For example, I decided to install Wireguard in Docker offscreen. By pointing Wireguard's local port (51821) to the open HTTPS (443) port designated /wireguard/ ...

![Screenshot of me installing Docker](/images/nginx7.png){: width="500px" height=auto}

I can access it from my PC! Pretty simple, but easy to overcomplicate.
