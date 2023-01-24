---
weight: 13
title: "Linux"
date: 2023-01-19
lastmod: 2023-01-19
draft: true
author: "Jose Benitez"
description: "Cool Linux commands"
images: []
resources:
- name: "featured-image"
  src: "linux.jpg"

tags: ["Linux"]
categories: ["Educational"]
lightgallery: true
---

## Commands
  1) **w**  = Shows the users logged into that machine.
  2) **uptime** = shows you how long the system has been running
  3) **ps** = shows a list of running processes in the machine
  4) **whoami** = returns name of user
  5) **whois** { ipv4 or DNS } = queries information about specified host 
  6) **dig** = queries the DNS (phonebook of the internet)
     - dig -x {ip.address}: does the opposite (shows you the name of the ip if one exists)
  7) **top** = dynamically shows a list of current processes
     - PID = process id
     - VIRT = virtual size
     - RES  = amount of resident memory being used by a process in KB 
     - S = shows the states like (R=running, Z=zombie, D=doing I/O)

  8) **ping** = small program that uses ICMP echo request/echo reply messages to test wheter a destination is reachable. sends a small packet 

