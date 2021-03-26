# Command Line Scripting

BASH SHELL

Linux sistemlerde işletim sistemiyle etkileşim kurmanın ana grafiksel olmayan araç Shell dir. bir konsol terminal veya bash olarak adlandırıldığını görmüssünüzdür.
    
Free BSD gibi kali linux gibi herhangi bir grafik arayüzüne sahip olmayan eski bir unix sisteme kuracak olsaydınız underlying işletim sistemiyle  etkileşime girmenin tek yolu kabuktan geçer.

Free BSD kabuğu aşağıdakine benzer.Görüldüğü gübü hiç GUI / Arayüz yok.

![](https://raw.githubusercontent.com/cagatayceyhan/terminal_Img/main/sc1.PNG)

Linux Shell bir komut yorumlayıcısıdır. Çeşitli Shell türleri vardır ve bunlardan en popüler olanı Bash dir.

Her Shell davranışı farklı olsada temel amacı aynıdır. İşletim sistemiyle etkileşim kurmak için bir komut satırıyla etkileşim kurmamız gerekir.

Diğer önemli Sheller:

- ksh    
  
- zsh
  
- dash

BASH Environment /BASH Ortamı

Kali linux makinemizde Terminali başlattığımızda yeni bir BASH kabuğu başlatılır.

Biz onu kullanmadan önce işletim sistemi bash ortamını başlatır.

Kabuk başlatıldığında İşletim sistemi ~/.bashrc, ~/bash_login veya ~/.bash_profile gibi birkaç dosyanın varlığını  kontrol eder.Bu dosyalar, ortamın doğru şekilde kurulmasına yardımcı olacak bazı talimatlar içerir ~/.bash_logout dosyasındada aynı şey olur.

Ortamın önemli bir kısmı ortam değişkenleridir.

Bunları program yorumlayıcısı başlatıldığında önceden tanımlamış normal programlama değişkeni olarak düşünebilirsiniz.

Ortam değişkenleri sistem işlevlerini doğru şekilde kullanmak için gerekli olan işletim sisteminden gelen bilgileri içerir.

Terminale env komutunu girerek ortam değişkenlerini görüntüleyebiliriz.

![](https://raw.githubusercontent.com/cagatayceyhan/terminal_Img/main/sc2.PNG)


en önemli ortam değişkenlerinden birisi PATH dir. echo komutu kullanılarak içeriğini görüntüleyebiliriz.

Bash de bir değişkene başvurmak istiyorsanız  önüne dolar işareti koymalısınız. Örneğin PATH değişkeninin içeriğini görmek için şunu yazmanız gerekir.

    echo  $PATH

![](https://raw.githubusercontent.com/cagatayceyhan/terminal_Img/main/sc3.PNG)

PATH in formatı vardır 

[location]:[location]:[location]:...:[location]

ve bash penceresinde bir komut girdiğinizde bash in çalıştırılabilir dosyaları nerede arayacağı hakkında bilgi içerir.

terminale merhaba yazdığımızdaki çıktı.

![](https://raw.githubusercontent.com/cagatayceyhan/terminal_Img/main/sc4.PNG)

Bu bash içerisinde "merhaba" yürütülebilir dosyasının varlığı PATH değişkeninde bulunan tüm konumları kontrol ettiği anlamına gelir.Orada merhaba adında bir yapı olmadığı için komut bulunamadı hatası verdi.

PATH değişkeni yürütme yardımcılarından biridir. Özellikle PATH içinde tutulan konumlara bir program eklersek çağrıldığında çalışacaktır.

Bash Commands and Programs

Bash in kendisi temel işlevlerini sağlayan bazı yerleşik komutlara sahiptir.

Ancak varsayılan olarak /bin veya /usr/bin gibi PATH konumlarında tutulan uzantı programlarına büyük ölçüde güvenir.

Bash yerleşik komutlarına örnek olarak fg,echo,set,while verilebilir.

Günlük görevlerde tutulan komutların çoğu / bin gibi PATH knumlarında tutulan harici mini programlardır.Örnekler ls,ping,passwd,chmod, ve daha fazlası

komutun gerçek konumunu bilmek istiyorsak which komutunu kullanırız.

![](https://raw.githubusercontent.com/cagatayceyhan/terminal_Img/main/sc5.PNG)

Linux işletim sisteminde çok fazla komut vardır.Çoğu zaman bir komutun ne iş yaptığını hatırlamak isteriz.Bu gibi durumlarda manuel lin kısaltması olan man komutunu kullanırız.

PATH olmayan bir programı çalıştırmak istersek mutlaka yolunu belirtmemiz gerekir. 

Bir programı göreceli bir yol kullanarakda çalıştırmak isteyebilirsiniz.Göreceli yol mevcut dizinden konumun ne oldu anlamına gelir. 


![](https://raw.githubusercontent.com/cagatayceyhan/terminal_Img/main/sc6.PNG)

veya istenen yürütülebilir dosyayı bulmak için  sistemin birden çok dizini geçmesini sağlayabilirsiniz.


![](https://raw.githubusercontent.com/cagatayceyhan/terminal_Img/main/sc7.PNG)


# Bash Output Redirection and Special Characters


Bash kabuğuna yazarken özel anlamı olan karakterlere dikkat etmelisiniz.


    ~  mevcut kullanıcının ana dizini
    * yalnızca belirli dosya türlerini seçmek için kullanılabilen bir joker karakterdir.


Bir bash kabuğunda bir komut çalıştırıldığında sonucuna çıktı adı verilir.Her komutun varsayılan davranışı  çıktıyı bash kabuguna yazdırmaktır.Ancak kullanıcı bu davranışı değiştirebilir ve çıktıyı başka bir yere yönlendirebilir.

Temel çıktıyı yönlendirmenin iki yöntemi vardır: bir dosyaya veya bir komuta

Bir dosyaya yönlendirmek için 

komutun çıkışını içeren bir dosya oluşturmak için  komut > dosyaadı.txt komutu kullanılır.veya bir mevcut dosyanın  üzerine komutun çıkışıyla yazın.

komutun çıkışını içeren bir dosya oluşturmak için veya komutun çıktısını mevcut bir dosyaya eklemek için >> file.txt komutunu kullanabiliriz.

Başka bir komutun çıktısına eklenti yapmak için pipe "|" komutunu kullanırız.

Zincirleme komutları oldukça  güçlü BASH özelliğidir.Daha önceden bahsedilen özel karakterleri kullanarak  bir çok sıkıcı görevi  otomatikleştiren tek satırlık  bir komut dosyası oluşturarak birden çok komut zincirlemek mümkündür.Bu tür komut dosyalarına genellikle onelines denir.

Örneğin 

![](https://raw.githubusercontent.com/cagatayceyhan/terminal_Img/main/sc8.PNG)

Yeniden yönledirilmiş üç bloğa ayrılan komut yapısı


![](https://raw.githubusercontent.com/cagatayceyhan/terminal_Img/main/sc9.PNG)

ilk olarak operator değerlendirelecektir. *conf ismine sahip tüm dosyaları /etc/dizininde listeleyecek ve sıralayacaktır. ancak bu kullanıcı tarafından görülmeyecektir.


listelenen her dosya için dosya komutu (dosya biligisi)yürütülecek ve bu çıktı test.txt dosyasına yeniden yönledirilecektir.

Daha sonra sıra && operatörüne gelir.Bu komut önceki komut başarılı olursa  sonraki komuta  ilerleyin anlamına gelir.


![](https://raw.githubusercontent.com/cagatayceyhan/terminal_Img/main/sc10.PNG)


Bu durumda çıktıyı başarılı bir şekilde  bir dosyaya yeniden yönlendirdiğimiz için  cat komutunu kullanarak text .txt  içeriğini görüntüleyebiliriz.

![](https://raw.githubusercontent.com/cagatayceyhan/terminal_Img/main/sc11.PNG)

# Bash Conditional Statements and Loops


Terminallere bash deyimleri yazmanın yanı sıra aynı zamanda betik dosyalarınıda kaydedebiliriz.

Linux  bash komutları içeren herhangibir dosyayı  çalıştırabilmektedir. ancak genel standartlara uygun olarak  bir bash komut dosyası  <örnek.sh> uzantısına sahip olmalıdır.

Bash komut dosyaları  en başında hangi kabuğun yorumlanmaları gerektiğini gösteren bilgileri içermektedir.

Bash kullanmak istiyoruz bu nedenle herhangibir bash komut dosyasının ilk satır şu olmalıdır.

    #!/bin/bash

Bir bash dosyasını oluşturup kaydettikten sonra aynı zamanda yürütülebilir hale geldiğinden emin olmamız gerekir.

Linux izinleri geniş ve biraz gelişmiş bir konudur.bu komut dosyası oluşturma komutunun sağlığı açısından oluşturulan komut dosyası üzerinde chmod +x  <komut adı> komutunu kullandığımızdan a emin olmalıyız.Daha sonra ./script_name komutunu vererek oluşturduğumuz komutu kullanabiliriz.


![](https://raw.githubusercontent.com/cagatayceyhan/terminal_Img/main/sc12.PNG)


Diğer komut dosyaları dili gibi BASH de koşullu ifadeler işlevselliği sunar.

Basic syntax is : 

    if <şart>; then 

    <şart> 

    fi

ek olarak else elif  if gibi yapılarda kullanılır.


    if [ x ]; then

    docommand

    elif[ y ];then

    doothercommand

    else

    dosomethingelse

    fi

bash de koşullku ifade yazmak zordur çünkü farklı  karşılaştırma türleri içi,n farklı kalıplar kullanmanızı gerektirir.

numaralar aşağıdaki operatörler kullanılarak karşılaştırılabilir.

* -eq # equal / Eşit 

* -ne # not equal /Eşit değil 

* -lt# less than / Küçüktür

* -le # less than or equal / Küçük eşittir.

* -gt# greater than /  Büyüktür

* -ge# greater than or equal  / Büyük eşittir.

# Bash Conditional Statements / Koşullu İfadeler


Örnek  (Köşeli parantez içerisindeki boşluklara dikkat edilmeli)

    x=231

    y=321

    if [ "$a" -eq "$b" ];then

    echo "They're equal";

    fi

bash içerisinde İki adet  temel döngü vardır. for ve while

Bir for döngüsü döngü koşulundaki ögeler üzerinde yineleme yapmak için uygundur.Örneğin geçerli dizedeki  her ögeyi şu şekilde yazdırırız.

    #!/bin/bash

    for i in $( ls ); do

    echo item: $i

    done

Numaralar üzerinde yenileme yapmak istiyorsak  bash "seq" komutunu kullanabiliriz.

    #!/bin/bash

    for i in `seq 1 10`;

    do

    echo $i

    done


while döngüsü bir dosyadaki ögeler üzerinde yineleme yaparken çok yararlı olabilir.Aşağıdaki temel söz dizimi nasıl göründüğünü görüyoruz.

    while [condition]; do <command1>;<command2>; done

Windows Command Line 


Windows komut satırı (cmd.exe) Linux bash kabuğunun Microsoftaki eşdeğeridir.

Konumu  C:\Windows\system32\cmd.exe

Bash in aksine windows  komut satırı  esas olarak  yerleşik işlevlere komutlara dayanır.

Bazı komutlar dir,cls,move veya del dir.

# Windows Environment



Bashler benzer şekilde windows un  da bir ortamı vardır. genellikle windows GUI tarafından yönetilir.

Windows 10 da windows ortam değişkenlerini  yönetmek için  Denetim masası > Sistem ve Güvenlik > Sistem > Gelişmiş Sistem Ayarlarına gideriz.

![](https://raw.githubusercontent.com/cagatayceyhan/terminal_Img/main/sc13.PNG)

Ortam Değişkenlerine  tıklayarak ayarları yönetebilirsiniz.Cmd.exe yi her başlattığımızda çevresel ayarları buradan çekilir.Değişkenleri global olarak (tüm kullanıcılar için sistem değişkenleri)veya mevcut bir kullanıcı için yönetebilir.

![](https://raw.githubusercontent.com/cagatayceyhan/terminal_Img/main/sc14.PNG)

En ilginç değişkenlerden birisi Windows PATH i dir. Tam olarak Linux un PATH değişkeninin yaptığı gibi çalışır. ve komut satırı  programlarının  nerede aranacağı ile ilgili konumlar sağlar.

![](https://raw.githubusercontent.com/cagatayceyhan/terminal_Img/main/sc15.PNG)

windows ta çalıştırılabilir dizinler ";" sembolüyle ayrılırlar.

Bir cmd.exe penceresinde bir şey yürütmeye çalıştığımızda windows sistemi bunun yerleşik komutlardan herhangi biriyle eşleşip eşlenmediğini kontrol eder.Yürütmeye çalıştığımız şey  yerleşik bir komut değilse windows onu bulmak için  PATH değişkeninde belirtilen tüm komutları arayacaktır.


Bashde olduğu gibi  konumunu komut satırına görece veya mutlak olarak belirterek  başka herhangiş bir programı çalıştırabilirsiniz.Sadece dizinin eğik çizgilerinin  bash kullanımından farklı bir yönü işaret ettiğini hatırlamanız gerekir.Bash de normal / bölü işareti varken windowsda ters \ kullanılır.

![](https://raw.githubusercontent.com/cagatayceyhan/terminal_Img/main/sc15.PNG)

# Windows Commandsand Programs


Daha önce belirttiğimiz gibi Windows komut satırı  Linux komut satırından  daha fazla yerleşik komutu destekler.Bununla birlikte  bazı yaygın Windows yardımcı programları  C:\Windows\system32 de (varsayılan olarak PATH de)bulunur.bulunan bağımsız yürütülebilir dosyalardır. 
Örneğin:  

ping.exe

 yardımcı programdır.


Yeni yüklenen dosyanızı cmd üzerinden çalıştırabilir hale getirmek istiyorsanız onu PATH lokasyonuna eklememiz gerekir veya konumu içerecek şekilde PATH değişkenini değiştirmelisiniz.



 Yalnızca birkaç Windows programının  bir komut satırı  arabirimini desteklediğini ve bu nedenle bunların oradan çalıştırılmasının yazılımın GUI sinin başlatılmasına  neden olabileceğini unutmayın.




# Windows Output Redirection and Special Characters


Windows un komut satırı Bash e göre daha az esnek bir komut dosyası oluşturma ortamıdır.

Windowsda gelişmiş komut dosyaları oluşturmak istiyorsanız bunun için Powershell komutunu kullanmalısınız.

Windows un ortam değişkenlerine erişmek için  %variablename%  hatırlayacağınız gibi  bu değişkenler Gelişmiş sistem ayarları - ortam değişkenleri  içinde ayarlanandır.Bunları komut satırı benceresine  yazdırmak için echo command kullanmanız gerekir.



Ayrıca kendi değişkenlerimizi oluşturabilir veya   var olanları gecici olarak değiştirebiliriz.Değişkenler kalıcı olmayacak yanlızca geçerli  cmd.exe penceresinde var olacaktır.Açık başka komut  satırı pencereniz varsa  birimdeki değişkenleri değiştirmek diğerini etkilemeyecektir.

![](https://raw.githubusercontent.com/cagatayceyhan/terminal_Img/main/sc17.PNG)

Çıktı yeniden yönlendirme, Windows'ta da çalışır. Bir komutun çıktısını bir dosyaya yeniden yönlendirmek için şunları yapabilirsiniz:

Komutun çıktısıyla bir dosya oluşturmak için echo aaa> file.txt formatını kullanın veya mevcut bir dosyaya komutun çıktısı ile yazın.

Komutun çıktısıyla bir dosya oluşturmak için echo bbb >> file.txt dosyasını kullanın veya komutun çıktısını mevcut bir dosyaya ekleyin.

Daha sonra "type" komutunu kullanarak file.txt’nin içeriğini görüntüleye biliriz.



Windows komut satırında sonraki komutları yürütmek isterseniz, bunu elde etmek için aşağıdaki sembolleri kullanabiliriz:

command1 & command2 - sonuçtan bağımsız olarak her ikisini de çalıştır

command1 && command2 –ilk komutu çalıştırın ve başarılı olursa 

ikinci komutu çalıştırın

Windows komut satırında sonraki komutları yürütmek isterseniz, bunu elde etmek için aşağıdaki sembolleri kullanabilirsiniz:

command1 | command2 - çıktıyı ilk komuttan ikinci komuta gönder

command1 || komut2 –ilk komutu çalıştırın ve başarısız olursa

 ikinci komutu çalıştırın

# Windows Conditional Statements and Loops

Daha büyük komut satırı komut dosyaları oluşturmak için, bunları satır başına bir talimatla .bat dosyaları olarak kaydedebilirsiniz.

Windows bu biçimi otomatik olarak tanır ve kullanıcıların bu tür dosyaları çalıştırmasına izin verir. Bunları, not defteri gibi basit bir metin düzenleyici kullanarak düzenleyebilirsiniz.


Bash  gibi, komut satırı da karşılaştırma operatörlerinde birden fazla  olasılığa sahiptir. Ancak, sadece basit değer  karşılaştırmalarını ele alacağız.

Değişken belirli bir kelime içeriyorsa, değerleri karşılaştırmak için aşağıdaki talimatları kullanabilirsiniz:

![](https://raw.githubusercontent.com/cagatayceyhan/terminal_Img/main/sc18.PNG)

Windows komut satırı, çeşitli işlevlere sahip temel FOR döngüsü sunar. Bu kursun bağlamında, FOR ve FOR / F kullanarak dosyalar ve dosya içerikleri bakıcağız.

Örneğin, for döngüsünü kullanarak bir dizindeki dosyaları listelemek isterseniz, aşağıdaki komutu kullanabilirsiniz:

    for %i in (*.*) do @echo FILE: %i

Komuttan önceki "@", komut istemini gizlemek (C: \ Kullanıcılar> gibi) ve yalnızca çıktıyı görüntülemek anlamına gelir.


![](https://raw.githubusercontent.com/cagatayceyhan/terminal_Img/main/sc19.PNG)















































































