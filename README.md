# wsl-ubuntu-gui

## WSL commands: ##

1. dism.exe /online /enable-feature /featurename:Microsoft-Windows-Subsystem-Linux /all /norestart

2. dism.exe /online /enable-feature /featurename:VirtualMachinePlatform /all /norestart

3. wsl --set-default-version 2

## Ubuntu GUI commands: ##

1. sudo apt update && sudo apt -y upgrade

2. sudo apt-get purge xrdp

3. sudo apt install -y xrdp

4. sudo apt install -y xfce4

5. sudo apt install -y xfce4-goodies

6. sudo cp /etc/xrdp/xrdp.ini /etc/xrdp/xrdp.ini.bak

7. sudo sed -i 's/3389/3390/g' /etc/xrdp/xrdp.ini

8. sudo sed -i 's/max_bpp=32/#max_bpp=32\nmax_bpp=128/g' /etc/xrdp/xrdp.ini

9. sudo sed -i 's/xserverbpp=24/#xserverbpp=24\nxserverbpp=128/g' /etc/xrdp/xrdp.ini

10. echo xfce4-session > ~/.xsession

11. sudo nano /etc/xrdp/startwm.sh

##12. Comment these lines to:##

#test -x /etc/X11/Xsession && exec /etc/X11/Xsession
#exec /bin/sh /etc/X11/Xsession

##13. Add these lines:##

# xfce
startxfce4

14.sudo /etc/init.d/xrdp start

##Now in Windows, use Remote Desktop Connection##

1.Search for remote desktop connection

2. Set the computer as localhost:3390

3. Login using your Ubuntu username and password


Links for Reference and extra information :

1.Microsoft GUI announcement: https://devblogs.microsoft.com/commandline/the-windows-subsystem-for-linux-build-2020-summary/

2.Ubuntu WSL2 GUI Install:

3.https://dev.to/darksmile92/linux-on-windows-wsl-with-desktop-environment-via-rdp-522g

4.WSL 2 install: https://docs.microsoft.com/en-us/windows/wsl/install-win10

5.Docker for WSL2: https://docs.docker.com/docker-for-windows/wsl/

6.What is WSL? https://docs.microsoft.com/en-us/windows/wsl/about

7.WSL documentation: https://docs.microsoft.com/en-us/windows/wsl/

8.WSL 2 Announcement: https://devblogs.microsoft.com/commandline/announcing-wsl-2/
