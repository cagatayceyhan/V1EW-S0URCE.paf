# Introductory Networking

## The OSI Model: An Overview 

![](https://muirlandoracle.co.uk/wp-content/uploads/2020/02/OSI-Table.png)

<h3> Which layer would choose to send data over TCP or UDP?

<H4> 4.Katman

--------------------------------
<h3> Which layer checks received packets to make sure that they haven't been corrupted?

<h4> 2.Katman
-------------------------
<h3> In which layer would data be formatted in preparation for transmission?

<h4> 2.Katman

---------------------

<h3> Which layer transmits and receives data?

<h4> 1.Katman

--------------------------------------

<h3> Which layer encrypts, compresses, or otherwise transforms the initial data to give it a standardised format?

<h4> 6.Katman

----------------------------------------

<h3> Which layer tracks communications between the host and receiving computers?

<h4> 5.Katman
-------------------------

<h3> Which layer accepts communication requests from applications?

<h4> 7.Katman

-----------------------------------

<h3> Which layer handles logical addressing?

<h4> 3.Katman

-----------------------------------------------------------

<h3> When sending data over TCP, what would you call the "bite-sized" pieces of data? 

<h4> Segments

-------------------------------------

<h3> [Research] Which layer would the FTP protocol communicate with?

<h4> 7.Katman

-----------------------------------

<h3> Which transport layer protocol would be best suited to transmit a live video?

<h4> UDP Protokolü 

----------------------------------------------

# Encapsulation 

![](https://muirlandoracle.co.uk/wp-content/uploads/2020/02/image.jpeg)

<h3> How would you refer to data at layer 2 of the encapsulation process (with the OSI model)?

<h4> Frames

-----------------------------------------

<h3> How would you refer to data at layer 4 of the encapsulation process (with the OSI model), if the UDP protocol has been selected?

<h4> Datagrams

-----------------------------------

<h3> What process would a computer perform on a received message?

<h4> De-encapsulation

-------------------------------------------------

<h3> Which is the only layer of the OSI model to add a trailer during encapsulation?

<h4> Data Link

-------------------------------------

<h3> Does encapsulation provide an extra layer of security (Aye/Nay)?

<h4> Aye/Yes

---------------------------------------------

# The TCP/IP Model 

![](https://muirlandoracle.co.uk/wp-content/uploads/2020/02/image-3.png)

<h3>Which model was introduced first, OSI or TCP/IP?


<h4>TCP/IP

-------------------------------

<h3>Which layer of the TCP/IP model covers the functionality of the Transport layer of the OSI model (Full Name)?

<h4>Transport

-----------------------------

<h3>Which layer of the TCP/IP model covers the functionality of the Session layer of the OSI model (Full Name)?

<h4>Application

-------------------------------

<h3>The Network Interface layer of the TCP/IP model covers the functionality of two layers in the OSI model. These layers are Data Link, and?.. (Full Name)?

<h4>Physical

-----------------------------

<h3>Which layer of the TCP/IP model handles the functionality of the OSI network layer?

<h4>Internet

-------------------------------

<h3>What kind of protocol is TCP?

<h4>Connection-based

-----------------------------

<h3>What is SYN short for?

<h4>Synchronise

-------------------------------

<h3>What is the second step of the three way handshake?


<h4>SYN/ACK

-----------------------------

<h3>What is the short name for the "Acknowledgement" segment in the three-way handshake?


<h4>ACK

-----------------------------

<h3>What command would you use to ping the bbc.co.uk website?


<h4>ping bbc.co.uk

----------------------------

<h3>Ping muirlandoracle.co.uk
What is the IPv4 address?

<h4>217.160.0.152

![](https://raw.githubusercontent.com/cagatayceyhan/terminal_Img/main/1n.PNG)

----------------------------

<h3>What switch lets you change the interval of sent ping requests?

<h4>-i

----------------------------

<h3>What switch would allow you to restrict requests to IPv4?

<h4>-4

----------------------------

<h3>What switch would give you a more verbose output?

<h4>-v

----------------------------

# Traceroute 

<h3>What switch would you use to specify an interface when using Traceroute?

<h4>-i

---------------------------

<h3>What switch would you use if you wanted to use TCP SYN requests when tracing the route?

<h4>-T

---------------------------

<h3>[Lateral Thinking] Which layer of the TCP/IP model will traceroute run on by default (Windows)?


<h4>Internet

---------------------------

# WHOIS

<h3>What is the registrant postal code for facebook.com?


<h5>94025

![](https://raw.githubusercontent.com/cagatayceyhan/terminal_Img/main/whois1.PNG)

------------------------------

<h3>When was the facebook.com domain first registered?


<h5>29/03/1997


![](https://raw.githubusercontent.com/cagatayceyhan/terminal_Img/main/whois2.PNG)

------------------------------

<h3>Which city is the registrant based in?


<h5>Redmond


![](https://raw.githubusercontent.com/cagatayceyhan/terminal_Img/main/whois3.PNG)

------------------------------

<h3>[OSINT] What is the name of the golf course that is near the registrant address for microsoft.com?


<h5>Bellevue Golf Course


![](https://raw.githubusercontent.com/cagatayceyhan/terminal_Img/main/whois4.PNG)

------------------------------

<h3>What is the registered Tech Email for microsoft.com?


<h5>msnhst@microsoft.com


![](https://raw.githubusercontent.com/cagatayceyhan/terminal_Img/main/whois5.PNG)

------------------------------

# Dig

<h3>What is DNS short for?


<h5>Domain Name System

--------------------------------------------

<h3>What is the first type of DNS server your computer would query when you search for a domain?


<h5>Recursive

--------------------------------------------

<h3>What type of DNS server contains records specific to domain extensions (i.e. .com, .co.uk*, etc)*? Use the long version of the name.


<h5>Top-Level Domain

--------------------------------------------
<h3> Where is the very first place your computer would look to find the IP address of a domain?


<h5> Local Cache

--------------------------------------------
<h3>[Research] Google runs two public DNS servers. One of them can be queried with the IP 8.8.8.8, what is the IP address of the other one?


<h5>8.8.4.4

--------------------------------------------
<h3>If a DNS query has a TTL of 24 hours, what number would the dig query show?


<h5>86400

--------------------------------------------

