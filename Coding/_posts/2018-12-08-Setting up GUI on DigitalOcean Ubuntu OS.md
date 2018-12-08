---
layout: single
title: Setting up GUI on DigitalOcean Ubuntu OS
categories: Coding
tags: 
- DigitalOcean
- VNC viewer
---

DigitalOcean offers affordable VPS for teams to collaborate anywhere in the world. It's very easy to set up Linux servers on the platform.
<br />
<br />
I will document down the process to add a GUI according to this [link](https://www.digitalocean.com/community/tutorials/how-to-install-and-configure-vnc-on-ubuntu-16-04)
<br />
<br />
1. SSH into VPS
```
ssh root@<ip address>
```
2. Install Xfce and TightVNC
```
sudo apt-get update
sudo apt install xfce4 xfce4-goodies tightvncserver
```
3. Initial configurations VNCserver by setting passwords
```
vncserver
```
4. Default port for VNCserver is 5901. In order to reconfigure VNCserver, we need to kill instance of VNCserver first. :1 represents port 5900+1
```
vncserver -kill :1
```
5. Backup config file
```
mv ~/.vnc/xstartup ~/.vnc/xstartup.bak
```
6. Modify config file. Tell VNCserver to read from resources files and start
```
#!/bin/bash
xrdb $HOME/.Xresources
startxfce4 &
```
7. Grant executable privileges 
```
sudo chmod +x ~/.vnc/xstartup
```
8. Restart VNC server
```
vncserver
```
9. Forward to localhost of VNC client on local machine
```
ssh -L 5901:127.0.0.1:5901 -N -f -l username server_ip_address
```
10. Login using credentials
11. Viola!

<br />

In case port is binded, run the following to check the pid and kill the process
```
lsof  -i :<port number>
kill -9 <PID>
```
<br />
That's all.