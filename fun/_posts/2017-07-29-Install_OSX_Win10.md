---
layout: single
title: Installing Qlik Sense on MacOS Sierra (VirtualBox)
categories: fun
---

Qlik Sense are not compatible with MacOS, so is there any workaround? Yes there is! All you need
is a Windows VM.
<br />

### Download Qlik Sense Desktop
Go ahead and download the installer for [Qlik Sense](http://www.qlik.com/us/try-or-buy/download-qlik-sense).
You will need to first register an account by filling up a simple form. Upon completion, the download will take place.
<br />
### VirtualBox
Next, download a copy of [VirtualBox](https://www.virtualbox.org/). Install it.
<br />
### Windows 10
Download a copy of [Windows 10](https://www.microsoft.com/en-us/software-download/windows10ISO).
The installation guide can be found [here](https://betanews.com/2015/07/29/how-to-install-windows-10-on-oracle-virtualbox-no-windows-key-required/).
<br />
### Adding a shared folder with VirtualBox
According to a [StackOverflow answer](https://stackoverflow.com/questions/27355688/shared-folder-between-macosx-and-windows-on-virtual-box)
1. VirtualBox Manager: Open the Shared Folders setting and click the '+' icon to add a new folder. Then, populate the Folder Path 
(or use the drop-down to navigate) with the folder you want shared and make sure "Auto-Mount" and "Make Permanent" are checked.
2. Boot Windows
3. Once Windows is running, goto the Devices menu (at the top of the VirtualBox Manager window) and select 
"Insert Guest Additions CD Image...". Cycle through the prompts and once you finish installing, let it reboot.
4. After Windows reboots, your new drive should show up as a Network Drive in Windows Explorer.
5. Drop Qlik Sense installer into the shared folder and access the file in VirtualBox via the shared folder.
6. Go ahead and install.

<br />
Have fun with Qlik Sense!