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

## CLI Commands
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
     - ping -Rsv <hostname> = forms record of actual route travelled by query and reply
  9) **traceroute** google.com= basically pings every server in the route to your host address
  10) **which** = shows the full path of (shell) commands.
    - which gcc for exmample shows the path to the gcc compiler for running C/C++ programs  
  11) **poink** = network security tool that uses the ARP (Address Resolution Protocol) protocol to perform various tasks such as network mapping, service discovery, and vulnerability assessment.
   - ARP is a protocol used to map an IP address to a physical (MAC) address on a network.-  
## System Calls
- System calls are executed by kernel of the Operating System. User-space programs can invoke these calls such as those written in C.  More details about these tools can be found by executing 
   ```bash 
      man 2 <system call>
   ```
  1) **open** = returns a file descriptor (int). Kind of like you need to open a book before you can actually read it
     ```c
          int source = open(argv[1], O_RDONLY);
          int target = open(argv[2], O_WRONLY);
     ```
  2) **read** = returns the number of bytes read
     ```c
          char buffer[4096];
          int bytes_read = read(source, buffer, sizeof(buffer));
     ```
  3) **write** = returns the number of bytes written to an output file
     ```c
          char buffer[4096];
          int bytes_written = write(target, buffer, bytes_read);
     ```
  4) **close** = close files opened previously
       ```c
            close(source);
            close(target);
       ```
  5) **mkdir** = to create a directory in C first specify output file path and then specify the file permissions.
      ```c
            int rc = mkdir(output, 511);
            if (rc == -1)
            {
                  printf("Unable to create directory.");
                  exit(1);
            }

      ```