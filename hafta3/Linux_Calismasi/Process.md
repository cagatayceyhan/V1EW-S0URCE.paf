# Process

Süreç(process),çalışır dosyaların çalışır hallerine verilen isimdir.Yani bir program çalıştırıldığında,belleğe yüklenen o programa süreç adı verilir.Sistemde bizim başlattığımız süreçler haricinde daha bir çok servise ait süreçler çalışmaktadır.Aynı zamanda çalışan bir program birden fazla süreçten oluşabilir.Sistemde ki süreçlerle ilgili bilgi almak,işlem yapmak vs. ile ilgili kullanabileceğimiz çeşitli komutlar bulunmaktadır.

## ps komutu

Herhangi bir anda çalışan süreçleri görmek için ps komutunu kullanırız.Bu komutun kullanım parametrelerini öğrenmek için ***ps --help** komutunu kullanabiliriz.

![ps-all](https://raw.githubusercontent.com/cagatayceyhan/terminal_Img/main/ps%20-all.PNG)

ps: Aktif kullanıcıyla ilgili olan süreçler.

ps -e yada ps -f: Sistemde çalışansüreçlerin ayrıntılıayrıntılı listesi için kullanılabilirler.

ps -u:sistemdeki bir kullanıcıyla ilgili süreçler.

## pstree komutu

Sistemdeki süreçleri hiyararşik bir liste halinde görüntülemek için **pstree** ya da **ps -el --forest** komutları kullanılabilir.

![ps-all](https://raw.githubusercontent.com/cagatayceyhan/terminal_Img/main/pstree.PNG)

Eğer Süreçleri PID numaralarıyla beraber görmek istiyorsak **pstree -p** komutunu kullanırız.

![ps-all](https://raw.githubusercontent.com/cagatayceyhan/terminal_Img/main/pstree-p.PNG)

##(process id), süreçlerin numarasıdır ve sistemde süreçlerin bir nevi haberleşmesini sağlar.

bir kullanıcıyla ilgili süreçleri görmek için  **pstree user** komutunu kullanılır.Bir süreci alt süreçleriyle(child processes) birlikte görmek için de ""pstree pid** komutu kullanılır.

![ps-all](https://raw.githubusercontent.com/cagatayceyhan/terminal_Img/main/pstreepid.PNG)

## top komutu

süreçler hakkında bilgi almak için kullanabileceğimiz bir başka komutda **top** komutudur.Bu araç ps aracının aksine süreçleri anlık değişimlerine de içerecek şekilde izler.Sistemde çalışan uygulamalar,iş yüklerine göre sürekli kaynak talep ederler ve bu yüzden anlık değişimlerolabilir.Bu komutun en temel kullanımı **top** şeklindedir.Eğer komutu **top-d 10** formatında kullanırsak,sonuçları 10 sabniyede bir günceller.(var sayılan değer 3 saniyedir.)çıkmak için q tuşuna basılmalıdır

![top](https://raw.githubusercontent.com/cagatayceyhan/terminal_Img/main/top.PNG)

## pgrep

Hafızada çalışan süreçlerin belirli kriterlere göre listelenmesi için **pgrep** komutu kullanılır.Çalışan süreçler üzerinde değişiklik yapabilmek için önce o süreci bulmamız gerekir.Örneğin ls komutu ile ilgili süreçleri bulmak için **pgrep ls** komutunu kullanabiliriz.

![top](https://raw.githubusercontent.com/cagatayceyhan/terminal_Img/main/pgrep.PNG)

Bu komutta ls  komutuna ait pid numarasını görmüş olduk Eğer süreç numarasıyla beraber süreç isimlerini de döndürmek istiyorsak -l parametresini kullanmalıyız.Yani komut **pgrep -l ls** şeklinde olmalı.

![top](https://raw.githubusercontent.com/cagatayceyhan/terminal_Img/main/pgrep-l.PNG)


Herhangi bir kullanıcıya ait olan süreçleri bulmak için de **pgrep -lu user** komutu kullanılabilir.


![top](https://raw.githubusercontent.com/cagatayceyhan/terminal_Img/main/-lu.PNG)


## kill-killall komutu

Süreçleri sonlandırmak için kullanıcağımız komutlar **kill** ve **killall** komutlarıdır.Bu komutların genel kullanımı şu şekildedir.

**kill pid : süreci pid numarasıyla sonlandırmak için**

**kill -9 pid : Sonlandıramadığımız sürece öldürücü darbe vurmak için**

**killall sürec_ismi: Programla/servisle ilgili tüm süreçleri sonlandırmak için**

**killall -9 surec_ismi: Ölmekte direnen servisin süreçlerini öldürmek için**

**killall -i sürec_ismi: Süreçleri interaktif olarak sonlandırmak için**

## xkill Komutu

Bir X oturumunda cevap vermeyen bir uygulamayı öldürmek için terminalden **xkill** komutunu kullanırız.Böylece fare işaretcisi X şeklini alır ve öldürmek istediğiniz uygulama penceresine tıklayarak o uygulamayı sonlandırabiliriz.
