OSI Referans Modeli
------------------------------------------
Tarihçe
--------------------------------------
TCP/IP ilk olarak Amerika Savunma Bakanlığı'nın(DoD) veri iletişim ihtiyacını karşılaştırmak için tasarlanmıştır.1960'lı yılların sonunda Amerika Savunma Bakanlığına bağlı çalışan ARPA-Advancecd Research 
Projects Agency (ARPA) ABD'de bulunan üniversitelere,ağ üzerinden veri alışverişinde bulunmak amacıyla,üretici markalardan bağımsız bir protokol bulmak amacıyla çalışmaya başladı. Bu çalışmalar neticesinde ARPANET
kuruldu.
1973 yılında ağ için bir protokol seti geliştirmek amacıyla Stanford üniversitesinde daha sonra Bolt Beranek Newman  ve  University College London 'in da dahil olduğu -bir internetworking projesi başlatıldı.1978 
kadar TCP'nin dört uyarlaması gerçekleştirildi ve denendi.1980 de bu küme sabitleşti ve ARPANET'e bağlı bilgisayarlar arasındaki iletişim kolaylaştırıldı.TCP/IP nın yanı sıra 1978 Yılında OSI Referans modeli ISO 
tarafından kullanıma sunulmuştur.1984 yılında yeniden düzenlenerek OSI (Open System Interconnection) referans modeli olarak yayınlanmıştır.

Bilgisayar ağları kullanılmaya başlanmalarıyla beraber farklı üreticilerin birbirlerinin ağlarına entegre olabilmek için ortak bir standardın gerekliliği ortaya çıkmıştır. Önceleri firmalar kendilerine
özel ağ sistemleri geliştirip bunları bir paket halinde müşteriye sunuyorlardı. Fakat bu çok pahalıydı ve dışarıya kapalı bir sistem oluşturmaktaydı. Aslında kendi içlerinde çok sağlıklı çalışabilmelerine karşın
kendi dışındaki ağlarla iletişim kurmaları çok zor ya da imkânsızdı. Örneğin IBM işletim sistemleri, IBM network aygıtları kullanarak kendi aralarında iletişim kurabiliyorlardı. 
Ağ sistemlerinde arzın talebi karşılayamaması ve ağ piyasasında donanım üreticilerinin baskısı sonucunda, ağ sistemlerinin işlevleri için standart bir modelin oluşturulması gerektiği anlaşıldı. 
Bu nedenle ISO (International Organization for Standardization) tarafından 1978 yılında bilgisayar ağları standardı olan OSI referans modeli ortaya konmuştur. İlk olarak 1978 yılında ortaya çıkarılan bu
standart 1984 yılında yeniden düzenlenerek OSI (Open System Interconnection) referans modeli olarak yayınlanmıştır. Model yaygın olarak kabul görmüş ve network işlemi için bir kılavuz olmuştur.
OSI Modeli sadece bir standarttır. Eskiden olduğu gibi isteyen kendi başına bir ağ iletişim modeli geliştirebilir. Ancak OSI modeli referans alınmadıysa diğer ağlarla iletişimi zor olacak değişik 
üreticiler bu ağ sistemi için donanım ve yazılım üretemeyecekler demektir.

OSI referans modeli bilgisayar ağlarında iletişim ortamından (kablolu, kablosuz) kullanıcıya kadar olan işlemleri 7 katmana ayırmıştır.Bu katmanlar TCP/IP 4 Katmana ayrılmıştır.

![osivstcpip](https://i0.wp.com/get-itlabs.com/wp-content/uploads/2014/02/Cisco-OSI-TCP-IP-STACK.jpg)

# OSI Katmanları

![](https://www.firatboyan.com/images/Essays/Uploads/PreviewImage_OSI-model.jpg)
---------------------------------------------------
**1.Katman**: **Fiziksel Katman** : Fiziksel katman veri parçacıklarının(bit)kablo,fiber,hava gibi iletim ortamlarında nasıl iletileceğini tanımlar.Gönderen tarafta fiziksel katman 1 ve 0 'ları bir iletim ortamının
anlayacağı şekilde(elektrik sinyali,radyo sinyali,ışık)gönderir,alıcı tarafta fiziksel katman iletim ortamında okuduğu bu sinyalleri 1 ve 0 haline getirir.Farklı üreticilerin ağ donanımlarınınbirbirleri ile sorunsuz 
iletişim kurmaları için, giden gelen veri bitlerinin farklı marka donanımları için aynı şeyi ifade etmesi gerekmektedir.Bu yüzden belirli standartların oluşturulması, aynı protokollerin kullanılması gerekmektedir.


**Gönderim işleminden önce nasıl(ortam, özellik) gönderileceğine karar verilmelidir ki işte bu işlemi gerçekleştiren katman fiziksel katmandır. Kablolu bağlantı için kablo türü, kablosuz bağlantı için iletim kanalı seçimi vb. kararlar bu katmanda verilir. Bitler, elektrik, radyo sinyalleri, ışık gibi pek çok yolla gönderilebilir. İletimin gerçekleşmesi açısından önemli unsur ise taşıma ortamıdır. Taşıma ortamı hem alıcı hem gönderici için aynı olmalıdır. Elektriksel yolla iletilen veri radyo sinyalleri olarak alınırsa iletim düzgün şekilde gerçekleşemez. Taşıma ortamı iletim için tek unsur, tek şart değildir. Voltaj değeri veri iletim hızı gibi değerlerin de uygun şekilde tanımlanması gerekir.**

|Kullanılan standartlar|     |
|-----------------|----------------------|
|Standart|Açıklama| 
|EIA/TIA-232| DTE ile DCE arasındaki seri ikili tek sonlu veri iletimi ve sinyalleme için kullanılan seri iletişim standardının genel adıdır.|
|EIA/TIA-449|Uç veri cihazları ve veri haberleşme cihazları arasındaki işlevselliğin ve mekanik karakteristiğin arayüzünü tanımlar.|
|RJ45:RJ45| Ethernet ağı için yaygın olarak kullanılan bir konnektör türüdür.Ethernet kablosu ile NIC kartına bağlanılmasını sağlar.|
|FDDI|Fiber Distributed Data Interface  yüksek hızlı bir bilgisayar ağıdır. Özellikle fiberoptik kablo hatlarında kullanılır.|
|Ethernet| Yerel ağlar için kullanılan Veri Çerçevesi tabanlı bilgisayar ağı teknolojileri ailesidir.|

---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
**2.Katman : Veri Bağlantısı Katmanı** : Bu katman,kaynaktan gönderilen verinin çerçeve(frame) haline getirilerek hedef adresine iletilmesini sağlar.Bu katman Media Access Control(MAC) ve Logical Link Control(LLC)
olmak üzere iki alt katmandan oluşur.MAC alt katmanı her bir network kartında benzersiz 48 bitlik MAC adresini kullanır.Veri paketinde bulunan kaynak ve hedef MAC adresleri ile haberleşmenin doğru yapılmasını sağlar.LLC alt katmanı bir üst katman için geçiş görevini üstlenir.İki katman arasındaki haberleşmeyi mantıksal portlar SAPs(Servis Access Points) oluşturarak sağlar.Bu katmanda kullanılan CRC hata denetim protokolü ve CSMA/CD çakışma protokolü ile gönderilen verinin hata ve çakışma denetimi yapılır.

**Bir data frame incelenirse Data (Veri), Header (Başlık), Trailer (Kuyruk) olmak üzere temel olarak 3 bölümden oluştuğu görülür. İçerikte hedef ve kaynak bilgileri, hata kodunu tutan değer CRC (Cyclic Redundancy Code ), verinin kendisi, başlangıç ve bitişi belirten özel işaret bitleri gibi yapılar vardır. 2. katmandaki çoğu işlem ağ kartı içerisinde gerçekleşir. Alınan, gönderilen data frameler için onaylama bekler. Onaylama alınmayanlar için tekrar gönderim işlemini gerçekleşir.LLC ve MAC bölümlerine gelecek olursa üst kısımda LLC alt kısımda MAC bölümü bulunur. LLC Layer 3 ve Layer 2 arasındaki bağlan tıyı sağlar. Bağlantıda kullanılan protokole (UDP, TCP/IP) uygun erişim noktaları yani mantıksal portlar (Service Access Points, SAPs) oluşturur. Böylece hedef ve kaynak cihazlar karşılıklı olarak aynı protokoller üzerinden bağlantı gerçekleştirir LLC, bunu verinin çerçeve yapısına (Destination Service Access Point — DSAP, Source Service Access Point — SSAP) ekleyerek sağlar. Bu bilgileri ekledikten sonra veriyi bir alt bölüm olan MAC’e yollar. “Onay alınmayan data frameler tekrar gönderilir” durumu ise yine LLC’nin sorumlulukları arasındadır. Yine akış kontrolü (Flow Control) yani karşı tarafın alabileceği maksimum veri paketi sayısının aşılmamasını sağlayabilmek de LLC’nin görevlerindendir.LLC ve MAC bölümlerine gelecek olursa üst kısımda LLC alt kısımda MAC bölümü bulunur. LLC Layer 3 ve Layer 2 arasındaki bağlan tıyı sağlar. Bağlantıda kullanılan protokole (UDP, TCP/IP) uygun erişim noktaları yani mantıksal portlar (Service Access Points, SAPs) oluşturur. Böylece hedef ve kaynak cihazlar karşılıklı olarak aynı protokoller üzerinden bağlantı gerçekleştirir LLC, bunu verinin çerçeve yapısına (Destination Service Access Point — DSAP, Source Service Access Point — SSAP) ekleyerek sağlar. Bu bilgileri ekledikten sonra veriyi bir alt bölüm olan MAC’e yollar. “Onay alınmayan data frameler tekrar gönderilir” durumu ise yine LLC’nin sorumlulukları arasındadır. Yine akış kontrolü (Flow Control) yani karşı tarafın alabileceği maksimum veri paketi sayısının aşılmamasını sağlayabilmek de LLC’nin görevlerindendir.**

**MAC bölümü ise adından da anlaşılacağı üzere veri çerçevesine hedef ve kaynak cihazların MAC adresini ekler. Bu fiziksel bağlantıda daha güvenilir iletişimler kurmayı sağlar. Çünkü her bir cihaz için eşsiz MAC adresleri mevcuttur. Yine de bu durumda layer 2 için zaafiyetler bulunmaktadır. Veri iletimi sırasında bir hata meydana gelirse bunun bilgisi CRC içerisinde tutulur. Hatadan kasıt verinin iletim ortamı içerisinde bozunması olabilir, ya da gönderilen ve alınan verinin aynı olmaması durumu da olabilir.**

**MAC bölümü, mac adreslerinin yanında bir de işte bu CRC kodunu ekler. Gönderici tarafta veri paketini fiziksel katmana aktarırken; alıcı tarafta veriyi LLC’ye yönlendirir.**

**Saldırılarda MAC ve ARP ataklarının da önemli bir yeri vardır. MAC ve ARP protokollerine ve bu protokollere değinen saldırılara burada detayıyla yer verilmeyecektir. Ancak örnek vermek gerekirse MAC Flooding, ARP Poisoning/ARP Spoofing gibi saldırılar katman 2 saldırılarındandır.**

|Kullanılan standartlar|     |
|-----------------|----------------------|
|Standart|Açıklama| 
|IEEE 802.2:IEEE 802.2| Mantıksal bağlantı kontrolünü OSI Modelinin veri bağlantı katmanının üst kısmı olarak tanımlayan ISO / IEC 8802-2 standardının orijinal adıdır.|
|HDLC: HDLC| OSI 2. katmanında yer alan bir iletim protokolüdür. HDLC, PPP gibi WAN iletişiminde paketlerin yerine nasıl ulaştırıldığını belirleyen yaygın protokollerden birisidir. HDLC Ethernet protokolüne göre çok basittir.Temel noktadan noktaya iletişim protokolü olarak da kabul edilebilir.|
|Frame Relay| Standart bir geniş alan ağı teknolojisidir. Verilerin eski teknolojilere nispeten yüksek hızlarda dijital networkler üzerinden iletilmesini sağlar.Eskimiş ve artık yaygın olmayan bir teknolojidir. Birden fazla kullanıcının haberleşme kaynaklarını paylaşması esasına dayanır.|

---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

**3.Katman : Ağ Katmanı** : Bu katman ağ adresi(IP adress) verinin kaynaktan hedefe ulaşmasını sağlar.Kaynak ve hedef IP adresi eklenmiş şekline paket ismi verilir.IP paketi adreslerle birlikte paketin toplam boyutu,
TTL,servis tipi,versiyon,hata denetimi gibi bilgiler barındırır.Ağ ortamında veriyi yönlendiren yönlendiriciler(router) ve yönlendirme algoritmaları bu katmmanda çalışır.

Kullanılan protokoller şunlardır;

|Kullanılan standartlar|     |
|-----------------|----------------------|
|Standart|Açıklama| 
|IP| IP adresi, interneti ya da TCP/IP protokolünü kullanan diğer paket anahtarlamalı ağlara bağlı cihazların, ağ üzerinden birbirleri ile veri alışverişi yapmak için kullandıkları adres.|
|IPX| Novell Netware istemcileri ve sunucuları tarafından kullanılan ağları birbirine bağlayan bir Novell protokolüdür. Ek olarak veri paketlerini göndermek için en iyi bağlantı sunan, ancak veri teslimini garanti etmeyen bir veri birimi protokolüdür.|
|AppleTalk| Apple Inc. tarafından Macintosh bilgisayarları için geliştirilmiş, durdurulan özel bir ağ protokolleri paketidir. AppleTalk, yerel alan ağlarının önceden kurulum yapılmadan veya herhangi bir tür merkezi yönlendirici veya sunucuya ihtiyaç duyulmadan bağlanmasına izin veren bir dizi özellik içerir.|
|ARP| Adres Çözümleme Protokolü (ARP), Internet Protokolü adresinin (IP adresi) yerel ağda tanınan fiziksel makine adresine eşlenmesi için kullanılan bir protokoldür. ARP önbelleği olarak adlandırılan bir tablo,her MAC adresi ile karşılık gelen IP adresi arasında bir ilişkiyi sürdürmek için kullanılır.ARP, bu korelasyonu yapmak ve her iki yönde adres dönüşümü sağlamak için protokol kurallarını sağlar.|
|RARP|RFC 903 dosyasında tanımlanmış olan RARP (İngilizce Reverse Address Resolution Protocol, yani Ters Adres Çözümleme Protokolü), bir TCP/IP ağında MAC adresleri ile IP adresleri arasındaki bağı yapmak için kullanılır. Sanılanın aksine, RARP "saf" bir iletişim için kullanılmaz: RARP'ın istek sorusunda genelde soran ve soruşturulan MAC adresi olarak aynı MAC adresi yazılır, dolayısıyla RARP'ın asıl amacı lokal makinenin IP adresini öğrenebilmektir.Öte yandan, cevapta sadece o makinenin IP adresi bilinecektir; yani ağ maskesi, varsayılan ağ geçidi ve DNS sunucusunun adresi gibi girdiler olmayacaktır. Dolayısıyla,RARP ile IP adresini elde edebilmiş olan bir makine, bu bilgiye sahip olmasına rağmen iletişim kurmakta güçlük çekecektir.Bu bilgilere de ulaşabilmek için, günümüzde RARP yerine DHCP kullanılır (RARP ise hiçbir şekilde kullanılmaz). Öte yandan, çok basit veya çok eski kimi cihazlar hala RARP kullanıyor olabilir.|
|ICMP| Genel olarak; TTL süresi dolduğu zaman paketin sahibine bildirim yapma, herhangi bir durumda yok edilen paket hakkında geribildirim sağlama, hata oluşumlarında geribildirim sağlama, paketbaşka bir yoldan gideceği zaman geribildirim sağlama gibi görevler üstlenir. Örneğin, sorun çözümü için sıkça kullanılan Ping ve Tracert komutları ICMP Echo Request ve ICMP Echo Reply mesajları ile çalışır.|
|RIP| Router Information Protocol, yani Yönlendirme Bilgi Protokolü anlamına gelen RIP, bir TCP/IP ağındaki router'ların birbirini otomatik olarak tanımasında kullanılan bir iç yönlendirme protokoldür.Aynı zamanda uzaklık vektör algoritmasına dayanır ve IGP'nın bir uygulamasıdır.|

-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

**4.Katman : İletim Katmanı** 
**Layer 4 oturum ve uygulama katmanları için standartlaştırılmış erişim sağlar. Yani iletişim ağının özelliklerine göre herhangi bir düzenleme yapılması gerekmez. Böylece üst katmanlar teknolojik değişikliklerden izole edilmiş olur. Temel olarak taşıma katmanı, gönderici tarafta üst katmanlardan gelen veriyi parçalar; alıcı tarafta ise gelen veri parçalarının doğru sırayla birleştirilmesi işlemlerinden sorumludur denebilir. Layer 4te üst katmandan gelen veriler segmentlere dönüştürülür. Segmentler ağ paketi boyutundadır.**

**Taşıma katmanı veri akışının kalitesini artırma (QoS = Quality of Service), güvenilirlik, hata kontrolü, zamanında ulaştırma ya da bunun kontrolü, akış denetimi, çoklama gibi işlemler gerçekleştirir. Güvenilirlik durumu taşıma katmanında kullanılan protokolle alakalı bir durumdur. Örneğin TCP/IP protokolünde cihazlar arası bir denetim söz konusu iken UDP protokolünde herhangi bir denetim yapılmaz. Taşıma işlemi, mesajın alıcı taşıma katmanına herhangi bir hata olmadan ulaşmasını sağlamak için uçtan uca gerçekleştirilir eğer hata varsa bu, mesajın yeniden iletilmesi ile düzeltilir. Çoklama ise aynı ağ üzerinde birden fazla uygulamanın kullanılmasına izin verir. Ayrıca bazı uygulamalar paket yerine direkt baytları kabul eder bu durumda da taşıma katmanı bayt odaklı veri akışını yönetebilir.**

Önemli protokoller şunlardır:

|Kullanılan standartlar|     |
|-----------------|----------------------|
|Standart|Açıklama| 
|TCP| TCP (Transmission Control Protocol) bilgisayarlar arasındaki iletişimin, küçük paketler hâlinde ve kayıpsız olarak gerçekleştirilmesini sağlayan bir protokoldür. Aslında TCP (Transmission Control Protocol) protokolünün en önemli özelliği kimlik doğrulaması yapması ve veriyi karşı tarafa gönderirken veya alırken verinin bütünlüğünü sağlamasıdır. Gelişmiş bilgisayar ağlarında ortaya çıkan kayıpları önlemek için TCP protokolü yazılmıştır. HTTP, HTTPS, POP3, SSH, SMTP, TELNET ve FTP gibi günlük hayatta sıkça kullandığımız protokollerin veri iletimi TCP vasıtasıyla yapılır.UDP protokolüne göre yavaş ancak güvenli bir veri iletişimi sağlar. UDP (User Datagram Protocol)  protokolünde ise verinin karşı bilgisayar tarafından alınıp alınmadığı kontrol edilmez ve veri iletişimi çok hızlı bir şekilde gönderilir.|
|UDP|: TCP/IP protokol takımının iki aktarım katmanı protokolünden birisidir. Verileri bağlantı kurmadan yollar.Gelişmiş bilgisayar ağlarında paket anahtarlı bilgisayar iletişiminde bir datagram modu oluşturabilmek için UDP protokolü yazılmıştır. Bu protokol minimum protokol mekanizmasıyla bir uygulama programından diğerine mesaj göndermek için bir prosedür içerir. Bu protokol 'transaction' yönlendirmelidir. Paketin teslim garantisini isteyen uygulamalar TCP protokolünü kullanır.Geniş alan ağlarında (WAN) ses ve görüntü aktarımı gibi gerçek zamanlı veri aktarımlarında UDP kullanılır.UDP bağlantı kurulum işlemlerini, akış kontrolü ve tekrar iletim işlemlerini yapmayarak veri iletim süresini en aza indirir.|UDP ve TCP aynı iletişim yolunu kullandıklarında UDP ile yapılan gerçek zamanlı veri transferinin servis kalitesi TCP'nin oluşturduğu yüksek veri trafiği nedeniyle azalır.
|SPX| Ağlar Arası Paket Değişimi, küçük ve büyük ağlar için paket anahtarlama ve sıralamayı sağlayan bir dizi ağ dizini ve NetWare ağında paket sıralamasını işleme protokolüdür.|
|RTP| RTP, gerçek zamanlı ses, görüntü ya da simülasyon verilerinin uçtan uca taşınmasını sağlayan protokoldür. Bu protokol IETF nin Audio-Video Transport çalışma grubu tarafından geliştirildi.|
|H.323| H.323, herhangi bir paket ağında görsel-işitsel iletişim oturumları sağlamak için protokolleri tanımlayan ITU Telekomünikasyon Standardizasyon Sektörünün bir Tavsiyesidir.

----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

**5 - Katman : Oturum Katmanı**: Bu katman ,kaynak  ve hedef arasındaki iletişimi başlatır,yönetir ve sonlandırır.İstemciden kullanılan her bir ağ bağlantısı e-mail,web browser,ftp gibi her bir uygulama ayrı bir oturum açarak verilerin birbirine karışması engellenir.

**Her cihaz tek bir cihaz ile iletişim halindedir diye bir kural yoktur. Yani bir cihaz eş zamanlı olarak birden fazla cihazla haberleşme içinde olabilir. Aynı şekilde bir uygulama da birden fazla uygulama içerisinde olabilir. Katman mantığını anlatmaya çalışırsak; bu durumda cihazlar ve uygulamalar arası iletişimin karışmaması için her bir iletişime birer oturum(session) gözüyle bakılır. Günlük hayattan bir örnekle session mantığını anlamaya çalışalım. Siz bir konuşmacı olarak bir davete katıldınız. Bu konuşmaya bir çok davetlinin geleceğini düşünürsek her birinin yakakartı bulunmalıdır ki siz de, davetli de o an için kiminle iletişimde olduğunuzu anlayın. Sonuçta A kişisinden almak istediğiniz bilgiyi, B kişisine sormak büyük bir karışıklığa sebebiyet verebilir. İşte oturumlar da buna benzer bir mantıktadır. Anlık olarak iletişimde bulunulan her bir uygulama adına bir oturum (session) oluşturulur. Böylece çok iletişimli bir ortam içerisinde büyük bir karışıklık önlenir. Çünkü her bir uygulamanın bir yakakartı gibi oturum kimliği bulunur. Oturum katmanı iki uygulama arasındaki sohbeti yönetir ve senkronize eder, sonlandırır. Eğer senkronizasyon işlemi gerçekleştirilmezse veri kayıpları, iletişimin koparılması gibi sorunlar yaşanabilir. Örneğin karşılıklı haberleşen iki uygulamadan (bunlar A ve B olsun) A, B’ye bir veri yollayacakken B uygulaması sohbeti keserse, bu durumda A uygulamasının yolladığı veri kayıp bir veri olacaktır.**

Bu katmanda çalışan protokoller ce servisler aşağıda verilmiştir:

|Kullanılan standartlar|     |
|-----------------|----------------------|
|Standart|Açıklama|
|Netbios| Ağ'a bağlı aygıtların birbirleri ile haberleşmesi için kullanılan bir API'dir. NetBIOS, Network Basic Input/Output System 'in kısaltmasıdır. Bu, ayrı bilgisayarlarda yerel alan ağı üzerinden iletişim kurmak için OSI Modelini sağlayan uygulamaların oturum katmanı ile ilgili hizmet vermektedir.|
|NFS|Ağ Dosya Sistemi, Sun Microsystems tarafından 1984 yılında geliştirilmiş, ağdaki bilgisayarların ortak bir dosya sistemine, yerel diskleri kadar kolay ulaşmasını sağlayan, RPC temelli dağıtık dosya sistemi yapısıdır.|
|SQL| Verileri yönetmek ve tasarlamak için kullanılan bir dildir. SQL, kendisi bir programlama dili olmamasına rağmen birçok kişi tarafından programlama dili olarak bilinir. SQL herhangi bir veri tabanı ortamında kullanılan bir alt dildir.| 
|Socket|: Soket, TCP/IP'de, veri iletişimi için gereken iki bilgi olan IP adresi ve port numarasının yan yana yazılmasıyla oluşan iletişim kanalıdır.Örneğin, 192.168.1.1 makinesine 23 numaralı porttan yapılmış olan bir bağlantı 192.168.1.1:23 şeklinde yazılır.|

-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

**6.Katman: Sunum Katmanı**: Ağ ortamında PC’ler arası paylaşılan verinin anlamlı olması bu katman sayesindedir.Ağ ortamında PC’ler arası paylaşılan verinin anlamlı olması bu katman sayesindedir. Paylaşılan bilginin
PC’ler tarafından da okunabilmesi için verinin ortak bir formata dönüştürülmesi gerekmektedir. Paylaşımda bulunan bilgisayarların farklı yazılımlarla yönetildiğini düşündüğünüzde bu işlevin önemi anlaşılmaktadır.
Böylece farklı programların birbirlerinin verisini kullanabilmesi mümkün olur. Sunum katmanının en önemli görevlerinden biri, paylaşılan verinin karşı bilgisayara şifreli olarak iletebilmesidir.

**Sunum katmanı gönderilecek verinin uygun formatta hazırlanmasını gerçekleştirir. Böylece karşı taraftaki uygulama katmanı bu veriyi kullanabilir. Yani uygulama katmanı için çevirme, dönüştürme işlemi gerçekleştirir. Ayrıca sistemler arasında syntax farklılığı ya da sistemden kaynaklı bit uzunluğu farklılıkları vs. olabilir. Örneğin bir sistem bir harfi 8 bit ASCII olarak kaydederken bir diğeri 16 bit Unicode kullanabilir. İkisi de aynı harfi temsil etmesine rağmen format, uzunluk gibi farklılıkları olabilir. Bu durumda sunuş katmanı 8 ya da 16 bit ile değil direkt o harf ile ilgilenilmesini sağlar. Çünkü uygulamalar arası farklılıklarda tercüman gibi davranır.**

Kullanılan formatlar şunlardır: GIF,DIVX,DOC,ASCII,EBCDIC,TIFF,JPEG,PICT,MPEG,MIDI

------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
**7.Katman: Uygulama Katmanı**:Bu katman, kullanıcıların ve programların ağı kullanabilmesi için araçlar sunar. Uygulama katmanı son katman olduğundan diğer katmanlara herhangi bir hizmet sunmaz. 
Çalıştırılan uygulamalar için ağ hizmetlerini oluşturur. HTTP program değil, kurallar dizesi olan bir protokoldür. Bu protokole göre işlev gören bir Internet Explorer, aynı protokolü kullanan başka Web 
sunuculara bağlanır. Ayrıca bu katman iletişim kuracağı bilgisayarın iletişime hazır olup olmadığını tespit eder, iletişimi senkronize eder. 

Kullanılan uygulama ve protokollerden bazıları şunlardır;
|Kullanılan standartlar|     |
|-----------------|----------------------|
|Standart|Açıklama|
|Telnet| Telnet, Internet ağı üzerindeki çok kullanıcılı bir makineye uzaktaki başka bir makineden bağlanmak için geliştirilen bir TCP/IP protokolü ve bu işi yapan programlara verilen genel isimdir.|
|HTTP| HTTP bir kaynaktan dağıtılan ve ortak kullanıma açık olan hiperortam bilgi sistemleri için uygulama seviyesinde bir iletişim protokolüdür.|
|Web Browser|: Web tarayıcısı veya ağ tarayıcısı kullanıcıların World Wide Web üzerinde bulunan bilgi kaynaklarını edinmeye ve görüntülemeye yarayan yazılımların genel adıdır.WWW üzerindeki bilgi kaynakları web sayfası, resim, video veya başka içerik türü olabilir.|
|FTP| File Transfer Protocol olan FTP’nin Türkçe karşılığı Dosya Transfer Protokolü’dür. İsminden de anlaşılabileceği gibi internete bağlı iki bilgisayar arasında dosya transferini sağlayan bir protokol ve bu işleme hizmet eden uygulamaya verilen isimdir.Örneğin bir web sitende yer alması istenen dosyalar sunuculara FTP üzerinden aktarılabilir.|
