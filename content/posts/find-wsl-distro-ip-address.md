---
title: "Get a WSL Distro IP Address"
date: 2022-08-13T10:14:05+01:00
publishDate: 2022-08-13T11:00:00+01:00
description: Get the IP address of a WSL (Windows Subsystem for Linux) distribution via powershell.
draft: false
tags:
  - Powershell
  - Windows
  - WSL (Windows Subsystem for Linux)
---

## Getting the IP Address via Powershell

### Get the IP address for the default distribution

If the default distro is not running, this will start the default distro and return the IP once running.

{{< highlight "linenos=false" >}}
PS> wsl hostname -I
192.168.78.100
{{< /highlight >}}

### Get the IP address for a non-default distribution

List all of the running WSL distributions (omit `--running` flag to list all, regardless of state).

{{< highlight "linenos=false" >}}
PS> wsl -l --running
Windows Subsystem for Linux Distributions:
Ubuntu (Default)
Arch
{{< /highlight >}}

Get the IP for the specific distribution with `wsl -d <distro> hostname -I`.

{{< highlight "linenos=false" >}}
PS> wsl -d "Ubuntu" hostname -I
192.168.78.100

PS> wsl -d "Arch" hostname -I
192.168.78.110
{{< / highlight >}}
