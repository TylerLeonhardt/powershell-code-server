# powershell-code-server

A complete PowerShell developer experience - all in a Docker container!

![screenshot](https://user-images.githubusercontent.com/2644648/55316260-dd4dde80-5422-11e9-9dd2-7303b5f21532.png)

This container image contains:
* Coder.com's [code-server](https://github.com/codercom/code-server)
* [PowerShell](https://github.com/PowerShell/PowerShell)
* The [PowerShell extension for vscode](https://github.com/PowerShell/vscode-powershell) which works with code-server

It's running in an Ubuntu 18.10 container. Once I figure out how to make code-server a bit more portable we can probably support more OS's.

You can find the Dockerfile for this container image [on GitHub](https://github.com/TylerLeonhardt/powershell-code-server).

## Let's go!

1. `docker pull tylerl0706/powershell-code-server`
2. `docker run -t -p 127.0.0.1:8443:8443 -v "${PWD}:/root/project" tylerl0706/powershell-code-server:stable code-server --allow-http --no-auth`
3. Open `http://localhost:8443` in your browser of choice

> The second command will start the container on port `8443` and mount whatever is in `PWD` allowing you to actually modify the files on your host OS from within the container.

## Tags

* *stable:* contains the latest stable version of the PowerShell extension and PowerShell
* *latest:* contains the latest version (stable or not) of the PowerShell extension and PowerShell
* *1.12.0-pwsh:* contains the 1.12.0 version of the PowerShell extension and the latest stable version of PowerShell
* *2.0.0-preview.2-pwsh:* contains the 2.0.0-preview.2 version of the PowerShell extension and the latest stable version of PowerShell
