---
layout: post
title: How to Create Your Very Own VPN
subtitle: In less than 5 minutes
gh-repo: Nyr/openvpn-install
gh-badge: [star, fork, follow]
tags: [openvpn, vpn, privacy, vps]
comments: true
published: true
---

![VPNHEADER](/assets/img/VPN.jpg){: .mx-auto.d-block :}

### WHY DO YOU NEED A VPN?

As the years go by, the need for privacy has significantly increased. Goverments spying, Geoblocking, ISP spying, add agencies, etc. are just some examples of why having a relieable source of internet traffic encryption like a VPN is a neccasety.

### WHY SHOULD I BOTHER MAKING MY OWN VPN?

Although all the vpn providers claim and brag about their zero-logging policy, examples like [HideMyAss](https://www.hidemyass.com/) keep proving unless you take the matters in your own hand, you can never be sure.

Also, since nowadays its possible to get a VPS as low as $1 a month you can save a buck or two as well without being worried about getting dragged into a 3-year long contract.

### OPENVPN

![OPENVPNHEADER](https://slides.poul.org/2017/corsi-linux-avanzati/OpenVPN/openvpn_logo.png){: .mx-auto.d-block :}

A opensourced software for the host and client side VPN connection that is fully secure and fast. In fact, it so good, popular services like NordVPN and ProtonVPN use it in their commercial product.

### HOW DO YOU SET UP YOUR OPENVPN SERVER

First, you need a VPS (Virtual Private Server) to run the service on. My choice has alway been DigitalOcean for their simplicity and quality of service.
You can use my [refferal link](https://m.do.co/c/70b5599f91d9) to get 100 dollars credit for 60 days. that should be enough for a VPS that can do VPN and alot more for 2 months free of charge.

Then the usual way would be to go through with the OpenVPNs installation on your choice of OS on the VPS, but there is a much easier way.

Github user [Nyr](https://github.com/Nyr) has created a [shell script](https://github.com/Nyr/openvpn-install) for Linux, specifically debian based distros to make the installation much faster and easier. 
So, lets get to it.

```
wget https://git.io/vpn -O openvpn-install.sh && bash openvpn-install.sh
```
Now you are prompted with alist of all your internet IP addresses and you should choose your public IP address that your VPS provider has provided you.

{: .box-note}
**Note:** Its most likley the only of of them that is not a private IP address. TLDR; anything but 10.XX.XX.XX or 192.168.XX.XX

The next step is to choose a DNS provider for your VPN service to resolve your requests. My choice has always been [CloudFlare/1.1.1.1](1.1.1.1) for their security and speed, but [Google/8.8.8.8](https://developers.google.com/speed/public-dns/) and [Adgaurd](https://adguard.com/en/adguard-dns/overview.html) are also note worthy options.

Almost there! 

Now you should choose a name for your first connection, it can be anything. 

After that, the script will run and do its magic and save a .ovpn file in your user's home directory. Save the file to your client computer.

Download and isntall a client side application for your OS from [OpenVPN official page](https://openvpn.net/download-open-vpn/).

Now you can either insert or drag and drop the .ovpn file in the application and add it to your connection list. 

WALLAH!! Its done!! Now you have your own personal VPN service.

{: .box-note}
**Note:** I highley recommend you creating a new client for each connection since it will increase the speed of the your connection.

{: .box-warning}
**Warning:** Even though OpenVPN is very light and can run on pretty much any device, the number of clients connecting to your VPN at the same time tottally depends on the RAM and Bandwidth available to your VPS.
