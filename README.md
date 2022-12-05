# Lostark DPS Meter

A fork of [https://github.com/karaeren/LostArkLogger](https://github.com/karaeren/LostArkLogger) with the capability to
remote log packets via winpcap for docker.

![Image](https://safe.manu.moe/9Sxwowoi.jpg)

Zero risk made possible with [tabfloater](https://www.tabfloater.io).

## Setup

We call the pc where you run the game the main computer and the pc where you run the dps meter the remote computer.
Both computers have to be in the same network.

It's possible but not recommended to run the dps meter on the main computer.

### First step: Setup docker

You have to install docker on the remote computer.

For instructions on how to install docker, check the [docker desktop](https://www.docker.com/).

### Second step: Setup rpcapd

You need to install [npcap](https://nmap.org/npcap/) on your main computer.

Make sure to have the option `Install Npcap in WinPcap API-compatible Mode` checked.

After that, you have to install rpcapd.

if your windows is blocked for install unsigned software, you have to disable it.

```powershell
Set-ExecutionPolicy Unrestricted
```

Then you can install rpcapd with the following command:

You can use the following [script to install it](bin/install-rpcapd.ps1).

This script install rpcapd as a service. You can check the service in your `services.msc` or with the following command:

```powershell
Get-Service rpcapd
```

### Third step: Configure and run the container

Run docker-compose to build the container.

```bash
docker-compose up -d --build
```

### Fourth step: Access the overlay

You can access the overlay by opening the following url in your browser:

```
http://<remote-computer-ip>:1338
```

## Support & Troubleshooting

We have a [discord server](https://discord.gg/bM8NtsJVeb) where you can ask questions or report bugs.

# WARNING

This is not endorsed by Smilegate or AGS. Usage of this tool isn't defined by Smilegate or AGS. I do not save your
personal identifiable data. Having said that, the .pcap generated can potentially contain sensitive information (
specifically, a one-time use token)

### Archive

You can find the old installation instructions [here](.github/archive/INSTALLATION.md).
