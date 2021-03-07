# VoIP Nedir?

![](https://healthbeyondshowcase.org.au/wp-content/uploads/2018/05/VoIP-Logo-RichBlue.png)

Açılımı **Voice Over Internet Protocol** olan VoIP,kurumsal yerel alan ağları veya geniş alan ağları üzerinden ses ve multimedya içeriğinin iletilmesini sağlayan bir grup teknoloji ve metodolojidir.VoIP uç noktaları;özel masaüstü VoIP telefonlarını,PC'lerde ve mobil cihazlarda çalışan softphone uygulamalarını ve WebRTC etkin tarayıcılarını içerir.VoIP codec bileşenlerinin kullanılarak sesi veri paketine yerleştirir,paketleri bir ip ağı üzerinden iletir ve paketleri bağlantının diğer ucunda sesi geri sıkıştırır.VoIP,geniş bant ve özel ağlar üzerinden ses hizmeti sunulmasını ve işletmelerin tek bir ses ve veri ağı kullanmasını sağlar.VoIP ayrıca,kesintiler,uç noktalar ve ağlar arasında yedek iletişimi takiben hızlı yük devretmeyi etkinleştirerek IP tabanlı ağların esnekliğinide desteklemektedir.

VoIP altyapısı,standartları ve VoIP uç noktaları tipik olarak,sıkıştırılmamış paketlerin iletilmesi için standart olan G.711 veya sıkıştırılmış paketlerin standartı olan G.729 gibi Telekominikasyon Birliği(ITU) standart codeclerini kullanır.

# VoIP Penetrasyon Testi Nedir?

Birçok şirketin Maliyeti Düşürmek ve iletişim işlevselliğini arttırmak için VoIP protokolünü kullanmaya başlaması kurum ağına saldırı riskini de beraberinde getirmektedir.Olası Saldırı senaryolarının önceden saptanması ve bu senaryolardaki güvenlik açıklarının önlenmesi ağ güvenliği için kritik önem taşımaktadır.VoIP altyapısı sızma testleri,VoIP altyapısı güvenlik durumunun tam olarak anlaşılmasını sağlar ve olası saldırıda saldırganın sistemde oluşturabileceği hasar ve risklerin tespit edilmesine olanak tanır.

## VoIP Penetrasyon Testi Metadolojisi

* Veri şebekesinden ses şebekesine VLAN bağlantısı kurma

* Numaralandırmayı genişletme

* SIP kimlik doğrulamasını yakalama

* Dinleme Çağrıları

* CallerID sahtekarlığı

* RTP enjeksiyonu

* Sinyal yönetme

* Güvensiz hizmetlerin tanımlanması

* Uygulama düzeyinde güvenlik açıkları

* Sesli posta saldırıları

* Telefon firmware analizi

# VoIP  TEKNOLOJİSİNİN TOPOLOJİSİ VE CİHAZLARI

## VoIP Gatekeeper

Bant genişliğinin kontrolü,yönetim ve adres değişimleri buradan yapılır.Arama kabul kontrol işlemi de bu cihazda yapılır.

## VoIP Gateway

VoIP ve VoIP olmayan ağlar arasındaki geçişi sağlar.Analog ve Dijital VoIP cihazları ile fiziksel bağlantısı vardır.Örneğin VoIP Gateway  DLS hat ile PSTN hattın bağlanması için gereklidir.IP ağlar ile PBX arasında bağlantı kurulmasını sağlayarak analog sinyal ile gelen sesi dijital sinyale çevirdikten sonra IP üzerinden taşınmasına olanak sağlayan cihazdır.

## MCU (MULTIPOINT CONTROL UNIT)

MCU farklı fiziksel bölgelerden yapılan video konferans ya da toplantılarda gerçek zamanlı bağlantı sağlar.

## Call Agent

IP telefonlar için arama kontrolü sağlar. Bant genişliği kontrolü yönetimi ve adres dönüşümü yapar.Gatekeeper router üzerinde çalışırken call agent bir server platformu üzerinde çalışır.

## Application Server

Ses,Mail anlık mesajlaşma gibi uygulamaları sunar.

##PBX (PRIVATE BRUNCH EXCHANGE)

Dahili telefonlardan oluşan telefon ağını harici ve mobil telefon hatlarına bağlayan sistemdir.İç ağlarda Santral olarak kullanılmaktadır.

# VoIP Birleşenleri ve Protokolleri

VoIP ağlarının anlaşabilmesi için sinyalleşme ve sinyalleşmede kullanılan bir takım protokollerin anlaşılması gerekmektedir.Sinyalleşme iki son nokta arasında bağlantıların kurulması,devam ettirilmesi,oluşturulması, kontrol bilgilerinin karşılıklı olarak değişitirilmesi,bağlantıların gözlemlenmesi için kullanılan teknolojidir. VoIP teknolojileri  sinyalleşme için  bazı seçenekler kullanılır.H.323,SIP,MGCP,SCCP gibi protokoller sinyalleşme için kullanılabilmektedirler.

## H.323 Protokolü

IP ağlarda gerçek zamanlı voice,video,ses,fax,paketleri taşımak için kullanılan protokoldür.Ayrıca uçtan uca sinyal tanımlaması yapabilir.

## MGCP

PSTN Gateway kontrolü için bir metottur.Dış arama kontrol cihazlarına bağlı olan VoIP Gateway kontrol eder.

## SCCP

Cisco özellikli bir protokol olmakla birlikte Cisco Communication Manager ve Cisco IP telefon arasında kullanılır.

## SIP

SIP IETF standardı bir protokoldür. HTTP ile bazı karakteristik özellikleri aynıdır. 7. katmanda 
çalışan bir client-server programıdır. SIP INVITE ve ACK gibi mesajlara sahiptir. SIP bir 
oturumdaki iletişimin türünü sınıflandırmak için SDP (session description protocol) kullanılır. SIP 
kullanıcının yerini belirleme, arama yapma, kullanıcıya ulaşma, kullanıcı cihazların özelliklerini 
anlama gibi işlemler için kullanılır. Asıl amacı oturum başlatma sürdürme, kontrol etme ve 
sonlandırmadır. SIP adresleri email ya da telefon numarası gibi gözükebilirler, örneğin 
cagatay@domain.com, 0 123 345667@domain.com gibi.

|Invite Arama oturumunu başlatmak için kullanılan paket

Paket | Görevi | 
---------|----------|
Invite | Arama oturumunu başlatmak için kullanılan paket |
 ACK | Invite isteğini onaylayan paket.
 Cancel   | Beklemede olan paketi sonlandııran paket.
Register | Kullanıcıyı SIP sunucusuna kayıdeder.
Options | Aranan kişi hakkında bilgi verir.
Bye | İki kişi arasında oturumu sonlandıran paket.

Kod Numarası | Görevi
-------------|---------|
1xx | İsteğin alındığını ve işleme tabi tutulduğunu belirtir.
2xx| İsteğin kabul edildiğini ve başarıyla işleme alındığını bildirir.
3xx| Yönlendirme cavabıdır.
4xx| Hata mesajıdır.Sunucuya ulaşılmadığını yada bir problem olduğunu gösterir.
5xx| Hata mesajlarıdır.Ağ geçitine ulaşmaması buna örnek olarak verilebilir.
6xx| Global hata mesajı cevabı

## Media Transmission Protokols

Voice paketleri gerçekte RTP ve RTCP gibi protokoller üzerinden taşınmaktadırlar.

## RTP(Relaible Transfer Protokol)

Video ses paketlerinin gerçek zamanlı,uçtan uca çalışmasını sağlayan protokoldür.Video ve ses verilerinin taşıma işlemi hızlı gerçekleşmesi gereken bir işlem olduğundan dolayı RTP UDP protokolünü kullanır.

# VoIP Saldırı Yöntemleri 

SIP protokolünde,arama isteğini başlatan kullanıcı, sunucuda oturum açabilmek için  INVATE isteğinde bilgilerini şifrelemeden gönderdiği için,bu bilgiler arada dinleyiciler tarafından elde edilebilmektedir.

Bu güvenlik açıklığı sebebiyle,biir çok yöntemle saldırı düzenlenebilir,iletişim engellenebilir veya istenmeyen farklı durumların ortaya çıkarılmasına sebep olabilir.

VoIP sistemi,gerçek zamanlı iletişimi  içerisinde barındırdığı için,yapılacak olan güvenlik önlemleri de tek sefere mahsus güvenlik önlemleri olmayacaktır.Sağlanacak güvenlik önlemleri,gerçek zamanlı olmalıdır.

SIP ya da VoIP saldırıları,diğer iletim metotlarında olduğundan çok  daha farklı şekilde zarar görmektedir.Ses iletimi anlık yaşandığı için,bir yerde depolanmamaktadır. veya tekrardan iletmek çok mümkün olmamaktadır.SIP trafiği paketler içerisinde taşındığı için,paketlerin yanlış adrese yönlendirilmesi veya manüple edilerek ilgili adrese yönlendirilmesi gibi durumlar orataya çıkabilmektedir.

# Dos ve DDoS Saldırıları

DoS ya da DDoS saldırılarında,mevcut SIP sunucusunun hizmetinin kesintiye uğraması veya servis yanıltma amaçlanır.Bu atakta,yeterli bilgileri ele geçirdikten sonra,sunucu savunmasız kalmaktadır.Aynı anda birden fazla saldırganın hedef sunucuyu etkisiz hale getirmek için yaptığıDDoS saldırıları ise SIP için en çok karşılaşılan ve en ağır sonuçlar doğuran saldırı çeşitidir.

SIP için yapılan DDoS saldırıları,çok fazla sayıda REGISTER ya da INVITE paketinin sunucuya gönderilmesi,SIP paketinin yapısının değiştirilmesiya da SIP durum kosları değiştirilmesi olarak karşımıza çıkabilir.Özellikle açık internet erişimi bulunan ve network dışından da çağrı kabul eden sunucular bu saldırılara karşı savunmasızlardır.Sunucu tarafından imzalanmış ya da şifrelenmiş ses paketleri fahi bu saldırıdan etkilenmektedir.Paket iletiminin gerçek zamanlı gerçekleştiği  bu sistemlerde zararlı yazılımlar DDoS saldırıları ile çoğalarak sistem trafiğini arttırır ve sistem cevap veremez hale gelir.**SIP paket tekrarlama saldırısı,SIP paket ekleme saldırısı,TLS bağlantı sıfırlama saldırısı,flood saldırıları,sahte mesaj saldırıları en bilinen Dos saldırılarındandır**.Bu tür saldırılara karşı SIP destekli güvenlik duvarı kullanılarak,ayrıca IDS ve IPS cihazlarına SIP odaklı kurallar ekleyerek detaylı ağ analizi yapılması sağlanabilir ve saldırılar önlenebilir.

# Telekulak Saldırıları

Bu saldırıda ağa erişerek veri paketlerine erişim ve kişisel bilgilere ulaşılması amaçlanmaktadır.Saldırgan sistem üzerindeki zafiyet ve açıklıkları bulmak amacıyla da telekulak saldırısı gerçekleştirebilir.VoIP teknolojisinde,erişim kolay olması nedeniyle IP ağına erişimi bulunan saldırgan iletilen paketleri görüntüleyebilir ve yakalayabilir.Bazı paket yakalama programları ile bu saldırı rahatlıkla gerçekleştirilebilirç

Örneğin, Wireshark gibi uygulamalarda ağı dinleyen bir saldırgan çok rahatlıkla sizin paketlerinizi yakalayabilir,paketlerinizin üzerindeki bilgileri parçalayarak elde edebilirçSonrasın da bu paketler üzerinde manipülasyon yaparak sizin adınıza başka kullanıcılar aktarabilir.

Bazı protokol analiz edici programlar,yanlızca VoIP trafiğini dinlemek ve daha sonraki analizler için saklamak üzerine konfigüre edilebilir.VoIP kullanımı ,geleneksel telefon sistemindeki Tapping teknikleriyle karşılaştırıldığında geleneksel telefon sistemindeki telekulak saldırısında,saldırı ile bir telefon görüşmesine erişebilirken VoIP ağına yapılan bir telekulak saldırısı ile birden fazla VoIP oturumuna(telefon konuşmasına)ulaşılabilir.Bu yönden VoIP ek riskler getirmişlerdir.

VoIP ağında telekulak saldırısını kolaylaştıran eklentilerin başında,sesin iletiminde kullanılan RTP protokolünde şifreleme ya da asıllama yapılmıyor olmasıdır.RTP başlığında PT(payload type) alanında kullanılan codec ile ilgili bilgi vardır.İnternette rahatça erişilebilen,RTP trafiğini kaydetmeye yarayan araçları kullanarak RTP trafiğini kesip kaydeden birisi,codec bilgisi de elinde bulunduğundan,bu RTP trafiğini daha sonra decode edip dinleyebilir ya da tekrarlama saldırıları gibi birçok saldırı amacıyla kullanılınabilir.

# Ortadaki Adam Saldırıları (Man in the Middle Attack)

Ortadaki adam saldırısı araya girenin, taraflar tarafından haberi olmadan iki taraf arasındaki mesajları okuyabilmesi ve değiştirebilmesi olarak tanımlanabilir.Ortadaki adam saldırısı,DoS yada telekulak gibi diğer saldırı türlerini gerçekleştirmek içinde kullanılabilir.

Call Hijack,saldırıda bulunan taraflardan birinin yerine geçmesi durumudur.Call hijact saldırısında bulunan biri,şüpheleri arttırmadan MITM saldırısına dönüştürebilirç

Bu saldırılar,farklı şekillerde gerçekleştirilebilir:

* 3xx cevap kodlarını kullanarak(call redirect)
* Kayıt bilgilerini değiştirmek (registration manipulation)

# Kayıt Bilgilerinin Değiştirilmesi (Change of Register Data)

Bu saldırı ile sistemdeki kullanıcıların kayıt bilgilerini değiştirerek,yapılan tüm isteklerin farklı bir sunucuya gitmesi sağlanarak istekler yönlendirilebilir.SIP mesaj içeriğinde bulunan,isteğin kimden yapıldığına dair bilgiler değiştirilerek sahte kullanıcı kayıtları yapılabilir.Kullanıcı veri bloğu iletişim kanalları UDP mesajlarının kontrol olmasından dolayı saldırgan hem kendini sisteme kaydedebilir hemde sistemde ki aktif kullanıcıları kendine yönlendirebilir.Birçok SIP tabanlı sistemde herhangibir yetkilendirme istenmediği için bu saldırı rahatlıkla gerçekleştirilebilmektedir.Bu saldırıyı başarıyla gerçekleştirdikten sonra ortada ki adam saldırısı gerçekleştirmek de daha kolay hal almaktadır.Yetkilendirme yaparak söz konusu saldırının önüne geçilebilir.Bu konuda önlem alınmaması durumunda, saldırgan kendisini SIP sunucusu olarak tanıtarak,bir recorder aracılıyla kullanıcılar arasındaki görüşmeleri kaydedebilir veya dinleyebilir.

# Tekrarlama Saldırıları (repeat Attack)

SIP mesajlarının ele geçirilmesi ve belli bir süre sonra aynı mesajların geri gönderilmesi ile gerçekleştirilir.Genelde yetkili bir kullanıcının bilgilerinin çalınması ve onun yerine geçmesi ile  gerçekleştirilir.Bu saldırı ile tek bir arama için oturum başlatılacakken birden çok oturum başlatılması ile birden çok arama gerçekleştirilmiş olur bu da gerek sistemi meşgul etmesi gerekse maddi açıdan kayıp oluşturması nedeni ile önlem alınması gereken bir durumdur. Yine aynı şekilde yetkilendirme ve şifreleme senaryoları ile bu saldırı türü engellenebilir.

# Oturum Bozma Saldırıları (Session Corruption Attack)

Var olan bir sinyalleşme ya da oturumu kesmek amacıyla gerçekleştirilir. İletişim halinde bulunan kullanıcılar arasına saldırganın girmesi ve aradaki bağlantıyı, BYE mesajı yollayarak bitirmesi ile sonuçlanır [16]. HTTP Digest Authentication kullanılmış olsa dahi saldırgan zararlı ACK ya da CANCEL istekleri ile oturumların düşmesine neden olabilir. Güvenli oturum kurulması sağlanarak ve gerekli yetkilendirmeler yapılarak oturuma dâhil olunması engellenebilir ve bu sayede de oturumun devamlılığı sağlanabilir.

# Yanıltma (Spoofing)

Spoofing, IP paketlerinin, yanlış kaynak adresi kullanılarak gönderilmesidir. Saldırıda bulunan kişinin IP adresini gizlemesi; başka bir taraf ya da kişiyi saldırıyı yapan olarak göstermesi; güvenilir bir kullanıcı gibi görünmesi yanında network trafiğini dinleme ya da ele geçirme ve ortadaki adam saldırısı gibi saldırıları gerçekleştirmek için kullanılabilir.

Bu tür yanıltma saldırısındaki bir risk, kimlik hırsızlığıdır. Örneğin bir müşteri, sipariş vermek üzere bir yeri arayıp telefonda kredi kartı numarası gibi önemli bilgilerini verebilir.  müşteri, satış departmanı yerine, onun yerine geçmiş olan saldırganla konuşmaktadır. Bu, klasik bir ‘man-in-the-middle spoofing’ saldırısıdır.Başka yanıltma türü de arayan ID’si (Caller ID) ya da CLID (call line identification) değiştirilerek yapılabilir. Yalancı bir kullanıcının ya da varolan bir kullanıcının telefon numarası değiştirilebilir. Bu da; arayan numaraya göre asıllama yapan sistemlere zarar vermek için kullanılabilir. Bazı VoIP cihazları periyodik olarak belli bir sunucudan firmware yüklemek üzere konfigüre edilmiş olabilir. Spoofing ile cihaza yanlış bir firmware dosyası yüklenmesi sağlanabilir.