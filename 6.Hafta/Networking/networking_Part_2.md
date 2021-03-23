ejpt-Part-2

# Routing


Routing protokolleri bir ağa ulaşmak için en iyi yolu belirlemek için kullanılır. Mektubu teslim etmek için  mümkün olan en kısa yolu  kullanmaya çalışan bir postacı gibi davranırlar.

Bir Router gelen her paketin hedef adresini inceler ve  ardından arayüzlerinden biri aracılığyla iletir.

Doğru yönlendirme arayüzünü seçmek için bir yönlendirici bir IP arayüz bağlantısı bulduğu yönlendirme tablosunda bir arama gerçekleştirir.

Tablo ayrıca varsayılan adresli(0.0.0.0) bir giriş içerebilir.Bu girdi yönlendirici hedefi bilinmeyen bir ağ olan bir paket aldığında kullanılır.

![](https://raw.githubusercontent.com/cagatayceyhan/terminal_Img/main/R1.PNG)

Bu örnekte, yönlendirme tablosu üç girişten yapılmıştır.


- Arayüz 1 paketleri 228.72.0.0/16 ya iletmek için kullanılır.
- Arayüz 2 paketleri 192.168.5.0/24 e iletmek için kullanılır.
- Arayüz 3 hedefi tablodaki diğer herhangi bir girişle eşleşmeyen paketler için varsayılan yol olarak kullanılır.

Yönlendirme Tablosu Örneği

192.168.5.3 için arayüz 3 e gelen bir paket arayüz 2 ye iletilir.

![](https://raw.githubusercontent.com/cagatayceyhan/terminal_Img/main/R2.PNG)

Yönlendirme tablosundaki ilk giriş hedef ağ ile eşleşmiyor.

![](https://raw.githubusercontent.com/cagatayceyhan/terminal_Img/main/R3.PNG)




İkincisinde ise 192.168.5.0/24 ağında 192.168.5.3 ile eşleşiyor.

![](https://raw.githubusercontent.com/cagatayceyhan/terminal_Img/main/R4.PNG)

Varsayılan rota örneği

72.13.37.2 için arayüz 1 e gelen bir paket varsayılan yol olan arayüz 3 üzerinden yönlendirilir.

![](https://raw.githubusercontent.com/cagatayceyhan/terminal_Img/main/R5.PNG)


Eşleşen giriş yok bu nedenle yönledirici paketi arayüz 3 üzerinden iletir.

![](https://raw.githubusercontent.com/cagatayceyhan/terminal_Img/main/R6.PNG)


Gerçek dünyada olduğu gibi hedefe ulaşmak için birden fazla yol vardır.

Bu nedenle yol keşfi sırasında yönlendirme protokolleri ayrıca her bağlantıya bir metrik atar

bu iki yolun aynı sayıda atlama sayısına sahip olması durumunda en hızlı rotanın seçilmesini sağlar.

metrik kanalın tahmini bant genişliğine ve tıkanıklığına göre seçilir.

Metriklere göre yönlendirme kararının nasıl verildiğine bakalım

![](https://raw.githubusercontent.com/cagatayceyhan/terminal_Img/main/R7.PNG)


11.32.3.118 için arabirim 3 e gelen bir paket arabirim 1 üzerinden yönlendirilir çünkü yolun ölçüsü 15 tir.

Arayüz 2 üzerinden yönlendirme 17 metriğe sahip olacaktır.

![](https://raw.githubusercontent.com/cagatayceyhan/terminal_Img/main/R8.PNG)




Yönlendirme tabloları sadece yönlendiriciler tarafından tutulmaz her host kendi tablosunu saklar

Nasıl göründüklerini kontrol etmek için şunları kullanabiliriz.


- ip route on Linux
- route print on Windows
- netstat -r on OSX

Linux üzerinde yönlendirme tablosunu kontrol etmek:

![](https://raw.githubusercontent.com/cagatayceyhan/terminal_Img/main/R9.PNG)

Microsoft Windows üzerinde yönlendirme tablosu kontrol etmek:


![](https://raw.githubusercontent.com/cagatayceyhan/terminal_Img/main/R10.PNG)


Mac OSX üzerinde yönlendirme tablosunu kontrol etmek:

![](https://raw.githubusercontent.com/cagatayceyhan/terminal_Img/main/R11.PNG)

# Link Layer Devices and Protocols | Bağlantı Katmanı ve Cihazları
Paket iletme TCP/IP en alt katmanında gerçekleşir.Bu katmanın adı Link Layer /bağlantı katmanıdır.

Yönlendiriciler hedefe giden en iyi genel yolun farkında olsalar da bağlantı katmanı aygıtları ve protokolleri yanlızca bir sonraki atlama ile ilgilenirler.

Bu bölüm bunları içerir : 

Switch nasıl çalışır.

Ağ kartı MAC adresleri

Adres çözümleme protokolü (ARP)

Hublar ve anahtarlar, yerel bir ağda  çerçeveleri /Frames (katman 2 paketleri) ileten ağ cihazlarıdır.

Bağlantı katmanları ağ adresleriyle çalışır MAC adresleriyle

IP adresleri bir ağdaki bir ana bilgisayarı tanımlamak için kullanılan katman 3 network katmanı adresleme şemasıdır.MAC adresi ise bir ağ kartını  benzersiz bir şekilde tanımlar (katman 2)

bir MAC (Ortam Erişim Kontrolü) adresi aynı zamanda fiziksel adres olarakda bilinir.


```
00:11:AA:22:EE:FF
```

Bilgisayarınızda yüklü olan ağ kartlarının MAC adresini bulmak için şunları kullanabiliriz.

- ipconfig /all on Windows
- ifconfig on *nix operating systems, like MacOS
- ip addr on Linux

Bir ağdaki her ana bilgisayarın hem bir MAC hem de bir IP adresi vardır.

Paket göndermek için  birlikte nasıl kullanıldıklarını görelim.

UNUTMA ALT KATMAN ÜSTEKİ KATMANA HİZMET EDER.

MAC adreslerinin nasıl kullanılacağını görmek için bir örneğe bakalım.

![](https://raw.githubusercontent.com/cagatayceyhan/terminal_Img/main/LA1.PNG)



* Bir yönlendirici ile iki farklı ağ birbirine bağlanır

![](https://raw.githubusercontent.com/cagatayceyhan/terminal_Img/main/LA2.PNG)

* Ağdaki her ana bilgisayarın hem bir IP'si hemde bir MAC adresi vardır. Yönlendiricinin her biri kendi adreslerine sahip iki arabirimi vardır.

![](https://raw.githubusercontent.com/cagatayceyhan/terminal_Img/main/LA3.PNG)






* İş istasyonu A iş istasyonu B ye bir paket göndermek isterse hangi IP ve MAC adreslerini kullanacaktır.

* İş istasyonu A aşağıdakileri içeren bir paket oluşturacaktır:

* İş istasyonunun hedef IP adresi Datagramın IP  başlığını böl.

* Frame bağlantı katmanı başlığındaki yönlendiricinin hedef MAC adresi

* A iş istasyonunun kaynak IP adresi

* A iş istasyonunun kaynak MAC adresi

* Yönlendirici daha sonra paketi alır ve B nin ağına iletir,paketin MAC adreslerini yeniden yazar:

* Hedef MAC adresi  B olacaktır.

* Yönlendiricinin kaynak MAC adresi

* Yönlendirici kaynak ve hedef IP adreslerini değiştirmeyecektir.

* Bir cihaz paket gönderdiğinde:

* Hedef MAC adresi sonraki sekmenin MAC adresidir.bu yerel olarak ağın paketi nereye ileticeğini bilmesini sağlar.

* Hedef IP adresi hedef ana bilgisayarın adresidir. bu global bilgidir ve paket gezisi boyunca aynı kalır.

* Bu yöntem bir  bakıma bir arkadaşınıza nasıl mektup göndericeğinizi hatırlatır.

* Ev adresini(IP Adresini) ve mektubu bırakabileceğiniz en yakın postanenin adresini (MAC adresini )bilmeniz gerekir.

* Bunların dışında özel bir MAC adresi vardır.

```
FF:FF:FF:FF:FF:FF
```
 
* Bu adres broadcast/ yayın MAC adresidir.

* Bu adrese sahip bir çerçeve / frame  (katman 2 deki paketin adı) yerel ağdaki (aynı yayın etki alanı içindeki)tüm ana bilgisayarlara gönderir.










