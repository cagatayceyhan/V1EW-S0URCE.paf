|eJPT-networking-Part-3| 

# Swiches


Yönlendiriciler / Routerlar IP maskesiyle çalışırken swichler MAC adresleriyle çalışırlar. 

Swichlerin ayrıca birden fazla arabirimi vardır. bu nedenle bir veya daha fazla MAC adresini bir arabirime bağlayan bir yönlendirme tablosu tutmaları gerekir.

![](https://raw.githubusercontent.com/cagatayceyhan/terminal_Img/main/sw1.PNG)

Yönlendirme tablosuna CAM (içerik adresleme belleği) denir.Bir çok ana bilgisayar bir Switch e bağlanabilir. Nasıl olduğunu görelim

![](https://raw.githubusercontent.com/cagatayceyhan/terminal_Img/main/sw2.PNG)

Karşılaşabileceğimiz en küçük sqitcler genellikle bir DSL ev routerına entegre edilen ev switchleridir.Genellikle 4 porta sahiptirler.

Kurumsal Switchler  64 adete kadar bağlantı noktasına sahip olabilir. ve sistem yöneticileri daha fazla ana bilgisayarı barındırmak için birden çok switch i  birbirine bağlayabilirler.

Bir switch ile diğeri arasındaki temel fark paket yönlendirme hızıdır.

Bir switch hızı 10 mbps ile 10Gbps arasında değişir.Günümüzde 1 Gbps ticari anahtarlarda en yaygın yönlendirme hızıdır.


Bu şemada tüm makineler aynı ağ üzerindedir.

Switchler tüm bilgisayarların birbirleriyle konuşmasına izin verirler.

![](https://raw.githubusercontent.com/cagatayceyhan/terminal_Img/main/sw3.PNG)

VLAN olmayan Switchler ağları segmentlere ayıramaz.Routerlar bu işi yapar.

![](https://raw.githubusercontent.com/cagatayceyhan/terminal_Img/main/sw4.PNG)

# SEGMENTASYON


Genellikle bir Router ın her ara birimi farklı bir ağ adresine sahip farklı bir alt ağ eklenir.

Ayrıca Router lar bir ff:ff:ff:ff:ff:ff yayını yapan MAC adresine sahiplerse bir arabirimden gelen paketleri iletmezler.

10.10.9.4 IP si 10.10.1.4 e paket göndermek isterse neler gerçekleşir.

![](https://raw.githubusercontent.com/cagatayceyhan/terminal_Img/main/sw6.PNG)


İlk Switch paketi alır CAM tablosunda bir arama gerçekleştirir ve onu bir sonraki Switch e iletir.
![](https://raw.githubusercontent.com/cagatayceyhan/terminal_Img/main/sw7.PNG)


İkinci switch paketi 10.10.1.4 e iletir.

![](https://raw.githubusercontent.com/cagatayceyhan/terminal_Img/main/sw8.PNG)


10.10.1.4 IP üzerinden 192.168.2.3 adresine bir paket göndermek istersek ne olur.
![](https://raw.githubusercontent.com/cagatayceyhan/terminal_Img/main/sw9.PNG)


10.10.1.4 Paketi yönlendiriciye göndermesi gerekir böylece ilk Switch paketi bir sonrakine iletir.
![](https://raw.githubusercontent.com/cagatayceyhan/terminal_Img/main/sw10.PNG)


Paket daha sonra Router a ulaşır ve yönlendirme tablosuna baktıktan sonra onu 192.168.2.0/24 ağına iletilir.

![](https://raw.githubusercontent.com/cagatayceyhan/terminal_Img/main/sw11.PNG)


Son olarak paket teslim edilir.

![]()


Yönlendirme tablosu MAC adreslerini arayüze bağlar.

Tipik bir yönlendirme tablosu şunları içerir :

MAC adresi

Switchlerin paketlerini belirli bir MAC adresine teslim etmek için kullanabileceği arayüzler

Yaşama Zamanı/ TTL

![](https://raw.githubusercontent.com/cagatayceyhan/terminal_Img/main/sw12.PNG)


Yönlendirme tablosu veya CAM tablosu cihazın RAM ınde saklanır ve sürekli olarak yeni bilgilerle yenilenir.

![]()


Tabloya bakarak şunları söyleyebilirsin:

Sırayla arayüz 1 ve 3 e tek bir ana bilgisayar eklenir.

arabirim 2 ye iki anabilgisayar eklenir(muhtemelen başka switchler aracılıyla.)

![]()


Aynı ana birimler ve arabirimler üzerinde herhangi bir ana bilgisayar eklenmemiş birden çok ana bilgisayar olabilir.

Örnek olarak arayüzde 4 numaraya bağlı bilgisayar yok.

TTL bir girişin tabloda ne kadar kalacağını belirler. bu önemlidir çünkü CAM tablosu sonlu bir boyuta sahiptir.

Bu nedenle bir girişin süresi dolar dolmaz tablodan kaldırılır.

![]()



Switch yeni MAC adreslerini dinamik olarak öğrenir aldıkları her paketin başlığını incelerböylece yeni ana bilgisayarları tanımlar.

Routerlar yönlendirme kurallarını güncellemek için karmaşık yönlendirme protokollerini kullanırken switcler bir paketi iletirken hangi arabirimi kullanıcaklarına karar vermek için yanlızca işledikleri paketlerin MAC adresini kullanır.


Kaynak MAC adresi CAM tablosu ile karşılaştırılır.

MAC adresi tabloda değilse switch tabloya yeni bir MAC arayüzü bağlaması ekleyecektir.

MAC arayüz bağlantısı zaten tabloda ise TTL güncellenir.

MAC tablodaysa ancak başka bir arayüze bağlıysa switch tabluyu günceller.

![]()


Bir paketi iletmek için 

Switch framein hedef MAC adresini okur.

CAM tablosunda bir arama gerçekleştirir.

Paketi ilgili arayüze iletir.

Bu MAC adresiyyle herhangi bir giriş yoksa switch frame i tüm arabirimlerine iletir.







ARP


Bir anabilgisayar başka bir anabilgisayara bir paket göndermek istediğinde uygun bir paket oluşturmak için hedefin IP sini MAC adresine bildirmesi gerekir.


Eğer adresi bilmiyorsan arkadaşına Mektup gönderemezsin. Kaynak ana bilgisayar IP adresini billiyor ancak hedef ana bilgisayarın MAC adresini bilmiyorsa ne olur?

Bu durum pek çok durumda örneğin her açılışta meydana gellir.

Ofisteki bir bilgisayar ,dosya sunucusu,yazıcılar ve web sunucusu gibi bir dizi IP adresini bilir ancak karşılık gelen MAC adresini bilmez.

Ana bilgisayarın diğer ağ düğümlerinin MAC adresini bilmesi gerekir ve bunları Adres çözümleme protokolü ARP kullanarak öğrenebilir.

ARP ile bir ana bilgisayar doğru IP adresini MAC adresi ile bağlamasını oluşturabilir.

Bu herhangi bir modern ağın kullandığı temel  protokollerden biridir

Bir ana bilgisayar A bir başkasına B trafik göndermek istediğinde ve yalnızca  B nin sadece IP adresini bildiğinde :

Hedef MAC adresi  olarak YAYIN ff:ff:ff:ff:ff:ff nib IP adresini  içeren bir ARP isteği oluşturur. Bu temeldir çünkü switch paketi her ana bilgisayara ileticektir.

 Ağdaki her ana bilgisayar talebi alacaktır.

ARP B nın MAC adresini söyleyen bir cevap döner.

 A adresi Broadcast MAC adresine bir paket göndererek b nin MAC adresini sorar.

![]()


 Switch paketi tüm bağlantı noktalarına gönderir.

![]()



 B adresi A adresine MAC adresini söyleyerek yanıt verir.

![]()


Son olarak switch yanıtı A adresine iletir.

![]()


Aygıt RAM ın boyutu sınırlı olduğundan ARP ön bellek girişinin de TTL süresi vardır.

Bir toplantı sahibi gücü kapatırken veya girişin TTL si sona erdiğinde bir girişi iptal etmiş olur.

Ana makinenizin ARP ön belleğini yazarak kontrol etmek için 

•arp -a on Windows. 
•arp on *nix operating systems 
•ip neighbour on Linux

HUBS 



Hublar bilgisayar ağlarında switch lerden önce kullanılıyorlardı.Aynı amaca sahiplerdi ama aynı işlevselliğe sahip değillerdi.

Hublar herhangi bir tür başlık kontrolü yapmadan ve sadece elektrik sinyallerini tekrarlayarak paketleri ileten basit tekrarlayıcılardır.

Bir bağlantı noktasından elektrik sinyalleri  alırlar ve diğer tüm bağlantı noktalarında aynı sinyalleri tekrarlarlar.

Bu hub tabanlı bir ağdaki her düğümün aynı elektrik sinyallerini dolayısıyla aynı paketleri aldığı anlamına gelir.

Günümüzde hubların yerini switcler almıştır. Kullanımı çok nadirdir. 

![]()


TCP & UDP



Bu katmanda taşıma katmanının nasıl çalıştığını  ve uygulama katmanın sunucu ve istemci işlerini tanımlamak için hizmetlerini nasıl kullandığını göreceksiniz.

İletim kontrol protokolü / TCP ve kullanıcı Datagram protokolü / UDP internette kullanılan  en yaygın aktarım protokolleridir. 

Bir taşıma katmanı protokolünün uygulama katmanına  sunabileceği farklı hizmetleri incelemeden önce, ağlarla ilgili  önemli bir konuyu ele alılım

Bilgisayar ağları güvenilmez olabilir.Bu kaynaktan hedefe yolculuk sırasında bazı paketlerin kaybolabileceği anlamına gelir.Ağ tıkanıklığı geçici bağlantı kaybı ve diğer teknik konular nedeniyle bir paket kaybolabilir.

Bir TCP protokolü tasarlarken tasarımcı bu sınırlarla nasıl başa cıkacağını seçmelidir.

 Örneğin TCP:

Paket teslimini garanti eder.Bu nedenle garantili teslimat gerektiren bir uygulama taşıma protokolü olarak TCP kullanılır.

Aynı zamanda bağlantı odaklıdır. Verileri aktarmadan önce bir bağlantı kurması gerekir.

TCP internette en çok kullanılan aktarım protokolüdür. Uygulamanın büyük çoğunluğu bunu kullanır ve IP protokol paketi genellikle TCP / IP olarak aktarılır.


Diğer yandan UDP ,TCP den çok daha  basittir.

UDP 

Paket teslimini garanti etmez.

Bağlantı odaklı değildir.

UDP daha iyi bir çıktı (saniyede ki paket sayısı) sağladığından  TCP den daha hızlıdır. Aslında paket sayısını tolere edebilen ancak yoğun iş hacmi olan multimedya uygulamaları tarafından kullanılır.

Örneğin UDP voIP ve Video akışı için kullanılır: ses veya videoda küçük  bir aksaklığı tolere edebileceğimiz uygulamalardır.

Buradaki tabloda TCP ve UDP karşılaştırdığımız bir tablo yer almakta.

![]()



PORTS



Uygulamalar ve süreçleri ağ üzerinden veri gönderip veri almak için TCP ve UDP kullanır.Bir IP ana bilgisayara ulaştığında taşıma katmanı hedef sürecinin ne olduğunu nasıl bilebilir?

Şimdi portlara bakacağız.

Port noktaları bir makinede ki tek bir ağ işlemini tanımlamak için  kullanılır.Bir ağdaki bir işlemi  kesin olarak tanımlamak istiyorsanız  <IP> <PORT> çiftini bilmeniz gerekir.

Örnek olarak bağlantı noktasını bir harf üzerindeki alıcının adıyla karşılaştırabilirsiniz. Sokak adresi IP binayı belirtirken kişi adı mektubun son alıcısını tanımlar.

Bu görüntüde istemci PC deki her istemci uygulamasının farklı bir bağlantı noktasınıu / PORTUNU nasıl kullandığını görebilirsiniz.

![]()


Tarayıcı web sunucusuna bağlanmak için yerel bağlantı noktası 3028 portunu kullanır.

Mail istemcisi yerel bağlantı noktası  1022 portunu kullanır.

Web tarayıcısından Web sunucusuna tüm iletişimde kaynak bağlantı noktası olarak 3028 ve hedef bağlantı noktası olarak 80 olacaktır.

Web sunucusundan tarayıcıya geri gönderilen tüm iletişimde kaynak bağlantı noktası 80 ve hedef port / kaynak noktası 3028 olacaktır.

Benzer şekilde posta istemcisi ve sunucusu için:

posta istemcisinden sunucuya tüm iletişimde kaynak bağlantı noktası  olarak 1022 ve hedef bağlantı noktası 25  portu olacaktır.

posta sunucusundan posta istemcisine  tüm iletişimlerde kaynak noktası 25 portu olurken  bu sefer hedef port 1022 portu olacaktır.

Ayrıca aynı anda çalışan aynı uygulamanın birden çok örneğine sahip olabilirsiniz.Her işlem farklı  bir bağlantı noktası ayıracaktır.

![]()


Bu örnekte A kaynak bağlantı noktası  olarak  3028 i kullanarak web sunucusuyla iletişim kurar.

Web browser  port 8723  nolu portu kullanırken 

![]()


Bir ağdaki bir işlemi doğru şekilde adreslemek için  <IP> : <PORT> çiftine başvurmanız gerekir.

Örneğin:

- 192.168.5.3:80 
- 10.11.12.1:443
- 172.16.8.9:22


Ancak ortak bir hizmet için doğru bağlantı noktasını nasıl bilebiliriz?

Well-known Ports / İyi Bilinen Portlar 


ilk 1024 olan 0-1023 aralığındaki portlar  iyi bilinen portlar olarak adlandırılırlar vew sunucular tarafından en yaygın serfisler için kullanılır.

Örneğin bir web tarayıcısı bir sunucuya HTTPS aracılıyla bağlandığında kullanıcının hedef bağlantı noktası 443 ü monuel olarak belirtmemiz gerekmez.


Her ortak protokol  0-1023 aralığında iyi bilinen bir bağlantı noktasına sahiptir. Yaygın sunucu  işlemleri  veya arkaplan uygulamaları çoğu zaman iyi bilinen bağlantı noktaları nı kullanır.

Tüm servis  portu atamalarını bilmemize gerek yoktur ama en azından aşağıdaki gibi yaygın olan ları bilmemiz gerekir.

SMTP 25

SSH 22

POP3 110

IMAP143

HTTP 80

HTTPS 443

NETBIOS 137,138,139

SFTP 115

TELNET 23

FTP 21

RDP 3389

MySQL 3306

MS SQL SERVER 

Daha önce kısaca anlatıldığı gibi bir deamon bir hizmeti çalıştıran bir programdır.Sistem yöneticileri servisin bağlantı için dinlediği bağlantı noktasını değiştirerek  deamon yapısını değiştirebilir.bunu hackerlar  sistemleri daha zor tanıması için biraz daha zor hale getirmek için yapıyorlar.

Örneğin 21 yerine 4982 numaralı bağlantı noktasında  veya 8821 numaralı bağlantı noktasında SSH dinleyen bir FTP arka planı programı bulabilirsiniz.

Şimdi bağlantı noktalarının uygulamalar tarafından nasıl  kullanıldığını görelim.

Sunucu ve istemci uygulamaları  hangi bağlantı noktasının kullanılacağını nasıl bilebilir.TCP veya UDP başlığında iki alan kullanırlarÇ kaynak ve hedef bağlantı noktaları

Kaynakta ve hedef bağlantı noktası  taşıma katmanı protokol başlığına dahil edilir. 

TCP başlığı gibi

![]()


UDP Başlığı 

![]()


Netstat Komutları


Dinleme bağlantı noktalarını  ve bir ana bilgisayardaki mevcut (TCP) bağlantılarını kontrol etmek için  şu komutları kullanabilirsiniz:

- •netstat -ano on Windows
- •netstat -tunp on Linux
- •netstat -p tcp -p udp together with
- lsof –n –i4TCP –i4UDP on MacOS


Makine dinleme işlemleri ve uzak sunuculara bağlanma işlemleri hakkında bilgi göstermek için bu komutlar kullanılır.

Windows için kullanılacak başka araç ise sysinternals tarafından sunulan TCPView aracıdır.

TCPView aracı 

İşlem ismi 

PID 

Protocol 

yerel ve uzak adresleri 

yerel ve uzak portları

Bağlantının durumu (varsa)

gibi durumları gösterir.

TCP Three Way Handshake / TCP Üçlü el Sıkışma 


TCP nın bağlantı odaklı olduğunu gördük.Şimdi TCP bağlantılarının  nasıl çalıştığına bakalım ve ilgili en önemli faktörleri sızma testi uzmanının bakış açısından 3 yönlü el sıkışma ile vurgulayalım.

TCP çalıştıran iki ana bilgisayar arasında bir bağlantı kurmak için üç adımı gerçekleştirmeleri gerekir:üç yönlü el sıkışma.Daha sonra gerçek veri aktarımını başlatabilirler.



El sıkışmada yer alan başlık alanları şunlardır.

sequence number /sıra numarası

Acknowledgement numbers / onay numarası 

SYN  and ACK bayrakları 

![]()


El sıkışmasındaki adımlar sunucu ve istemci  arasındaki  sıra ve alındı numaralarını senkronize etmek için kullanır.

![]()



İlk adımda istemci  SYN bayrağını etkinleştirilmiş ve rastgele  bir sıra numarasıyla  sunucuya bir TCP paketi gönderir.

![]()


İkinci adımda sunucu hem SYN hem de ACK bayrak seti ve başka bir rastgele sıra numarası içeren bir paket göndererek yanıt verir.

![]()


ACK numarası her zaman  istemci tarafından gönderilen SYN numarasının basit bir artışıdır.


Son olarak istemci bir ACK paketi  göndererek senkronizasyonu tamamlar.

İstemcinin ACK paketini gönderirken sunucu gibi davrandığına dikkat edin.


Güvenlik Duvarı ve Ağ Savunması


Piyasada bir sistem yöneticisinin ağı korumak için  kullanabileceği bir çok farklı cihaz vardır.

Bu cihazlar erişim kontrolü saldırı tespiti ve önleme gerçekleştirmek için farklı teknikler kullanır ve farklı katmanlar üzerinde çalışır.


Firewalls


Güvenlik duvarı bir bilgisayar veya özel bir ağ cihazı üzerinde çalışan özel tyazılım modülleridir.

Bir ağa giren ve çıkan paketleri filtrelemeye hizmet ederler.

![]()


Güvenlik duvarları sistem yöneticilerinin ve masaustu kullanıcılarının ağ kaynaklarına ve hizmetlerine erişimi kontrol etmelerine yardımcı olur.

 Bir güvenlik duvarı OSI modelinin farklı katmanları üzerinde çalışabilir. Böylece farklı özellikler  ve korumalar sağlanabilir.

 Güvenlik duvarlarının nasıl çalıştığını ve ne tür tehditleri  anlamamız zorunludur.

Bir çok kişi  güvenlik duvarları ve  antiviruslerin güvende kalmak için ihtiyaç duydukları  tek şey olduğuna inanır. 

 Bir güvenlik duvarının en temel  özelliği paket filtrelemedir.

Paket filtrelemeyi bir yönetici paketleri aşağıdaki   gibi  belirli özelliklere göre filtreleyerek kurallar oluşturabilir:

Paket filtrelemeyi bir yönetici paketleri  aşağıdaki gibi belirli özelliklere göre filtreleyerek kurallar oluşturabilir. 

- Kaynak IP adresi
  
- Hedef IP adresi 
  
- Protokoller
  
- Kaynak port 
  
- Hedef Port

Paket filtreleri  ev DSL yönlendiricilerin yanı sıra üst düzey kurumsal  yönlendiricilerinde çalışır ve ağ savunmasının temel taşıdır.

Paket filtreleri paketin nasıl işleneceği seçmek için her paketin başlığını inceler.Daha yaygın eylemler şunlardır.

Allow / izin ver :Paketin geçmesine izin ver

Drop /bırak : Paketi herhangi bir tanılama mesajı olmadan  paket kaynağı  ana bilgisayara bırakır.

Deny/ Reddet : Paketin geçmesine izin vermeyin ancak kaynak ana bilgisayara bildirin. 


Paket filtreleme güvenlik duvarı


Her paketin başlığını incelemek size gerçek içeriği hakkında herhangibir bilgi vermez.

Bir şirkette ağ yöneticileri dahili ağdan  web taramasına izin vermek  için kurumsal bir güvenlik duvarı yapılandırır.Bunu TCP trafiğinin  hedef noktası  olarak 80 veya 443 e sahip olmasına izin vererek yaparlar.Dahili bir makine  SSH aracılıyla  80 numaralı bağlantı noktasını  dinleyen bir  sunucuya bağlanmaya çalışırsa ne olur?

Şimdi paket incelemesinin bir bilgisayar korsanının sunucu istismar etmesini engellemediği tipik bir örneğe bakalım.

Bir şirket bir web sunucusu barındırır.Güvenlik duvarı İnternetten gelen internetten gelen tüm trafiğe izin verecek ve onu web sunucusunun 80 numaralı bağlantı noktasına yönlendirecektir.

![]()



Aynı şekilde uygulama açıklarıda geçecektir çünkü güvenlik duvarı  web de gezinme ile bir web uygulaması  istismarı arasındaki farkı göremez.

![]()


Aynı şekilde uygulama açıklarıda geçecektir çünkü güvenlik duvarı  web de gezinme ile bir web uygulaması  istismarı arasındaki farkı göremez.











































