eJPT Networking Part 1

# Networking

Konu başlıkları

1. Protokoller
2. Internet Protokol(IP)
3. Routing
4. Bağlantı katmanı  cihazları ve protokolleri (Link Layer Devices and Protocols)
5. TCP ve UDP
6. Güvenlik Duvarı ve Ağ Güvenliği (Firewall and Network Defense)
7. DNS
8. Wireshark

## Protocols | Protokoller

Bir bilgisayar ağında makineler protokoller aracılığıyla birbirleriyle konuşur.
Bu protokoller farklı donanım ve yazılım kullanan farklı bilgisayarların iletişim kurmasını sağlar.
İnternette her birinin kendi amacı olan çok çeşitli ağ protokolleri vardır.

## Paketler | Packets

Ağ oluşturmanın birinci amacı, ağa bağlı bilgisayarlar arasında bilgi alışverişi yapmaktır  Bu bilgiler paketler tarafından taşınır.

Paketler, veri iletimi için kullanılan fiziksel ortamda elektrik sinyalleri olarak bit akışlarından başka bir şey değildir.Bu tür bir ortam, bir LAN'daki biir kablo veya bir WiFi networkteki hava olabilir.

Bu elektrik sinyalleri daha sonra bilgileri oluşturan bitler(sıfırlar ve birler) olarak yorumlanır.

 Her protokoldeki her paket yandaki yapıya sahiptir.

 ![](https://raw.githubusercontent.com/cagatayceyhan/terminal_Img/main/122.PNG)

## HEADER

Başlığın protokole özgü bir yapısı vardır  bu alıcı ana bilgisayarların yükü doğru şekilde yorumlayabilmesini ve genel iletişimi yönetebilmesini sağlar.

## PAYLOAD

Gerçek bilgidir. İndirme sırasında bir e-posta mesajının parçası veya bir dosyanın içeriği gibi bir şey olabilir.

ÖRNEK - THE IP HEADER - IP  Başlığı

Örneğin, IP protokol başlığı en az 160 bit (20 bayt)  uzunluğundadır ve IP paketinin içeriğini yorumlamak için bilgi içerir.

![](https://raw.githubusercontent.com/cagatayceyhan/terminal_Img/main/IP%20header.PNG)

İlk 4 bit IP versiyonunu tanımlar. Bugün ip v4 ve ip v6 sürümlerini temsil etmek için kullanılırlar.

![](https://raw.githubusercontent.com/cagatayceyhan/terminal_Img/main/ipversiyon.PNG)

96.pozisyonda başlayan 32bit, kaynak adresini temsil eder.

![](https://raw.githubusercontent.com/cagatayceyhan/terminal_Img/main/kaynak.PNG)

Aşağıdaki 4 bayt ( 32 bit) hedef adresi temsil eder.

![](https://raw.githubusercontent.com/cagatayceyhan/terminal_Img/main/destination.PNG)

Başlıktaki bilgileri kullanarak, iletişime dahil olan düğümleri IP paketlerini anlayabilir ve kullanabilir.

## PROTOKOL LAYERS | PROTOKOL KATMANLARI

önceki örnekte  IP'nin (internet protokolü) başlığını gördük. Herbiri belirli bir amaca yönelik olan bir çok protokol var. 

Şunlar gibi 

- E-posta 
- Dosya alışverişi 
- VoIP aramaları yapma
- Bir sunucu ile bir istemci arasında iletişim kurma
- Bir ağdaki bilgisayarları tanımlama
- Veri iletme

Listeyi yeniden şu şekilde yazabiliriz.

- Application Layer
- Transport Layer
- Network Layer
- Physical Layer 



Bu katmanlar birbirinin üzerinde çalışır ve her katman kendi protokolüne sahiptir.

Her katman üstündeki katmana hizmet eder.

Uygulama katmanı bir ana bilgisayardaki bir işlemi nasıl tanımlayacağımızı ona nasıl ulaşacağımızı ve bir iletişim  kurmak için bakır telin nasıl kullanılacağını bilmesine gerek yoktur.Sadece temel katmanlarını kullanır.

## ISO/OSI 

OSI 1984 te uluslararası standarditasyon örgütü (ISO) ağ iletişimi için teorik bir model yayınlandı./ Open System Interconnection (OSI) açık sistemler arası iletişim gibi türkçeye çevirebiliriz.

OSI yedi katmandan oluşur ve gerçek protokollerin uygulanması için referans olarak kullanılır.

## ENCAPSULATION

TCP/IP bir ağ yığının gerçek dünyadaki  uygulamasıdır. ve internette kullanılan protokol yığınıdır.


TCP/IP 4 katmanı vardır.

- Application 
- Transport
- Network
- Physical

![](https://raw.githubusercontent.com/cagatayceyhan/terminal_Img/main/tcp.PNG)

![](https://raw.githubusercontent.com/cagatayceyhan/terminal_Img/main/encap1.PNG)

Uygulama katmanı paketini kendi başlığını ekleyen taşıma katmanına verir.

Uygulama paketi artık taşıma protokolünün yüküdür.

Aynı teknik aşağıdaki katmanlar tarafından da kullanılmaktadır.

Kapsulleme sırasında her protokol pakete kendi başlığını ekler ve bunu bir yük olarak ele alır.

Bu ana bilgisayar tarafından gönderilen her pakete olur.

Alıcı ana bilgisayar aynı işlemi ters sırada yapar.Bu yöntemi kullanarak uygulamanın aktarım ağ ve bağlantı katmanları nasıl çalıştığı konusunda endişelenmesine gerek yoktur. Sadece paketi taşıma katmanına verir.

## INTERNET PROTOCOL / IP

Internet protokolü (IP) TCP/ IP olarak da bilinen internet protokolü  paketinin internet katmanı üzerinde çalışan protokolüdür. IP veri birimlerini (IP paketlerine veri katarları denir) bir iletişimde yer alan ana bilgisayarlara teslim etmeden sorumludur ve bir ana bilgisayarı tanımlamak için IP adresini kullanır.

Mektup yazarken göndermeden önce zarfın üzerine adresini belirtmeniz gerekir. Benzer şekilde internet paketlerini doğru hedefe ulaştırmak için adresleme şeması kullanılır.

Bir bilgisayar ağındaki herhangibir ana bilgisayar ister özel bir ağ ister internet olsun benzersiz bir IP adresiyle tanımlanır.


## IPv4 Addresses | IPv4 Adresleri

Ağların büyük çoğunluğu IP sürüm 4 (IPv4) çalıştırır. IPv4 adresi 4 byte veya 32 bitten oluşur.


    73.5.12.132

Her noktadan sonra 8 bitlik bir değer alır.

![](https://raw.githubusercontent.com/cagatayceyhan/terminal_Img/main/ip%20adresi.PNG)

8 bitlik  0dan 255 e kadar 28  farklı değeri temsil eder.

Bu 0.0.0.0 ile 255.255.255.255 arasındaki bir adresi bir anabilgisayara atayabileceğimiz anlamına gelmez.  Bazı adresler özel amaçlar için ayrılmışlardır.

Örneğin ayrılmış bazı aralıklar şunlardır.

0.0.0.0-0.255.255.255 "bu"ağı temsil eder.

127.0.0.0 - 127.255.255.255 yerel ana bilgisayarı temsil eder(local)

192.168.0.0-192.168.255.255 özel ağlar için ayrılmışlardır.

IPv4 adreslerinin özel kullanımıyla ilgili ayrıntılı bilgiyi RFC5735 standar dökümantasyonunda bulabilirsiniz.


## IP/MASK 

Bir ana bilgisayarı tam olarak tanımlamak için ağınıda bilmeniz gerekir.Bunu yapmak için bir ip adresine ve bir ağ maskesine veya alt ağ maskesine ihtiyacımız olur.

Bir IP / ağ maskesi çifti ile bir IP adresinin ağ bölümünü ve anabilgisayar bölümünü tanımlayabilirsiniz.

IP address : 192.168.5.100
Subnet mask :  255.255.255.0

Ağ bölümünü bulmak için ağ maskesi ve IP adresi arasındaki bit düzeyinde VE işleme gerçekleştirmemiz gerekir.

192.168.33.12/255.255.224.0

oktetlerin binary biçimine dönüşümü

![](https://raw.githubusercontent.com/cagatayceyhan/terminal_Img/main/binary.PNG)

## IPv6

IPv4 adresleri her gün internete bağlanan çok sayıda cihaz nedeniyle tükeniyor.

32 bitlik bir adres olarak IPv4 ün 2^32 = 4.294.967.296 olası adresi vardır.

128 bitlik bir adres olarak IPv6 nın 2^32 * 2^96 olası değeri vardır. 2^96 değerinin 79 oktilyon adrese eşittir.

Bir IPv6 adresin iki nokta üst üste : ile ayrılmış 16 bitlik onaltılık sayı sisteminden oluşur. Onaltılık sayılar büyük küçük harf duyarlılığı vardır.0 ların olması durumunda atlanabilirler.

IPv6 adres örnekleri

2001:0db8:0020:130F:0000:0000:087C:140B

2001:0db8:0:160F::850C:140B

![](https://raw.githubusercontent.com/cagatayceyhan/terminal_Img/main/ipv6.PNG)

IPv6 aşağıdaki metin gösteriminde sunulabilir:

Normal biçim : 1080:0:FF:0:8:800:200C:417A

Sıkıştırılmış form :  FF01:0:0:0:0:0:0:43 Sıfırların atlanması sonucu FF01::43 olur.

IPv4  0:0:0:0:0:0:13.1.68.3 sıfırları attıktan sonra  ::13.1.68.3 bu değere ulaşır.


IPv6 ayrıca ayrılmış IPv4 adresleri gibi kullanılmayan özel durumlar için ayrılmış adreslere sahiptir.


Örneğin :

1/128 geri döngü adresidir.

::FFFF:0:0/96 IPv4 ile eşlemeli adreslerdir.

Bir IPv6 Adresi ikiye bölünebilir.(her biri 64 bit) ağ bölümü ve cihaz bölümü olarak ayrıca ilk 64 bit yalnızca alt ağı belirlemek için kullanılabilirken özel bir 16 bitlik boşlukla sona erer.

![](https://raw.githubusercontent.com/cagatayceyhan/terminal_Img/main/ipv6.2.PNG)

IPv6 adreslerinin üç türü vardır.(ikisini belirtmiş)

- Global Unicast address = Bu adresler globaldir ve global internette bulunurlar.
- Unique Local and Link local = Yalnızca yerel ağlarda bulunur.

IPv4 gibi IPv6 adresininde  bir ağ bölümü ve bir cihaz bölümü vardır.IPv4 den farklı olarak bir  IPv6 adresinin özel bir alt ağ bölümü vardır. 


Ağ adresi aralığı IPv6 da ilk 48 bit internet global adresleme içindir.

![](https://raw.githubusercontent.com/cagatayceyhan/terminal_Img/main/ipv6.3.PNG)

Alt ağ oluşturma aralığı 49'dan 64 e kadar 16  bit alt ağları tanımlamak içindir.

![](https://raw.githubusercontent.com/cagatayceyhan/terminal_Img/main/ipv6.4.PNG)

Son 64 bit cihaz (arayüz) kimlikleri içindir.

![](https://raw.githubusercontent.com/cagatayceyhan/terminal_Img/main/%C4%B1pv6.5.PNG)

IPv6 da alt ağ blokları yerine önekler vardır.

 
    2001:1111:1234:1234::/64

Yukarıdaki IPv6 adresine eğik çizgiden sonraki sayıbir önek için kullanılan bit sayısıdır.Arkasındaki her şey alt ağın ana bilgisayarları için kullanılabilir.

Fark etmiş olabileceğiniz gibi 64,ilk 64 bitin bir önek olduğu anlamına gelir ve daha önce de belirtildiği gibi her 4 basamaklı onaltılık kelime 16 bittir.Bu nedenle IPv6 adresini takip ederek onu şu şekilde bölebiliriz.

![](https://raw.githubusercontent.com/cagatayceyhan/terminal_Img/main/%C4%B1pv6.6.PNG)

2001: 1234:5678:1234 : 0000:0000:0000:0000  geçerli bir önektir ancak aşağıdaki biçime sıfırlar atılarak kısaltılabilir. 2001 : 1234 : 5678 : 1234 :: /64




















