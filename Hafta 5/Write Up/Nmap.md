# Nmap Switches 

<h3>What is the first switch listed in the help menu for a 'Syn Scan' (more on this later!)?


<h5>-sS

------------------------------------

<h3>Which switch would you use for a "UDP scan"?


<h5>-sU

------------------------------------
<h3>If you wanted to detect which operating system the target is running on, which switch would you use?


<h5>-O

------------------------------------

<h3>Nmap provides a switch to detect the version of the services running on the target. What is this switch?


<h5>-sV

------------------------------------
<h3>The default output provided by nmap often does not provide enough information for a pentester. How would you increase the verbosity?


<h5>-v

------------------------------------

<h3>Verbosity level one is good, but verbosity level two is better! How would you set the verbosity level to two?
(Note: it's highly advisable to always use at least this option)


<h5>-vv

------------------------------------
<h3>We should always save the output of our scans -- this means that we only need to run the scan once (reducing network traffic and thus chance of detection), and gives us a reference to use when writing reports for clients.

What switch would you use to save the nmap results in three major formats?


<h5>-oA

------------------------------------

<h3>What switch would you use to save the nmap results in a "normal" format?


<h5>-oN

------------------------------------

<h3>Sometimes the results we're getting just aren't enough. If we don't care about how loud we are, we can enable "aggressive" mode. This is a shorthand switch that activates service detection, operating system detection, a traceroute and common script scanning.

How would you activate this setting?

<h5>-A

------------------------------------

<h3>Nmap offers five levels of "timing" template. These are essentially used to increase the speed your scan runs at. Be careful though: higher speeds are noisier, and can incur errors!

How would you set the timing template to level 5?


<h5>-T5

------------------------------------
<h3>

We can also choose which port(s) to scan.

How would you tell nmap to only scan port 80?


<h5>-p 80

------------------------------------

<h3>How would you tell nmap to scan ports 1000-1500?


<h5>-p 1000-1500

------------------------------------
<h3>A very useful option that should not be ignored:

How would you tell nmap to scan all ports?


<h5>-p-

------------------------------------

<h3>How would you activate a script from the nmap scripting library (lots more on this later!)?


<h5>--script

------------------------------------
<h3>How would you activate all of the scripts in the "vuln" category?


<h5>--script=vuln



# TCP Connect Scans 

------------------------------------

<h3>Which RFC defines the appropriate behaviour for the TCP protocol?


<h5>RFC 793

------------------------------------



<h3>If a port is closed, which flag should the server send back to indicate this?


<h5>RST

------------------------------------

# SYN Scans

<h3>There are two other names for a SYN scan, what are they?

<h5>Half-Open, Stealth

--------------------------------------------------


<h3>Can Nmap use a SYN scan without Sudo permissions (Y/N)?

<h5>N

--------------------------------------------------


# UDP Scans 

<h3>If a UDP port doesn't respond to an Nmap scan, what will it be marked as?

<h5>open|filtered

--------------------------------------------------

<h3>When a UDP port is closed, by convention the target should send back a "port unreachable" message. Which protocol would it use to do so?

<h5>ICMP

--------------------------------------------------

# NULL, FIN and Xmas 

<h3>Which of the three shown scan types uses the URG flag?

<h5>xmas

--------------------------------------------------


<h3>Why are NULL, FIN and Xmas scans generally used?

<h5>Firewall Evasion

--------------------------------------------------


<h3>Which common OS may respond to a NULL, FIN or Xmas scan with a RST for every port?

<h5>Microsoft Windows

--------------------------------------------------
# ICMP Network Scanning 

<h3>How would you perform a ping sweep on the 172.16.x.x network (Netmask: 255.255.0.0) using Nmap? (CIDR notation)

<h5>nmap -sn 172.16.0.0/16
--------------------------------------------------

# NSE Scripts Overview 

<h3>What language are NSE scripts written in?

<h5>Lua

--------------------------------------------------

<h3>Which category of scripts would be a very bad idea to run in a production environment?

<h5>intrusive

--------------------------------------------------

<h3>What optional argument can the ftp-anon.nse script take?

<h5>maxlist

--------------------------------------------------

# Firewall Evasion

<h3>Which simple (and frequently relied upon) protocol is often blocked, requiring the use of the -Pn switch?

<h5>ICMP

--------------------------------------------------

<h3>[Research] Which Nmap switch allows you to append an arbitrary length of random data to the end of packets?

<h5>--data-length

--------------------------------------------------






