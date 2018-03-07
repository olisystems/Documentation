Tutorial_Version 1.0

# A quick starting tutorial for the OLIBOX v1

This tutorial will help you taking the first steps concerning the OLIBOX v1, a Development Platform for Blockchain & DLT applications in the Energy Sector.

## Featureset
The OLIBOX v1 offers the following:

- A powerful Embedded processing platform (RaspberryPi 3B based)
- An easy to use Linux environment for rapid development
- It´s very own measurement unit for easy access to real-life power-values
- It´s own web-server to easily browse power-values gained through the measurement unit
- SSH enabled

## First Startup

HASSAN HERE!
User names, Passwords and so on...

## Using TMUX

TMUX is a highly versatile tool for the administration of devices through an SSH tunnel. While a standard SSH tunnel only features one executable shell, TMUX will enable you to open multiple shells at once. 

There are many tutorials and cheat sheets available online:

Introduction to TMUX:
http://www.hamvocke.com/blog/a-quick-and-easy-guide-to-tmux/

Cheatsheet with shortcuts and other useful information:
https://www.cheatography.com/thecultofkaos/cheat-sheets/tmux-basics/

## Using the integrated measurement module

As mentioned in the Featureset above, OLIBOX v1 has its very own measurement module. It can be used to monitor and log real-life values from power lines after the installation of the Current-Transformers. 
*This installation should only be done by professionals who can qualify and quantify any risk that might be involved by the respective application.!*


OLIBOX v1 features its own web-server with a dashboard and a REST-API, from which you can get the power values. The general structure is:

http://<ipaddress>:1080/api/<phaseid>/<valueid>/now

*For <phaseid> you can choose*

<phaseid>/phase/comment
1/Phase 1
2/Phase 2
3/Phase 3
4/Neutral/ only for use with valueid current (current of  neutral conductor)
all/All phases


*For <valueid> you can choose*

<valueid>/unit/comment
current/Current [A]/(available for phase 1,2,3, neutral conductor)
voltage/Voltage [V]/(available for phase 1,2,3)
power/Power [W]/(available for phase 1,2,3)
cosphi/cos φ/(available for phase 1,2,3 –  it is important to measure the voltage)
frequency/Frequency [Hz]/(available for phase 1,2,3)
all/Get all Values

*The web-server in general is reachable at*
http://<ipaddress>:1080

*Tested Blockchain and DLT clients*

In our lab and real-life environment we have tested the following clients:

Geth: Full Node on Public and Private Networks
Parity: Full Node on Public and Private Networks
IPFS Node


