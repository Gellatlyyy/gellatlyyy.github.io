---
date: 2022-12-05T01:00:00.000Z
layout: post
title: Advent of Cyber - Day 5
subtitle: TryHackMe Advent of Cyber 2022 - Day 5.
description: A writeup of Day 5 - TryHackMe Advent of Cyber 2022 Challenge.
image: >-
  https://tryhackme.com/img/events/christmas/aoc4-wallpaper-2.png
optimized_image: >-
  https://tryhackme.com/img/events/christmas/aoc4-wallpaper-2.png
category: challenge
tags:
  - AOC2022
  - TryHackMe
  
author: Cameron Gellatly
paginate: true
---
# Learning Objectives

•	Learn about common remote access services.

•	Recognize a listening VNC port in a port scan.

•	Use a tool to find the VNC server’s password.

•	Connect to the VNC server using a VNC client.


# Task 1:
**Use Hydra to find the VNC password of the target with IP address 10.10.202.179. What is the password?**

Once connected to the attack box, we first run a stealth network scan to see if the there are any vulnerable ports exposed with this non-intrusive scan method.

We get the following results:
22/tcp – OPEN ssh
5900/tcp OPEN VNC

![img1](https://drive.google.com/uc?id=1Z8dlTaJOBJViYDhsr7JPvL39OjN7LurF)

Hydra can be used to brute force VNC credentials.
I first attempted to connect to 10.10.202.179 via Remmina VNC to see whether a username was required. This confirmed that no username is required and this can be omitted from the hydra command, leaving only the password to find.
The following command was used:

hydra -P /usr/share/wordlists/rockyou.txt 10.10.202.179 vnc

After ~2 mins, the following information was found

Host: 10.10.202.179

Password: 1q2w3e4r
 
Connected via VNC to target machine – flag located:
![img2](https://drive.google.com/uc?id=1WtJmTWJBwauJV8Z2BKZj5bqlZ3rrBval)
