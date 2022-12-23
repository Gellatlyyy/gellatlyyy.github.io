---
date: 2022-12-03T01:00:00.000Z
layout: post
title: Advent of Cyber - Day 3
subtitle: TryHackMe Advent of Cyber 2022 - Day 3.
description: A writeup of Day 3 - TryHackMe Advent of Cyber 2022 Challenge.
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
What is OSINT, and what techniques can extract useful information against a website or target?
Using dorks to find specific information on the Google search engine
Extracting hidden directories through the Robots.txt file
Domain owner information through WHOIS lookup
Searching data from hacked databases
Acquiring sensitive information from publicly available GitHub repositories


1.	**What is the name of the Registrar for the domain santagift.shop?**

To find this information, you can do a simple whois lookup to find information about the domain.

Namecheap, Inc.


2.	**Find the website's source code (repository) on github.com and open the file containing sensitive credentials. Can you find the flag?**

Simply by searching santagiftshop in the search field, the source code can be found.
Rather than searching through all of the files, I utilized Google dorks to find anything referencing “password” with the search term:
site:https://github.com/muhammadthm/SantaGiftShop "password"
The first result took me to the config.php page where the flag was found.
**$FLAG = '{THM_OSINT_WORKS}';**

From here, the rest of the tasks can be completed with the information that was located in the config.php page.

![img1](https://drive.google.com/uc?id=1RT5szL_OXFtwL_fPzmKC05ndMT4V2FOK)