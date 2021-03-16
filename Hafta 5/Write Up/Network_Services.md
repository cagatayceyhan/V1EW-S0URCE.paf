
# Network Services
----------------------------

## Understanding SMB 

-----------------------
<h3>What does SMB stand for?    

<h5>Server Message Block

--------------------------------

<h3>What type of protocol is SMB?    

<h5>response-request

--------------------------------

<h3>What do clients connect to servers using?    

<h5>TCP/IP

--------------------------------

<h3>What systems does Samba run on?

<h5>Unix

--------------------------------

# SMB

<h3>Conduct an nmap scan of your choosing, How many ports are open?

<h5>3

![](https://raw.githubusercontent.com/cagatayceyhan/terminal_Img/main/SMB1.PNG)

------------------------------------

<h3>What ports is SMB running on?


<h5>139/445

![](https://raw.githubusercontent.com/cagatayceyhan/terminal_Img/main/SMB2.PNG)

------------------------------------

<h3>Let's get started with Enum4Linux, conduct a full basic enumeration. For starters, what is the workgroup name?    

<h5>WORKGROUP

![](https://raw.githubusercontent.com/cagatayceyhan/terminal_Img/main/SMB3.PNG)

------------------------------------

<h3>What comes up as the name of the machine?        

<h5>POLOSMB

![](https://raw.githubusercontent.com/cagatayceyhan/terminal_Img/main/SMB4.PNG)

------------------------------------


<h3>What operating system version is running?   

<h5>6.1

![](https://raw.githubusercontent.com/cagatayceyhan/terminal_Img/main/SMB5.PNG)

------------------------------------

<h3>What share sticks out as something we might want to investigate?    

<h5>profiles

![]()

------------------------------------

<h3> What would be the correct syntax to access an SMB share called "secret" as user "suit" on a machine with the IP 10.10.10.2 on the default port?

<h5>smbclient //10.10.10.2/secret -U suit -p 445

![](https://raw.githubusercontent.com/cagatayceyhan/terminal_Img/main/SMB6.PNG)

------------------------------------

<h3>Lets see if our interesting share has been configured to allow anonymous access, I.E it doesn't require authentication to view the files. We can do this easily by:

- using the username "Anonymous"

- connecting to the share we found during the enumeration stage

- and not supplying a password.

Does the share allow anonymous access? Y/N?

<h5>Y

![]()

------------------------------------

<h3>Great! Have a look around for any interesting documents that could contain valuable information. Who can we assume this profile folder belongs to? 

<h5>John Cactus
  
![](https://raw.githubusercontent.com/cagatayceyhan/terminal_Img/main/SMB7.PNG)

------------------------------------

<h3>What service has been configured to allow him to work from home?

<h5>ssh


------------------------------------


<h3>Okay! Now we know this, what directory on the share should we look in?

<h5>.ssh

![](https://raw.githubusercontent.com/cagatayceyhan/terminal_Img/main/SMB9.PNG)


------------------------------------

<h3>This directory contains authentication keys that allow a user to authenticate themselves on, and then access, a server. Which of these keys is most useful to us?

<h5>id_rsa

![](https://raw.githubusercontent.com/cagatayceyhan/terminal_Img/main/SMB10.PNG)


------------------------------------


<h3>

Download this file to your local machine, and change the permissions to "600" using "chmod 600 [file]".

Now, use the information you have already gathered to work out the username of the account. Then, use the service and key to log-in to the server.

What is the smb.txt flag?

<h5>THM{smb_is_fun_eh?}

![](https://raw.githubusercontent.com/cagatayceyhan/terminal_Img/main/SMB14.PNG)


------------------------------------
#  Understanding FTP 

<h3>What communications model does FTP use?

<h5>client-server

![]()

------------------------------------



<h3>What's the standard FTP port?

<h5>21

![]()

------------------------------------


<h3>How many modes of FTP connection are there?    

<h5>2

![]()

------------------------------------

# Enumerating FTP 

<h3>Run an nmap scan of your choice.

How many ports are open on the target machine?  

<h5>2

![](https://raw.githubusercontent.com/cagatayceyhan/terminal_Img/main/FTP1.PNG)

------------------------------------



<h3>What port is ftp running on?

<h5>21

![]1(https://raw.githubusercontent.com/cagatayceyhan/terminal_Img/main/FTP2.PNG)

------------------------------------



<h3>What variant of FTP is running on it?   

<h5>vsftpd

![](https://raw.githubusercontent.com/cagatayceyhan/terminal_Img/main/FTP3.PNG)

------------------------------------



<h3>Great, now we know what type of FTP server we're dealing with we can check to see if we are able to login anonymously to the FTP server. We can do this using by typing "ftp [IP]" into the console, and entering "anonymous", and no password when prompted.

What is the name of the file in the anonymous FTP directory?

<h5>PUBLIC_NOTICE.txt

![](https://raw.githubusercontent.com/cagatayceyhan/terminal_Img/main/FTP4.PNG)

------------------------------------



<h3>What do we think a possible username
could be?

<h5>mike

![]()

------------------------------------



<h3>What is the password for the user "mike"?

<h5>password

![](https://raw.githubusercontent.com/cagatayceyhan/terminal_Img/main/FTP5.PNG))

------------------------------------

# Exploiting FTP 

<h3>What is ftp.txt?

<h5>THM{y0u_g0t_th3_ftp_fl4g}

![](https://raw.githubusercontent.com/cagatayceyhan/terminal_Img/main/FTP6.PNG)

------------------------------------


