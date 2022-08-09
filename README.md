# wsl-ubuntu-gui

This repo contains all the steps to download Ubuntu and use its GUI on a Windows system

## WSL commands: ##

Type the following WSL commands in Powershell to download WSL

```
dism.exe /online /enable-feature /featurename:Microsoft-Windows-Subsystem-Linux /all /norestart

dism.exe /online /enable-feature /featurename:VirtualMachinePlatform /all /norestart

wsl --set-default-version 2

```
Now , go to Microsoft Store and download the latest version of Ubuntu. After that open your new Ubuntu terminal by searching Ubuntu and type the following commands

## Ubuntu GUI commands: ##

Type the following commands in Ubuntu terminal to get the GUI version of Ubuntu

```
sudo apt update && sudo apt -y upgrade

sudo apt-get purge xrdp

sudo apt install -y xrdp

sudo apt install -y xfce4

sudo apt install -y xfce4-goodies

sudo cp /etc/xrdp/xrdp.ini /etc/xrdp/xrdp.ini.bak

sudo sed -i 's/3389/3390/g' /etc/xrdp/xrdp.ini

sudo sed -i 's/max_bpp=32/#max_bpp=32\nmax_bpp=128/g' /etc/xrdp/xrdp.ini

sudo sed -i 's/xserverbpp=24/#xserverbpp=24\nxserverbpp=128/g' /etc/xrdp/xrdp.ini

echo xfce4-session > ~/.xsession

sudo nano /etc/xrdp/startwm.sh
```
##  Comment these lines to: ##
```
#test -x /etc/X11/Xsession && exec /etc/X11/Xsession

#exec /bin/sh /etc/X11/Xsession
```
## Add these lines: ##


```
# xfce

startxfce4
```
## To start the Remote Desktop Connection ##
```
sudo /etc/init.d/xrdp start
```

## Now in Windows, use Remote Desktop Connection ##

1. Search for remote desktop connection

2. Set the computer as localhost:3390

3. Login using your Ubuntu username and password


## Links for Reference and extra information :##

1. Microsoft GUI announcement: https://devblogs.microsoft.com/commandline/the-windows-subsystem-for-linux-build-2020-summary/

2. Ubuntu WSL2 GUI Install:

3. https://dev.to/darksmile92/linux-on-windows-wsl-with-desktop-environment-via-rdp-522g

4. WSL 2 install: https://docs.microsoft.com/en-us/windows/wsl/install-win10

5. Docker for WSL2: https://docs.docker.com/docker-for-windows/wsl/

6. What is WSL? https://docs.microsoft.com/en-us/windows/wsl/about

7. WSL documentation: https://docs.microsoft.com/en-us/windows/wsl/

8. WSL 2 Announcement: https://devblogs.microsoft.com/commandline/announcing-wsl-2/
