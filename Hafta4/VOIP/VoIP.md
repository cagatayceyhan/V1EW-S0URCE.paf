#VoIP Nedir?

![](https://healthbeyondshowcase.org.au/wp-content/uploads/2018/05/VoIP-Logo-RichBlue.png)

Açılımı **Voice Over Internet Protocol** olan VoIP,kurumsal yerel alan ağları veya geniş alan ağları üzerinden ses ve multimedya içeriğinin iletilmesini sağlayan bir grup teknoloji ve metodolojidir.VoIP uç noktaları;özel masaüstü VoIP telefonlarını,PC'lerde ve mobil cihazlarda çalışan softphone uygulamalarını ve WebRTC etkin tarayıcılarını içerir.VoIP codec bileşenlerinin kullanılarak sesi veri paketine yerleştirir,paketleri bir ip ağı üzerinden iletir ve paketleri bağlantının diğer ucunda sesi geri sıkıştırır.VoIP,geniş bant ve özel ağlar üzerinden ses hizmeti sunulmasını ve işletmelerin tek bir ses ve veri ağı kullanmasını sağlar.VoIP ayrıca,kesintiler,uç noktalar ve ağlar arasında yedek iletişimi takiben hızlı yük devretmeyi etkinleştirerek IP tabanlı ağların esnekliğinide desteklemektedir.

VoIP altyapısı,standartları ve VoIP uç noktaları tipik olarak,sıkıştırılmamış paketlerin iletilmesi için standart olan G.711 veya sıkıştırılmış paketlerin standartı olan G.729 gibi Telekominikasyon Birliği(ITU) standart codeclerini kullanır.

#VoIP Penetrasyon Testi Nedir?

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

##VoIP Gatekeeper

Bant genişliğinin kontrolü,yönetim ve adres değişimleri buradan yapılır.Arama kabul kontrol işlemi de bu cihazda yapılır.

##VoIP Gateway

VoIP ve VoIP olmayan ağlar arasındaki geçişi sağlar.Analog ve Dijital VoIP cihazları ile fiziksel bağlantısı vardır.Örneğin VoIP Gateway  DLS hat ile PSTN hattın bağlanması için gereklidir.IP ağlar ile PBX arasında bağlantı kurulmasını sağlayarak analog sinyal ile gelen sesi dijital sinyale çevirdikten sonra IP üzerinden taşınmasına olanak sağlayan cihazdır.

## MCU (MULTIPOINT CONTROL UNIT)

MCU farklı fiziksel bölgelerden yapılan video konferans ya da toplantılarda gerçek zamanlı bağlantı sağlar.

## Call Agent

IP telefonlar için arama kontrolü sağlar. Bant genişliği kontrolü yönetimi ve adres dönüşümü yapar.Gatekeeper router üzerinde çalışırken call agent bir server platformu üzerinde çalışır.

## Application Server

Ses,Mail anlık mesajlaşma gibi uygulamaları sunar.

##PBX (PRIVATE BRUNCH EXCHANGE)

Dahili telefonlardan oluşan telefon ağını harici ve mobil telefon hatlarına bağlayan sistemdir.İç ağlarda Santral olarak kullanılmaktadır.

# VoIP birleşenleri ve protokolleri

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