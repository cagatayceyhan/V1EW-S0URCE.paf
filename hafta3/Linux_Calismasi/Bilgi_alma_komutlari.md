# Bilgi Alma Komutları

## lsb_release komutu

Kullanmış olduğumuz Linux distrosunun dağıtım bilgilerini ve adını öğrenmek için **lsb_release -a** komutunu kullanabiliriz.

![lsb_release](https://raw.githubusercontent.com/cagatayceyhan/terminal_Img/main/lsb_release.PNG)


Eğer dağıtımla ilgili bilgileri detaylandırmak istersek cat /etc/*release komutunu kullanabiliriz.

![lsb_release](https://raw.githubusercontent.com/cagatayceyhan/terminal_Img/main/catetcrelease.PNG)

## etc/issue komutu

Kullandığımız dağıtımın tam adını öğrenmek için **cat /etc/issue** komutunu kullanabiliriz.

![issue](https://raw.githubusercontent.com/cagatayceyhan/terminal_Img/main/etcissue.PNG)


## uname komutu

uname komutu ile tek başına sorgulama yapıldığında çekirdeğin ismini verecektir ancak **uname -a** komutu çalıştırıldığında çekirdeğin ismi,hostname, çekirdek mimarisi gibi bir çok bilgiyi birden öğrenebiliriz.

![uname](https://raw.githubusercontent.com/cagatayceyhan/terminal_Img/main/uname-a.PNG)



Yukarıda birçok bilgiyi tek bir komutla öğrenebildiğimizi gördük eğer istersek bu bilgileri teker teker ayrı komutlarlada öğrenebiliriz.

![uname](https://raw.githubusercontent.com/cagatayceyhan/terminal_Img/main/unamenmr.PNG)


## cal komutu

cal komutu ile bulunduğumuz ayı bir aylık takvim olarak konsolda görüntülemesini sağlayabiliriz.

![cal1](https://raw.githubusercontent.com/cagatayceyhan/terminal_Img/main/cal.PNG)


cal komutu ile bulunduğumuz ayı bir aylık takvim olarak konsolda görüntülemesini sağlayabiliriz.

![cal2](https://raw.githubusercontent.com/cagatayceyhan/terminal_Img/main/cal4.PNG)


Son olarak belirli bir senenin aylarını takvimde tam olarak görüntülemek için **cal yıl (cal 2021)** komutunu kullanabiliriz.

![cal3](https://raw.githubusercontent.com/cagatayceyhan/terminal_Img/main/cal2021.PNG)

## date komutu 

Kullandığımız sistemin o anki tarih ve saat bilgilerini öğrenmek için date komutu kullanılır.

![date](https://raw.githubusercontent.com/cagatayceyhan/terminal_Img/main/date.PNG)


## hostname komutu

Sistemimizde bilgisayarımıza verdiğimiz adı yani host adımızı öğrenmek için hostname komutunu kullanırız.


![hostname](https://raw.githubusercontent.com/cagatayceyhan/terminal_Img/main/hostname.PNG)


## uptime komutu

Sistemimizin ne kadar zamandır açık olduğunu öğrenmek için uptime komutunu kullanırız.

![uptime](https://raw.githubusercontent.com/cagatayceyhan/terminal_Img/main/uptime.PNG)


## w-who-whoami komutu

Kullandığımız sistemde kim login olmuş, o an hangi id ile çalışıyoruz gibi bilgileri öğrenmek için w-who-whoami gibi komutları kullanabiliriz.

w: Sistemde o anda hangi kullanıcının hangi komut veya uygulamaları çalıştırdığını gösterir.

![w](https://raw.githubusercontent.com/cagatayceyhan/terminal_Img/main/w.PNG)


who: Sistemde hangi kimlikle çalışıldığı bilgisine ulaşmamızı sağlar.

![who](https://raw.githubusercontent.com/cagatayceyhan/terminal_Img/main/who.PNG)


who-b: Kullandığımız sistemin en son ne zaman açıldığı bilgisini verir.

![who-b](https://raw.githubusercontent.com/cagatayceyhan/terminal_Img/main/who-b.PNG)


who -r: Sistemin hangi açılış seviyesinde(runlevel) başlatıldığını gösterir.

![who-r](https://raw.githubusercontent.com/cagatayceyhan/terminal_Img/main/who-r.PNG)


whoami: Kullanıcının hangi kimlikle çalıştığını gösterir.

![whoami](https://raw.githubusercontent.com/cagatayceyhan/terminal_Img/main/whoami.PNG)


## whereis komutu

Bir dosyayla ilgili kaynak ve yardım dosyalarının konumunu öğrenmek için whereis komutu kullanılır.

whereis komutunu -b parametresiyle kullanırsak çalıştırılabilir dosyanın konumunu verir.Eğer -m parametresi ile çalıştırırsak man sayfasının yerini, -s parametresi ile çalıştırırsak varsa kaynak kodunun yerini verir.

![where](https://raw.githubusercontent.com/cagatayceyhan/terminal_Img/main/whereis7.PNG)


## which komutu

Parametre olarak verilen bir komutun tam yol bilgisine erişmek için which kullanılır.

![which](https://raw.githubusercontent.com/cagatayceyhan/terminal_Img/main/which.PNG)


## locate komutu

locate komutu ile bir dosyanın hangi dizin ya da dizinler altında olduğunu öğrenmemize yardımcı olur.conf dosyalarını bulalım ve etc dizini altında olanlara bakalım.(çoğunlukla yapılandırma dosyaları etc nin altındadır ve grep burada tanımladığımız kalıbı arar)

![locate](https://raw.githubusercontent.com/cagatayceyhan/terminal_Img/main/locate.PNG)


## proc Sanal Dosya Sistemi ile Bilgi Almak

İşlemci ve ram hakkında detaylı bilgi almak için sanal dosya sistemi proc kullanılır.

İşlemci bilgisi için cat /proc/cpuinfo

![cpu](https://raw.githubusercontent.com/cagatayceyhan/terminal_Img/main/catproccpuinfo.PNG)


Ram bilgisi için cat /proc/meminfo komutları kullanılır.

![mem](https://raw.githubusercontent.com/cagatayceyhan/terminal_Img/main/meminfo.PNG)

## fdisk komutu

fdisk komutu genellikle diskleri bölümlemek için kullanılır ancak -l parametresiyle kullandığımızda (fdisk -l) sistemimizdeki disk bölümlemelerini görüntüleriz.

![fdisk](https://raw.githubusercontent.com/cagatayceyhan/terminal_Img/main/fdisk%20-l.PNG)


## df komutu

Disk kullanımı ile ilgili detaylı bilgileri df komutu ile öğrenebiliriz.

![df](https://raw.githubusercontent.com/cagatayceyhan/terminal_Img/main/df.PNG)


## du komutu

du komutu ile bir dizinin altında bulunan alt dizinleri,dosya ya da klasörlerin diskte kapladıkları alanın boyutunu görmek için kullanılır.

![du](https://raw.githubusercontent.com/cagatayceyhan/terminal_Img/main/du-h.PNG)


## free komutu

free komutu ile bellek üzerinde kullanım detaylarını görüntüleyebiliriz daha düzenli şekilde sonuç almak istiyorsak -m parametresiyle mb cinsinden sonuçta alabiliriz.

![free](https://raw.githubusercontent.com/cagatayceyhan/terminal_Img/main/free.PNG)


## hdparm komutu

Harddisk’le ilgili detaylı bilgi almak için kullanılan komuttur.kullanım şekli hdparm disk( hdparm /dev/sda1) şeklindedir.Kullandığımız diskin performansını öğrenmek için hdparm -Tt /dev/sda1 komutunuda kullanabilirsiniz.Burada küçük bir uyarı yapmam gerek hdparm bize istediğimiz donanımsal bilgileri ve performans sonuçlarını verecektir ancak hdparm başka parametrelerle kullanıldığında tehlikeli sonuçlar doğurabilir kullanırken girdiğimiz parametrelere dikkat etmeniz faydanıza olacaktır.

![hdparm](https://raw.githubusercontent.com/cagatayceyhan/terminal_Img/main/hdparm.PNG)


## modinfo komutu

Linux çekirdek modülleriyle ilgili bilgilere erişmek için modinfo komutu kullanabiliriz.Herhangi bir donanımın modülünü öğrenmek için modinfo d.ismi (modinfo cdrom) komutunu kullanabiliriz.Eğer modül listesini görmek istersek lsmod komutunu kullanabilirsiniz.

![modinfo](https://raw.githubusercontent.com/cagatayceyhan/terminal_Img/main/modinfo.PNG)
 

## stat komutu 

stat komutu dosya ya da dizin hakkında bilgi almamızı sağlar parametresiz kullanılabildiği gibi -f parametresiylede kullanılabilir.

![stat](https://raw.githubusercontent.com/cagatayceyhan/terminal_Img/main/stat.PNG)

## vmstat komutu

Kullanılan sistemin genel durumunu öğrenmek için vmstat komutu kullanılır.

![vmstat](https://raw.githubusercontent.com/cagatayceyhan/terminal_Img/main/vmstat.PNG)


Eğer sistem hakkında bilgilerin yenilenerek listelenmesini istersek gecikme parametresi ile kaç saniyede bir bilgilerin yenileneceğini vmstat komutuyla belirleyebiliriz.Bunun için vmstat X Y(vmstat 5 15) komutunu kullanabiliriz.X burada kaç saniyede yenileneceğini Y ise kaç defa yenilenme işleminin yapılacağını ifade eder.

![vms](https://raw.githubusercontent.com/cagatayceyhan/terminal_Img/main/vmstat515.PNG)


## history komutu 

history komutu GNU/linux sistemlerde , kullanılan komutları hafızasında tutarak(bu iş için ayrılan bir dosyaya belli bir sayıda yazılarak)geriye dönük olarak kullanılan komutların incelenmesini sağlayan ve istenildiğinde komutların tekrar kullanılmasını sağlayan komuttur.

![history](https://raw.githubusercontent.com/cagatayceyhan/terminal_Img/main/history.PNG)


Terminalde girilen komut çok fazla ve girdiğimiz komutu history ile listeleyip komut numarasını belirlersek numaranın önüne ! işareti ile numarayı girdiğimizde komut yeniden kendini tekrar edecektir. Örnek komut burada !63

Eğer son kullanılan komutu tekrardan çalıştırmak isterseniniz !! komutunu verirseniz son komut tekrarlanacaktır.

Daha önce kullanılan bir komutu tekrar aynı şekilde kullanmak için başına ! konulmalıdır.


Önceden kullanılmış bir komutun kullanılış biçimini öğrenmek istiyorsanız !komut:p komutuyla sorgulayabilirsiniz.

![unlem](https://raw.githubusercontent.com/cagatayceyhan/terminal_Img/main/!komutp.PNG)


Kullanılan komutların hepsini değil sadece belirli bir sayı aralığında görmek istiyorsak history sayı (history 7) şeklinde komutu kullanabilirsiniz.

![seven](https://raw.githubusercontent.com/cagatayceyhan/terminal_Img/main/history7.PNG)


Kullandığımız Komutların kaç tanesinin saklandığı ile ilgili bilgiyi HISTSIZE ortam değişkenin değerine bakmamız gerekir. Bunun için kullanmamız gereken komut echo $HISTSIZE dır.Default değer genellikle bindir.

![hist](https://raw.githubusercontent.com/cagatayceyhan/terminal_Img/main/echo4h%C4%B1ts%C4%B1ze.PNG)

Son olarak daha önce kullandığımız komutları görme ve yeniden kullanma amacıyla reverse search denilen yöntemide kullanabiliriz. Terminal açıkken ctrl+r kombinasyonunu kullanarak aktif edebiliriz burada istediğiniz komutun son kullanılma şekli burada çıkar ve isterseniz kullanabilirsiniz.

![research](https://raw.githubusercontent.com/cagatayceyhan/terminal_Img/main/ls.PNG)