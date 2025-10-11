# unattended Windows 11 Setup

This is meant for new pcs and laptops primarly for my own usage, because you should not install your system based on the settings and scripts that someone else made. If you stumble upon this, use it as a blueprint for your own setup.

based on Schneegans.de and ChrisTitusTech
 - activates local integrated administrator account with the password "changeme"
 - debloates preinstalled Apps
 - dectivates/minimizes telemetry

## Generell Usage (but please make your own)
Windows OOBE
SHIFT + F10
```powershell
curl -L -o C:\Windows\Panther\unattend.xml https://raw.githubusercontent.com/soundmountain/unattend/refs/heads/main/unattend.xml
%WINDIR%\System32\Sysprep\Sysprep.exe /oobe /unattend:C:\Windows\Panther\unattend.xml /reboot
```

## My Usage
Since I don't want to type a lot, I created a subdomain u.domain.tld with a webserver and certificate that redirects to https://raw.githubusercontent.com/soundmountain/unattend/refs/heads/main/unattend.cmd

So I only type
```powershell
curl -L -o unattend.cmd u.domain.tld
unattend.cmd
```
