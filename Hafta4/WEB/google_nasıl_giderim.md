# _GOOGLE'A ERİŞİM ADIMLARI?_

![](https://www.sonsuzteknoloji.com/wp-content/uploads/2018/03/google-tenor.gif)



Bilgisayarımız açıldığında işletim sistemi bulunduğu yerel ağda bir adet duyuru(çıkış) mesajı yayınlar.Yayınlanan bu mesaj modem ve istemci tarafından konuşabilmeleri  için iki tarafda kendi bilgilerini **ARP (Address Resolution Protocol) Tablosuna ekler.** ARP protokolü ilk olarak **MAC (Media Access Control)** bilgilerini öğrenir.Öğrenilen MAC adresi ARP tablosuna yazılır.Bu işlemler tamamlandıktan sonra **DHCP(Dynamic Host Configuration Protocol)  üzerinden Gateway ve Subnet Mask** değerleri alınır.
![](https://www.internetsociety.org/wp-content/uploads/2019/02/dnsprivacy1-450x339.gif)
Bu işlemler yerel ağda tamamlandıktan sonra **Browser açarız**.**google.com yazdığımızda** ilk olarak işletim sistemimiz içerisindeki **hosts** dosyasını bakar.İşletim sistemi **DNS(Domain Name System)** yönledirmesi yapmadan hosts dosyasındaki DNS çözümlemesinin bilgilerini söyleme imkanı vardır.Kısaca kullandığımız işletim sistemi  hosts dosyası browser'a google yazdığımız an DNS yönlendirmesi yapmadan google adresini hosts dosyasından çözümleme yapıp devam edebilir.Eğer hosts dosyası çözümleme yapmazsa DNS sunucusuna yönlendirme yaparak domain adresini orada çözümleme yapmaya çalışır.**Bu sorgulamayı UDP 53 portu üzerinden gerçekleştirir.**
İlk başvurulan DNS sunucusu **Resolver** (Özyinelemeli) DNS ad sunucuları (DRR), DNS isteğinde bulunan ana bilgisayara istenen etki alanı adının doğru IP adresini sağlamak için diğer sorumlu DNS istekleriyle iletişim kurar. DNS istemcisiyle DNS isim sunucusu arasında aracı (middle-man) görevi görür.Tarayıcınızdan bir web sitesine istekte bulunurken, bilgisayar web sitesiyle ilişkili IP adresini bulmak için DRR’a istekte bulunur; bu isteğin yanıtının işletim sisteminde ve web tarayıcısınında olmadığı varsayılmaktadır. DRR kendi önbelleğinde isteğin yanıtını bulamazsa diğer DNS sunucularına özyinelemeli(recursive) isteklerde bulunur.

Eğer DNS çözümlesi yapılamamış ve ip adresi hala bulunamamıssa Resolver istemciyi **Root DNS Server**'a  yönlendirir.Root DNS Server da bu çözümlemeyi yapamıyorsa Resolver DNS için bir cevap döner.Dönen cevapta **TLD(Top Level Domain)** yönlendirme bilgilerini içerir.Top level domain içerisinde yine çözümleme yapılmazsa son olarak TLD resolver DNS'i **Authorititive DNS server'a** bakması için bir yönlendirme mesajı gönderir.Buradan kesin olarak google.com'un DNS bilgilerini alırız.Alınan bilgiler istemciye bildirilir.IP adresini öğrendiğimiz google.com'a tarayıcımızdan istek yaptıktan sonra adrese ilerlemek için gateway üzerinden çıkış yaparız.Ancak çıkış yapmadan önce **TCP paketinde bazı değişiklikler yapması gerekir.**

TCP paketi **4 kısımdan** oluşur.**Source IP,Destination IP,Source Port,Destination Port**
**Source bizim içerideki IP adresimizdir.10.0.0.65 gibi.**


**Destination IP, bizim gitmek istediğimiz hedeftir. Google sunucularının IP adreside 172.217.169.174 dür.Yani Destination IP miz172.217.169.174 tür.**


**Source Port Random bir değer alır.Bu değer işletim sistemi tarafından rasgele atanır.**

**Destination Port hedefe çıkış portumuzdur google web hizmeti olduğu için çıkış portu 80 dir.**

![](https://www.grc.com/image/tcpconnect.gif)




TCP paketi geteway kısmından çıkmadan önce **NAT(Network Address Translation)** tarafından işleme tabi tutulur.**Burada NAT TCP Source IP kısmını silerek yerine yeni bir IP adres(DIŞ IP)ataması yapar.Paket dışarı çıktıktan sonra hedefe SYN paketi gönderir.Hedef geri dönüş olarak SYN+ ACK yollar.Sürecin tamamlanması için  istemci ACK paketini yollar.Bu sürece three way handshake (üçlü el sıkışma)adı verilir.**

El sıkışma sağlandıktan sonra konuşma işlemi başlamış olur.Bu işlemden sonra HTTP adımına geçmiş oluruz.İlk olarak **Firewall** üzerinden geçen paket kontrolü yapılarak paket firewall dan geçer ve Web sunucusuna erişir.
