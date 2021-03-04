# Genel Kavramlar

## Kernel(Çekirdek)

Bilgisayar sistemlerinde yazılım ve donanım arasındaki iletişimi sağlayan arabirimdir.

## Komut Satırı

Kullanıcıdan gelen komutları algılayarak kernel'e iletir.Kernelde bu komutları donanımlara ulaştırarak istenilen sürecin tamamlanmasını sağlar.
Komut satırı bir programdır ve alternatifleri vardır.Bu alternatiflerde kendi içerisinde çeşitli özellikleri barındırır.Komut Satırının alternatiflerini **cat /etc/shells** komutu ile öğreniriz.

![shells](https://raw.githubusercontent.com/cagatayceyhan/terminal_Img/main/shells.PNG)

Komut satırı altında kullandığımız kabuğu öğrenmek istersek **echo $SHELL** komutunu kullanırız.

![echo](https://raw.githubusercontent.com/cagatayceyhan/terminal_Img/main/echoshells.PNG)

## Ortam değişkenleri

Programların çalıştırılabilir dosyalarının kaydedildiği dizinlerdir.O dizinlere koyulan programlar sadece ismi kullanılarak çalıştırılabilir.Ortam değişkenleri kullanıldığı zaman yol belirtmemize gerek yoktur.**/bin/sh** yazdığımızda yol belirtip  sh kabuğunu çalıştırırız.Ancak Ortam değişkenleri sayesinde  **sh** komutunu yazarakta sh kabuğuna erişim sağlayabiliriz.
Bu özelliği bize sağlayan Ortam Değişkenleridir.

Ortam Değişkenlerini görmek istersek komut satırına **echo $PATH**  komutunu çalıştırırız.

![path](https://raw.githubusercontent.com/cagatayceyhan/terminal_Img/main/path.PNG)

*/Her iki nokta sonrası bir dizini temsil eder./*
/usr/local/sbin:
                  /usr/local/bin: 
                                  /usr/sbin:
                                            /usr/bin:
                                                      /sbin:/bin:
                                                                  /bin:/usr/local/games:
                                                                                        /usr/    games

İstersek her dizinin içeriğini ls komutu ile kontrol edebiliriz.


ls komutundan sonra karşımıza dizinler veya programlar çıkabilir.Çıkan bu sonuçlar renklerine göre kategorize edilir.
![ls](https://raw.githubusercontent.com/cagatayceyhan/terminal_Img/main/lsusr.PNG)

**Yeşiller = Çalıştırılabilir.**
**Maviler  = Dizinleri temsil eder.**