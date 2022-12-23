---
date: 2022-12-04T01:00:00.000Z
layout: post
title: Advent of Cyber - Day 4
subtitle: TryHackMe Advent of Cyber 2022 - Day 4.
description: A writeup of Day 4 - TryHackMe Advent of Cyber 2022 Challenge.
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

•	What is Scanning?

•	Scanning types

•	Scanning techniques

•	Scanning tools

The qa.santagift.shop site has been taken down for maintenance after being compromised.
We need to run a port scan on the web server to gather information.
Connected to the Attack Box and received IP of 10.10.198.1
Ran nmap scan on network with nmap -sC -sV 10.10.198.1
-sC – Standard network scan using default scripts.
-sV – Version detection for discovery of operating systems.

Results:
Port 22 OPEN (SSH) – OpenSSH 7.6p1 Ubuntu
Port 80 OPEN – Apache server 2.4.29 Ubuntu
Port 139 0 Samba smbd 3.x – 4.x
Port 445 Samba smbd 4.7.6 Ubuntu

Additional info:
Smb-security-mode:
Account-user: guest
Authentication_level: user
Challenge_response: supported
Message_signing: disabled.

SMB may be vulnerable.
Testing smb:
Navigated to smb://10.10.198.1 in file explorer.

![img1](https://drive.google.com/uc?id=1Nzkg0lrdGtml4DN6A1kPP9lz7A7jy-yI)

Password required to enter folders.
Tested credentials found in the OSINT phase with domain located in nmap scan:

Username: ubuntu

Domain eu-west-1.compute.internal

Password: S@nta2022

Successfully logged in and retrieved flag:
{THM_SANTA_SMB_SERVER}
Also retrieved user list containing passwords:

<table>
  <thead>
    <tr>
      <th>USERNAME</th>
      <th>PASSWORD</th>
    </tr>
  </thead>
  <tfoot>
    <tr>
      <td>santa</td>
      <td>santa101</td>
    </tr>
  </tfoot>
  <tbody>
    <tr>
      <td>santahr</td>
      <td>santa25</td>
    </tr>
    <tr>
      <td>santaciso</td>
      <td>santa30</td>
    </tr>
    <tr>
      <td>santatech</td>
      <td>santa200</td>
    </tr>
    <tr>
      <td>santaaccounts</td>
      <td>santa400</td>
    </tr>
  </tbody>
</table>


