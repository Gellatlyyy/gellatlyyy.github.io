---
date: 2022-12-06T01:00:00.000Z
layout: post
title: Advent of Cyber - Day 6
subtitle: TryHackMe Advent of Cyber 2022 - Day 6.
description: A writeup of Day 6 - TryHackMe Advent of Cyber 2022 Challenge.
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

•	Learn what email analysis is and why it still matters.

•	Learn the email header sections.

•	Learn the essential questions to ask in email analysis.

•	Learn how to use email header sections to evaluate an email.

•	Learn to use additional tools to discover email attachments and conduct further analysis.

•	Help the Elf team investigate the suspicious email received.


# Task 1:
**What is the email address of the sender?**

Connected to the attack box and located email.
Opened email with Sublime Text to view header information.

Sender (from): chief.elf@santaclaus.thm

Return address (reply to / return path): murphy.evident@bandityeti.thm

The following tasks can be completed with the heading information;
 
![img1](https://drive.google.com/uc?id=1Gtcb7YJd4UhNBWH_AXCd1Y90-KHJPzR_)

# Task 5: 
**What is hidden in the value of the Message-ID field?**

The message ID appears to be encoded with base64. Attempted to and view results via terminal:

![img1](https://drive.google.com/uc?id=1dwdwA9ntsmYEnYZkoerKeESE_PAY6bz8)
 
# Task 6: 
**Visit the email reputation check website provided in the task. What is the reputation result of the sender's email address?**

Firstly, I got the sha256 checksum on the file:

![img1](https://drive.google.com/uc?id=186LuPp4oqKk_VFGOaYP_w0wcbj58Q91i)
 
d60a5d9d88d6f9cee7dfa9ce0b14bc992c596838df71259016c5e7cda651ad48

Next, I searched the email reputation site as requested:
No results were found.

Tested the other suggested website – emailrep.io

Got results: RISKY


# Task 7: 
**What is the hash value of the attachment?**

First, the attachments will need to be extracted from the .eml.

emlAnalyzer -i Urgent\:.eml --header --html -u --text --extract-all

![img1](https://drive.google.com/uc?id=1CTxSXFhHyGwULMZQQvImaSWGc7yCaxIj)
 
Getting the sha256 checksum of the file:
 
![img1](https://drive.google.com/uc?id=1jQl44KdrCfr_gFoD5sqqROzgi9KCWIi_)

0827bb9a2e7c0628b82256759f0f888ca1abd6a2d903acdb8e44aca6a1a03467

The rest of the tasks can be completed by submitting the hash to VirusTotal and InQuest:

https://www.virustotal.com/gui/home/search

https://labs.inquest.net

![img1](https://drive.google.com/uc?id=1-Rs4dQ58GR4wE3jX3Im1sCZaGRC1qurm)

