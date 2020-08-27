# Running UWP on Linux with Uno Platform

Youtube Channel : https://youtube.com/FutureOfDotNet


Youtube : https://youtu.be/VjAfdm5_zVo


## Reference

* [Uno Platform and Windows Community Toolkit built app running on Ubuntu Linux, on Raspberry Pi](https://www.youtube.com/watch?v=l7mxSeSGyWU)
* [Running UWP on Linux With Uno](https://ian.bebbs.co.uk/posts/UnoLinux)

## Windows Terminal

* [Get Windows Terminal - Microsoft Store](https://www.microsoft.com/en-us/p/windows-terminal/9n0dx20hk701?activetab=pivot:overviewtab)
* PowerShell & Ubuntu

## .NET Core SDK 3.1.100

* [Download .NET SDKs for Visual Studio (microsoft.com)](https://dotnet.microsoft.com/download/visual-studio-sdks)

## Uno ProjectTemplates

* [NuGet Gallery | Uno.ProjectTemplates.Dotnet 3.0.12](https://www.nuget.org/packages/Uno.ProjectTemplates.Dotnet)
* dotnet new --install Uno.ProjectTemplates.Dotnet::3.1.0-dev.100

## WSL2(Windows Subsystem for Linux)

- [Windows Subsystem for Linux Installation Guide for Windows 10](https://docs.microsoft.com/en-us/windows/wsl/install-win10?WT.mc_id=DT-MVP-5000651)
  - https://bit.ly/31unnsp
- Install WSL
  - dism.exe /online /enable-feature /featurename:Microsoft-Windows-Subsystem-Linux /all /norestart
  - Restart machine
- Update to WSL2
  - Windows 10 version 1903 or higher, Build 18362
  - dism.exe /online /enable-feature /featurename:VirtualMachinePlatform /all /norestart
  - Restart machine
- wsl --set-default-version 2

## Install Ubuntu 20.04 LTS

- [Get Ubuntu 20.04 LTS - Microsoft Store](https://www.microsoft.com/en-us/p/ubuntu-2004-lts/9n6svws3rx71?activetab=pivot:overviewtab)

## Install X410

- [Buy X410 - Microsoft Store](https://www.microsoft.com/en-us/p/x410/9nlp712zmn9q?activetab=pivot:overviewtab)
- [X410 구매 - Microsoft Store ko-KR](https://www.microsoft.com/ko-kr/p/x410/9nlp712zmn9q?wa=wsignin1.0&activetab=pivot:overviewtab)

## X410 setting

- Allow Public Networks

## Test WSL2 + X Window Server

- sudo apt-get update
- sudo apt-get install vim-gtk

## Find my IP address

- ipconfig
- WSL -> IPv4 Address : 172.28.176.1

## Export Display Setting

- export DISPLAY=[IP Address]:0
  - ex) export DISPLAY=172.28.176.1:0

## Execute gvim

- gvim
- [Troubleshooting](https://github.com/cascadium/wsl-windows-toolbar-launcher/blob/master/README.md#troubleshooting)

## Create and Publish an Uno project

- dotnet new unoapp -o UnoLinux -w=false -wasm=false -ios=false -android=false -macos=false -sw=false
- cd .\UnoLinux\UnoLinux.Skia.Gtk\
- dotnet build
- dotnet publish --runtime linux-x64 -c Release --self-contained

## Running UWP on Ubuntu

- cd /mnt/[DRIVE LETTER]/[PATH]/UnoLinux/UnoLinux.Skia.Gtk/bin/Release/netcoreapp3.1/linux-x64
  - Ex) cd /mnt/c/users/kaki1/UnoLinux/UnoLinux.Skia.Gtk/bin/Release/netcoreapp3.1/Linux-x64
- ./UnoLinux.Skia.Gtk

## UWP app running in Ubuntu

- Uno UWP app
- Rendering to a Skia backend
- GTK host
- Ubuntu
- Windows Subsystem for Linux 2
