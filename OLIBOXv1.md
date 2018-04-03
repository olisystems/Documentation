Tutorial_Version 1.0

# A quick starting tutorial for the OLIBOX v1

This tutorial will help you taking the first steps concerning the OLIBOX v1, a Development Platform for Blockchain & DLT applications in the Energy Sector.

## Featureset
The OLIBOX v1 offers the following:

- A powerful Embedded processing platform (RaspberryPi 3B based)
- An easy to use Linux environment for rapid development
- It´s very own measurement unit for easy access to real-life power-values
- It´s own web-server to easily browse power-values gained through the measurement unit
- SSH
- Fleet Management (only from OLI Systems HQ)

## First Startup
To login, username and password is needed. Default username and password is given below.
- Username: As defined at the back of OLI box e.g. OLI_01
- Password: "password"(can be changed later)

## Using SSH

We highly recommend the usage of public and private keypairs for OLIBOXES v1 deployed in the field. Passwords can be brute-forced, so a PKI with local password encryption adds another layer of security.

## Using TMUX

TMUX is a highly versatile tool for the administration of devices through an SSH tunnel. While a standard SSH tunnel only features one executable shell, TMUX will enable you to open multiple shells at once. With TMUX, you will be able to easily monitor multiple processes at once.

There are many tutorials and cheat sheets available online:

Introduction to TMUX:

http://www.hamvocke.com/blog/a-quick-and-easy-guide-to-tmux/

Cheatsheet with shortcuts and other useful information:

https://www.cheatography.com/thecultofkaos/cheat-sheets/tmux-basics/

## Using the integrated measurement module

As mentioned in the Featureset above, OLIBOX v1 has its very own measurement module. It can be used to monitor and log real-life values from power lines after the installation of the Current-Transformers. 

**This installation should only be done by professionals who can qualify and quantify any risk that might be involved by the respective application environment.!**

OLIBOX v1 features its own web-server with a dashboard and a REST-API, from which you can get the power values. The general structure is:

http://ipaddress:1080/api/phaseid/valueid/now

**For phaseid you can choose**

phaseid/phase/comment

1/Phase 1

2/Phase 2

3/Phase 3

4/Neutral/ only for use with valueid current (current of  neutral conductor)

all/All phases

**For valueid you can choose**

valueid/unit/comment

current/Current [A]/(available for phase 1,2,3, neutral conductor)

voltage/Voltage [V]/(available for phase 1,2,3)

power/Power [W]/(available for phase 1,2,3)

cosphi/cos φ/(available for phase 1,2,3 –  it is important to measure the voltage)

frequency/Frequency [Hz]/(available for phase 1,2,3)

all/Get all Values

*The web-server in general is reachable at*

http://ipaddress:1080

## Tested Blockchain and DLT clients

In our lab and real-life environment we have tested the following clients:

Geth 1.8.3 ARMv7: Full Node on Public and Private Networks

Parity 1.9.4 beta ARMv7 : Full Node on Public and Private Networks

IPFS Node

### A quick note on Blockchain Clients and SD Cards:

If you are installing your Blockchain Client on your OLI Box, you will probably shift all the files and binaries to the SD Card, which is in first instance the only mass storage on the system. Please be aware that the SD Card basically forms a single-point of failure for the OLI Box. The many Write commands from the Client can accelerate the aging process due to electrochemical processes inside the SD Cards and the connection pins. It is therefore better to store the client and/or the included database on a separate USB-Stick that is connected to the Pi. This is mainly a problem with FUll nodes, as they store every single transaction and contract locally. Light clients with the right configuration can circumvent this problem though, as they do not feature as many write processes.
