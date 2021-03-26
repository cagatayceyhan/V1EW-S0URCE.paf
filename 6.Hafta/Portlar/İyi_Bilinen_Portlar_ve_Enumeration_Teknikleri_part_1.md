# İyi Bilinen Portlar ve Enumeration Teknikleri

## Port Nedir?
 
 Giriş, soket veya bağlantı noktası anlamında kullanılan bir bilgisayar terimidir. Fiziksel port ve sanal port (fiziksel olmayan) olarak ikiye ayrılır.

 Fiziksel port ile kastedilen bilgisayar bileşenlerinde bulunan ve fiziksel bağlantıda kullanılan bir donanım yuvasıdır. Bu tür portlar üzerinden bağlanmış herhangi bir makinaya veri gönderilebilir ve bu makinanın işleyişi kontrol edilebilir. Bir bilsayarda bulunan yaygın fiziksel portlara  AT Port, Firewire Port (IEEE-1394), Serial port, USB port, LAN veya Ağ Portu (RJ-45) vb. örnek verilebilir.

 Sanal port bilgisayar kullanırken ağ ve internet üzerinde veya bir yazılım vasıtasıyla yönlendirilen mantıksal bağlantı noktalarıdır. İnternet ortamında kullanılan port , sanal port diye açıkladığımız terimi ifade etmektedir. Bu soyut bağlantı noktarını adresleyebilmek için numaralar verilir. Bazı sunucular sabit port numrası kullanırken bazı sunucular ise farklı port adreslerinden hizmet verir. 1024’e kadar olan portlar özel portlarlardır, 1024’ün üzerinde ki port numaları ise genel kullanıma açıktır. Bu portlara telnet-23, http-80, ftp-21 portları örnek verilebilir.

 Ağ ortamındaki iletişimin ve veri alışverişinin sağlanması için sunucu programları tarafından bilgisayarlara IP adresleri verilir. Bu adresler kullanılarak ulaşılan bilgisayarda hizmet alınmak istenilen sunucu programı için port numaraları kullanılır. Bu nedenle ağ üzerindeki bir sunucu programa bağlanmak istenildiğinde bağlanılmak istenen IP numarasının yanına port numrası da eklenir.


 # İyi Bilinen Portlar

* 21 FTP
* 22 SSH
* 23 TELNET
* 25 SMTP
* 53 DNS
* 80 HTTP
* 110 POP3
* 115 SFTP
* 135 RPC
* 139 NetBIOS
* 143 IMAP
* 194 IRC
* 443 SSL
* 445 SMB
* 1433 MSSQL
* 3306 MySQL
* 3389 Remote Desktop

## FTP Enumeration

Dosya Aktarım Protokolü (FTP), bilgisayar dosyalarının bir bilgisayar ağındaki bir istemci ile sunucu arasında aktarımı için kullanılan standart bir ağ protokolüdür.

Yeni satır karakteri olarak 0x0d 0x0a kullanan bir düz metin protokolüdür, bu nedenle nc yerine telnet kullanarak bağlanmak önemlidir.

    Default Port: 21


    PORT   STATE SERVICE
    21/tcp open  ftp

## Enumeration

Banner Grabbing

    telnet -vn <IP> 21
    openssl s_client -connect crossfit.htb:21 -starttls ftp #Get certificate if any

   ##  Connect to FTP using starttls

    lftp
    lftp :~> set ftp:ssl-force true
    lftp :~> set ssl:verify-certificate no
    lftp :~> connect 10.10.10.208
    lftp 10.10.10.208:~> login                       
    Usage: login <user|URL> [<pass>]
    lftp 10.10.10.208:~> login username Password



## Unauth enum
FTP sunucusuyla ilgili bazı bilgileri almak için HELP ve FEAT komutlarını kullanabiliriz:

    HELP
    214-The following commands are recognized (* =>'s unimplemented):
    214-CWD     XCWD    CDUP    XCUP    SMNT*   QUIT    PORT    PASV    
    214-EPRT    EPSV    ALLO*   RNFR    RNTO    DELE    MDTM    RMD     
    214-XRMD    MKD     XMKD    PWD     XPWD    SIZE    SYST    HELP    
    214-NOOP    FEAT    OPTS    AUTH    CCC*    CONF*   ENC*    MIC*    
    214-PBSZ    PROT    TYPE    STRU    MODE    RETR    STOR    STOU    
    214-APPE    REST    ABOR    USER    PASS    ACCT*   REIN*   LIST    
    214-NLST    STAT    SITE    MLSD    MLST    
    214 Direct comments to root@drei.work
    FEAT
    211-Features:
    PROT
    CCC
    PBSZ
    AUTH TLS
    MFF modify;UNIX.group;UNIX.mode;
    REST STREAM
    MLST modify*;perm*;size*;type*;unique*;UNIX.group*;UNIX.mode*;UNIX.owner*;
    UTF8
    EPRT
    EPSV
    LANG en-US
    MDTM
    SSCN
    TVFS
    MFMT
    SIZE
    211 End

## Connections

Aktif FTP'de, FTP istemcisi ilk olarak N + 1 bağlantı noktasını dinler ve N + 1 bağlantı noktasını FTP Sunucusuna gönderir. FTP Sunucusu daha sonra M bağlantı noktasından FTP İstemcisinin N + 1 bağlantı noktasına veri bağlantısını başlatır.


Ancak, FTP İstemcisinin dışarıdan gelen veri bağlantılarını kontrol eden bir güvenlik duvarı kurulumu varsa, etkin FTP bir sorun olabilir. Ve bunun için uygun bir çözüm Pasif FTP'dir.

Pasif FTP'de, istemci N bağlantı noktasından FTP Sunucusunun 21 numaralı bağlantı noktasına kontrol bağlantısını başlatır. Bundan sonra, müşteri bir passv komutu verir. Sunucu daha sonra istemciye bağlantı noktası numarası M'den birini gönderir. İstemci, P bağlantı noktasından FTP Sunucusunun M bağlantı noktasına veri bağlantısını başlatır.

## Anonymous login

anonymous : anonymous
anonymous : 
ftp : ftp

    ftp <IP>
    >anonymous
    >anonymous
    >ls -a # List all files (even hidden) (yes, they could be hidden)
    >binary #Set transmission to binary instead of ascii
    >ascii #Set transmission to ascii instead of binary
    >bye #exit

## Automated

Anon oturum açma ve sıçrama FTP kontrolleri varsayılan olarak -sC seçeneği ile nmap ile gerçekleştirilir.

## Browser connection

    ftp://anonymous:anonymous@10.10.10.98

Bir web uygulaması, bir kullanıcı tarafından kontrol edilen verileri doğrudan bir FTP sunucusuna gönderiyorsa, çift URL kodlu% 0d% 0a (çift URL kodlamasında bu% 250d% 250a'dır) bayt gönderebilir ve FTP sunucusunun rastgele eylemler gerçekleştirmesini sağlayabilirsiniz. Bu olası rastgele eylemlerden biri, içeriği kullanıcı tarafından kontrol edilen bir sunucudan indirmek, bağlantı noktası taraması yapmak veya diğer düz metin tabanlı hizmetlerle (http gibi) konuşmaya çalışmaktır.

## Download all files from FTP

    wget -m ftp://anonymous:anonymous@10.10.10.98 #Donwload all
    wget -m --no-passive ftp://anonymous:anonymous@10.10.10.98 #Download all

## Telnet Enumeration

Telnet, kullanıcılara ağ üzerinden bir bilgisayara güvenli olmayan erişim sağlayan bir ağ protokolüdür.

    Default port: 23
    23/tcp open  telnet

## Enumeration

## Banner Grabbing

    nc -vn <IP> 23

## nmap 

    nmap -n -sV -Pn --script "*telnet* and safe" -p 23 <IP>

## Config file

    /etc/inetd.conf
    /etc/xinetd.d/telnet
    /etc/xinetd.d/stelnet



































