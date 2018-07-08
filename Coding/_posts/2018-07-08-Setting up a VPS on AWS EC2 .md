---
layout: single
title: Setting up Virtual Private Server(VPS) on AWS EC2
categories: Coding
tags: 
- AWS
- EC2
- VPS
- VNC viewer
---

Recently, I wanted to experiment with blockchain. Instead of setting up a VM on my Macbook,
I decided to set up a VPS on cloud instead. I have tried Digital Ocean before. A comparison between
AWS and Digital Ocean concludes that Digital Ocean is cheaper as a IaaS. However, I will like
to learn how to use AWS which is more popular generally as a PaaS.
<br />
<br />

AWS is available for free during the first year on the free tier. For more information, check
out the details [here](https://aws.amazon.com/free/).

1. Download and install [VNC Viewer](https://www.realvnc.com/en/connect/download/viewer/)
<br />
<br />
2. Create a EC2 instance on AWS (Credits: [Creativevisions](http://cv-indonesia.com/how-to-set-up-virtual-private-server-vps-with-amazon-web-services/))
Since the instructions are pretty clear on the linked site, I will summarise the steps for setting 
up an EC2 instance.
- Launch an instance from EC2 dashboard
- Choose an Amazon Machine Image (AMI). I chose Ubuntu but whichever suits ur needs will do.
- Configure your instance security group to include SSH, HTTP/HTTPS.
- Finally, launch it.
- Upcoming prompt of key pair, give your key pair a name and download the key-pair.pem in a secure location.
- Take note of your public IP and DNS.
<br />
<br />
3. Set up Ubuntu GUI on your VPS [Credits: Arafat Khan](https://medium.com/@Arafat./graphical-user-interface-using-vnc-with-amazon-ec2-instances-549d9c0969c5)
- SSH into instance. 
```
cd <dir key-pair.pem>
chmod 400 <key-pair.pem>
ssh -i key-pair.pem ubuntu@<your public dns>
```
Note that the -i flag refers to identity file. 
- Update and install packages
```
sudo apt-get update
sudo apt-get upgrade
sudo apt-get install ubuntu-desktop gnome-panel gnome-settings-daemon 
metacity nautilus gnome-terminal xfce4 vnc4server
```
- Start vncserver in console
```
vncserver
```
- Modify VNC Configuration
```
vi ~/.vnc/xstartup
```
Replace contents with the following:
```
#!/bin/sh
# Uncomment the following two lines for normal desktop:
unset SESSION_MANAGER
# exec /etc/X11/xinit/xinitrc
unset DBUS_SESSION_BUS_ADDRESS
startxfce4 &
[ -x /etc/vnc/xstartup ] && exec /etc/vnc/xstartup
[ -r $HOME/.Xresources ] && xrdb $HOME/.Xresources
xsetroot -solid grey
vncconfig -iconic &
gnome-panel &
gnome-settings-daemon &
metacity &
nautilus &
gnome-terminal &
```
- Logout of instance and login using port forwarding.
```
ssh -L 5902:localhost:5902 -i key-pair.pem ubuntu@<public DNS>
```
- Start a new vncserver
```
vncserver -geometry 1920x1080
```
<br />
<br />
4. Connect to localhost on port 5902 on VNC viewer.

<br />
<br />

That's all. 