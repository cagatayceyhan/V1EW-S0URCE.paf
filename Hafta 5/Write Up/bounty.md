# Bounty Hacker WriteUp

## Makineye vpn ile bağlandıktan sonra ilk olarak hedef sistem üzerinde Nmap taraması gerçekleştirip açık portları tespit ediyoruz.

![](https://raw.githubusercontent.com/cagatayceyhan/terminal_Img/main/b1.PNG)

**nmap çıktısın 3 portun açık olduğunu görüyoruz.**

**21/ftp- vsftpd 3.0.3 (Anonymous FTP login allowed) /Anonim bağlantıya izin veriyor.**
**22/ssh- OpenSSH 7.2p2**
**80/http- Apache/2.4.18**

21 portunun anonim bağlantıya açık olduğunu biliyoruz.Bu bilgiyi kullanarak 21 portu üzerinden anonymous kullanıcı adı ve parolasıyla 21 portuna ftp üzerinden yürüyebiliriz.

![](https://raw.githubusercontent.com/cagatayceyhan/terminal_Img/main/b2.PNG)


FTP bağlantısı başarılı oldu. ls komutu ile dizindeki dosyaları listeliyoruz.

![](https://raw.githubusercontent.com/cagatayceyhan/terminal_Img/main/b3.PNG)

Sorgu sonucu iki dosya olduğunu görüyoruz.Bunlar locks.txt ve task.txt dosyaları bunların içerisinde ne olduğunu görmemiz için **get** komutu ile dosyaları kendi makinemize çekiyoruz.

![](https://raw.githubusercontent.com/cagatayceyhan/terminal_Img/main/b4.PNG)

**locks.txt içeriği**

![](https://raw.githubusercontent.com/cagatayceyhan/terminal_Img/main/b5.PNG)

locks.txt dosyasının içerisinden parola listesi çıkıyor.İlerleyen adımlarda brute force işlemi için kullanabileceğimiz bir wordlist olabilir.

**task.txt içeriği**

![](https://raw.githubusercontent.com/cagatayceyhan/terminal_Img/main/b6.PNG)

Burada karşımıza **lin** kullanıcısının bıraktığı not karşımıza çıkıyor.Burada açık olan 22 portuna deneme yapmamız için tüm koşullar kullanıcı adı ve porola listesi ile sağlanmış durumda hydra ile Brute Force denemesi yapacağız.


**hydra ssh://10.10.76.95 -l lin -P /home/kali/lock.txt** komutuyla hydra üzerinden bruteforce atıyoruz.

![](https://raw.githubusercontent.com/cagatayceyhan/terminal_Img/main/b7.PNG)

hydra ile kullanıcı adı ve parolayı öğrendikten sonra ssh üzerinden giriş yapıyoruz

![](https://raw.githubusercontent.com/cagatayceyhan/terminal_Img/main/b8.PNG)

giriş yaptık ls komutu ile listeleme yaptıktan sonra cat user.txt içeriğine bakıyoruz.

![](https://raw.githubusercontent.com/cagatayceyhan/terminal_Img/main/b9.PNG)

## Privilege Escalation / Yetki Yükseltme

İlk olarak root yekisine erişmemiz gerekiyor.Kullanıcının root olarak ne çalıştırabileceğini görmek için **sudo -l** komutunu kullanıyoruz.

![](https://raw.githubusercontent.com/cagatayceyhan/terminal_Img/main/b10.PNG)

tar'ı root olarak çalıştırabileceğimiz gözüküyor.Tar üzerinde hak yükseltme işlemleri için GTFO bins üzerinde bulunan yetki yükseltme kodlarına bakabiliriz.

![](https://raw.githubusercontent.com/cagatayceyhan/terminal_Img/main/b11.PNG)

**Yetki Yükseltmeyi 
sudo tar -cf /dev/null /dev/null --checkpoint=1 --checkpoint-action=exec=/bin/sh
 komutu ile sağlıyoruz.**

ve root yetkisini alıp bayrağa ulaşıyoruz.

![](https://raw.githubusercontent.com/cagatayceyhan/terminal_Img/main/b12.PNG)




