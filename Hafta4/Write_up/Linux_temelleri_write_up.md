# Linux Challenges

## Görev 1 | The Basics

**What is flag 1?**

flag1'i bulmak için bulunduğumuz dizinde ls komutu ile listeleme yapıyoruz daha sonra çıkan sonuçta cat flag1.txt dosyasını açıp flag'i alıyoruz.

![](https://raw.githubusercontent.com/cagatayceyhan/terminal_Img/main/1.PNG)

-----------------------------------------------------------------------------------------------

**What is flag 2?**
flag2'yi bulmak için dizinler arası dolaşıyoruz.bob dizini içerisine girdiğimizde ls ile listeleme yapıyoruz.Listeleme sonucu flag2 ye ulaşıyoruz cat flag2.txt açıp içerisinden flag 2 yi alıyoruz.

![](https://raw.githubusercontent.com/cagatayceyhan/terminal_Img/main/2.PNG)

-------------------------------------------------------------------------------------------------

Flag 3 is located where bob's bash history gets stored.


**Flag 3 is located where bob's bash history gets stored.**

bob dizini altında ls-lah komutunu kullanarak detaylı şekilde listeleme yapıyoruz çıkan sonuçta cat .bash_history komutunu çalıştırıp flag3'e ulaşıyoruz.

![](https://raw.githubusercontent.com/cagatayceyhan/terminal_Img/main/3.PNG)

**Flag 4 is located where cron jobs are created.**

Crontab'a ulaşmak için bob kullanıcısına su komutu ile geçiyoruz.Geçtikten sonra locate komutu ile crontabs konumunu arıyoruz.çıkan sonuçtaki yola cd komutu ile gidiyoruz akabinde crontab -l komutu ile içeriden flagi alıyoruz.

![](https://raw.githubusercontent.com/cagatayceyhan/terminal_Img/main/4.PNG)

**Find and retrieve flag 5.**

İlk olarak locate flag5.txt dosyasının konumunu öğrenmek için locate komutunu kullanıyoruz akabinde locake komutunun çıkardığı sonuçtaki yola gidiyoruz.cat komutu ile flag5.txt komutunun içindeki flag değerini alıyoruz.

![](https://raw.githubusercontent.com/cagatayceyhan/terminal_Img/main/5.PNG)



**"Grep" through flag 6 and find the flag. The first 2 characters of the flag is c9.**

home dizini gidiyoruz ls komutu ile listeleme yapıyoruz.listeleme sonucu flag6.txt bu dizinde olduğunu görüyoruz.soruda belirtilmesi üzerine flag içerisinde c9 ifadesi geçtiğini biliyoruz bu yüzden grep ile c9 ifadesi geçen değeri arıyoruz ve flagi buluyoruz.

![](https://raw.githubusercontent.com/cagatayceyhan/terminal_Img/main/6.PNG)

**Look at the systems processes. What is flag 7.**

7 numaralı flagin  süreçlerde olduğunu biliyoruz bu yüzden ps aux komutu ile flage ulaşıyoruz.

![](https://raw.githubusercontent.com/cagatayceyhan/terminal_Img/main/7.PNG)

**De-compress and get flag 8.**

locate komutu ile flag8 konumunu öğreniyoruz.komutun bob dizini altında olduğunu öğreniyoruz.çıkarma işlemi yapmamız için öncelikle bob kullanıcısına geçmemiz gerekli bunun için su komutu ile bob kullanıcasına geçiyoruz.su komutu ile bob kullanıcısına geçtikten sonrta bob dizinine gidiyoruz.bob dizininde ls komutu ile sorgulama yapıyoruz.flsg8.tar.gz dosyası bizi karşılıyor.
daha sonra tar -xf flag8.tar.gz komutunu kullanıyoruz.sonra çıkartılan dosyadan cat komutu ile flagi okuyoruz.

![](https://raw.githubusercontent.com/cagatayceyhan/terminal_Img/main/8.PNG)



**By look in your hosts file, locate and retrieve flag 9.**

burada host dosyasına bakmamızı istiyor.etc altındaki host bilgilerini kontrol ediyoruz.

![](https://raw.githubusercontent.com/cagatayceyhan/terminal_Img/main/9.PNG)

**Find all other users on the system. What is flag 10.**

Sistemdeki tüm kullanıcıları bulmamızı istiyor bunun için linuxda kullanıcıların bilgilerinin olduğu passwd dosyasını incelememiz ve flagı bulmamız gerekiyor. cat /etc/passwd komutunu kullanıyoruz.

![](https://raw.githubusercontent.com/cagatayceyhan/terminal_Img/main/10.PNG)

# Görev 2 | Linux Functionality

**Run the command flag11. Locate where your command alias are stored and get flag 11.**

Bash takma adı, Bash komutlarını yenileriyle tamamlama veya geçersiz kılma yöntemidir.Bu yüzden .bashrc veya bash_aliases dosyalarının altında toplanır.bu yüzden home dizini altında tedaylı listeleme yapmamız gerek bunun içen ls -lah komutunu kullanıyoruz.çıkan listeleme sonucunda .basrc dosyasını görüyoruz.Komut satırında cat ile okuma yapıyoruz ve flage ulaşıyoruz.

![](https://raw.githubusercontent.com/cagatayceyhan/terminal_Img/main/11.PNG)

**Flag12 is located were MOTD's are usually found on an Ubuntu OS. What is flag12?**

Motd, tüm kullanıcılara bir e-posta mesajı göndermekten daha verimli bir şekilde ortak bir mesaj göndermek için kullanılan, “günün mesajını” içeren Unix benzeri sistemlerdeki bir dosyadır.bu dosya /etc/update-moth.d konumunda saklanır.update-motd.d dizinine girdiğimizde ilk kontrol edeceğimiz yer header konumudur.header konumunu cat ile içeriğini görüntülüyoruz.header görüntülememiz sonucunda burada flag12 görüyoruz.

![](https://raw.githubusercontent.com/cagatayceyhan/terminal_Img/main/12.PNG)



**Find the difference between two script files to find flag 13.**

Burada yapmamız gereken adımlar flag13 dosyasını bulmak.flag13 dosyasını bulduktan sonra karşımıza iki adet script çıkıyor.diff komutunu kullanarak iki dosya arasındaki farkları çıkartıyoruz ve flag13 bizi karşılıyor.

![](https://raw.githubusercontent.com/cagatayceyhan/terminal_Img/main/13.PNG)

**Where on the file system are logs typically stored? Find flag 14.**

Burada log kayıtlarının tutulduğu yeri incelememiz gerekiyor.log kayıtları var dizini altında toplanır buyuzden var/log dizinini kontrol etmemiz gerek.ls komutunu kullanarak listeleme yapıyoruz.Karşımıza flagtourteen.txt dosyası çıkıyor.Burada flag dosyasını buluyoruz.

![](https://raw.githubusercontent.com/cagatayceyhan/terminal_Img/main/14.PNG)


**Can you find information about the system, such as the kernel version etc.**

Burada kernel version yani çekirdek versiyonunu bulmamızı istiyor.Çekirdek versiyonumuz etc dizini altında release dosyası altında bulunur.Flagin burada olduğunu biliyoruz.flage ulaşmak için cat /etc/*release komutunu kullanıyoruz.flag15 burada buluyoruz.

![](https://raw.githubusercontent.com/cagatayceyhan/terminal_Img/main/15.PNG)

**Flag 16 lies within another system mount.**

Burada sistem bağlantılarını kontrol etmemiz gerekiyor.Bunun için media dizinine gidiyoruz.
media dizinine gittikten sonra burada bizi f/l/a/g/1/6/is adlı sıralı dizinler karşılıyor is dizini altında flag ulaşıyoruz.

![](https://raw.githubusercontent.com/cagatayceyhan/terminal_Img/main/16.PNG)

**Login to alice's account and get flag 17. Her password is TryHackMe123**

Burada bizden alice kullanıcısı olmamızı ve alice dizini altındaki flag17'nin içindeki bayrağı almamızı istiyor.Alice dizini altındaki flag17 cat komutu ile açıp flag alıyoruz.

![](https://raw.githubusercontent.com/cagatayceyhan/terminal_Img/main/17.PNG)




**Find the hidden flag 18.**

Burada bizden flag18 bulmamızı istiyor.ilk olarak locate komutunu kullanarak flag18 konumunu öğreniyoruz.flag18 gizli dosya olduğunu öğreniyoruz ardından ls -lah komutu ile dosyayı buluyoruz cat .flag18 komutunu kullanarak flag'e ulaşıyıoruz.

![](https://raw.githubusercontent.com/cagatayceyhan/terminal_Img/main/18.PNG)


**Read the 2345th line of the file that contains flag 19.**

Burada flag19 içerisinde bulunan 2345.satırda bulunan flagi almamızı istiyor.sed komutunu kullanarak bayrağa erişiyoruz.

![](https://raw.githubusercontent.com/cagatayceyhan/terminal_Img/main/19.PNG)

# Görev 3 | Data Representation, Strings and Permissions

**Find and retrieve flag 20.**

İlk olarak flag20 cat ile okutuyoruz.Okuttuğumuzda base64 kodlu bir metin bizi karşılıyor.Burada base64 decode tekniğini kullanarak flagi alıyoruz.

![](https://raw.githubusercontent.com/cagatayceyhan/terminal_Img/main/20.PNG)

**Inspect the flag21.php file. Find the flag.**
Php uzantılı flag21 dosyasını bulmak için locate komutunu kullanıyoruz.flagın yerini tespit ettikten sonra cat komutuyla okumaya çalışıyoruz ancak bayrağı göstermiyor.Bayrağın tam içeriğini görmek için less komutunu kullanıyoruz ve bayrağı elde ediyoruz.

![](https://raw.githubusercontent.com/cagatayceyhan/terminal_Img/main/21%20%20.PNG)

**Locate and read flag 22. Its represented as hex.**

İlk olarak flag22 locate komutu ile konumu buluyoruz.Daha sonra cat ile flag22 dosyasının içeriğini açıyoruz.bayrağın içerisinde hex kodu gizlenmiş.hex kodunu ascii koda ceviriyoruz ve bayrağa ulaşıyoruz.

![](https://raw.githubusercontent.com/cagatayceyhan/terminal_Img/main/22.1.PNG)

![](https://raw.githubusercontent.com/cagatayceyhan/terminal_Img/main/22.2.PNG)



**Locate, read and reverse flag 23.**

Burada flag23 ulaşıp içeriği tersten alarak bayrağa ulaşabileceğimiz söyleniyor.rev komutu ile flag23 içeriğini tersten alıyoruz.

![](https://raw.githubusercontent.com/cagatayceyhan/terminal_Img/main/23.PNG)

**Analyse the flag 24 compiled C program. Find a command that might reveal human readable strings when looking in the machine code code.**

Burada c kodunu insalar tarafından okunur halde analiz etmemiz gerektiğini söylüyor.su komutu ile gerry kullanıcısına geçiyoruz ardından gerry dizini altındaki flag24 strings komutu ile okunabilir hale getiriyoruz ve flag karşımıza çıkıyor.

![](https://raw.githubusercontent.com/cagatayceyhan/terminal_Img/main/24.PNG)

**25.BAYRAK İPTAL EDİLMİŞ**

**Find flag 26 by searching the all files for a string that begins with 4bceb and is 32 characters long.**

Burada komutunu kullanarak istenilen flagi buluyoruz. find / -xdev -type f -print0 2>/dev/null | xargs -0 grep -E [a-z0–9]{32} 2>/dev/null

**Locate and retrieve flag 27, which is owned by the root user.**

locate komutu ile bayrağın konumunu öğreniyoruz.Öğrendikten sonra sudo yetkisi alıyoruz. sudo cat /home/flag27 ile bayrağı açıyoruz.

![](https://raw.githubusercontent.com/cagatayceyhan/terminal_Img/main/27.PNG)

**Whats the linux kernel version?** 

burada kullandığımız linux distrosunun kernel versiöyonunu bizden istiyor.yapmamız gereken uname -a komutunu kullanarak tüm çekirdek bilgisini almak.

![](https://raw.githubusercontent.com/cagatayceyhan/terminal_Img/main/28.PNG)



**Find the file called flag 29 and do the following operations on it:**

* Remove all spaces in file.
* Remove all new line spaces.
* Split by comma and get the last element in the split.

Burada cat /home/garry/flag29 | tr -d " \n" komutunu kullanarak bayrağı elde ediyoruz.

![](https://raw.githubusercontent.com/cagatayceyhan/terminal_Img/main/29.PNG)

# Görev 4 | SQL, FTP, Groups and RDP

**Use curl to find flag 30.** 

Burada curl ile veri çekmemizi istiyor.ilk olarak ifconfig ile ip adresimizi öğreniyoruz.Daha sonra curl ile veriyi çekiyoruz.

![](https://raw.githubusercontent.com/cagatayceyhan/terminal_Img/main/30.PNG)


Flag 31 is a MySQL database name.

MySQL username: root
MySQL password: hello


Burada ilk yapmamız gereken mysql sunucusuna bağlanmak terminal üzerinden mysql -u root -p komutunu giriyoruz ardından parola ekranı geliyor.mysql'e bağlandıktan sonra ilk olarak databaseleri kontrol ediyoruz akabinde flagimizin olduğu database seçiyoruz ve tabloyu açtığımızda  bayrağa ulaşmış oluyoruz.

![](https://raw.githubusercontent.com/cagatayceyhan/terminal_Img/main/31.PNG)




**32 flag question, get data out of the table from the database you found above!**

Burada veri tabanından veri çekmemizi istiyor.SELECT * FROM flags komutunu girerek flag içeriğine ulaşıyoruz.

![](https://raw.githubusercontent.com/cagatayceyhan/terminal_Img/main/32.PNG)

**Flag 33 is located where your personal PATH’s are stored**

Home dizinimiz altında detaylı ls sorgusu çekerek .profile dosyasına ulaşıyoruz cat ile içeriğine bakıyoruz ve bayrağı alıyoruz.

![](https://raw.githubusercontent.com/cagatayceyhan/terminal_Img/main/33.PNG)

**Switch your account back to bob. Using system variables, what is flag34?**

İlk olarak su komutu ile bob kullanıcısına geçiyoruz ardından printenv komutu ile bayrağı env içerisinden alıyoruz.

![](https://github.com/cagatayceyhan/terminal_Img/blob/main/34.PNG)

**Look at all groups created on the system. What is flag 35?**

flag35 içindeki bayrağı getent group | grep flag35 komutu ile buluruz.

![](https://raw.githubusercontent.com/cagatayceyhan/terminal_Img/main/35.PNG)



**Find the user which is apart of the "hacker" group and read flag 36.**

İlk olarak locate komutu ile flag36 nın adresini tespit ediyoruz.Daha sonra cat /home/flag36 komutu ile bayrağı elde ediyoruz.

![](https://raw.githubusercontent.com/cagatayceyhan/terminal_Img/main/36.PNG)






