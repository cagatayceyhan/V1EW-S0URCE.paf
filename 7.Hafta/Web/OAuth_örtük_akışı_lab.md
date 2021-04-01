# OAuth_örtük_akışı_lab 

Bu laboratuvar, kullanıcıların sosyal medya hesaplarıyla oturum açmalarına izin vermek için bir OAuth hizmeti kullanır.İstemci uygulamasının hatalı doğrulaması, bir saldırganın diğer kullanıcıların hesaplarına parolalarını bilmeden oturum açmasını mümkün kılar.
Laboratuvarı çözmek için Carlos'un hesabına giriş yapın. E-posta adresi **carlos@carlos-montoya.net.**
Aşağıdaki kimlik bilgilerini kullanarak kendi sosyal medya hesabınızla giriş yapabilirsiniz: **wiener: peter.**

Gerekli işlemleri yapmak için ilk olarak Burp Suite açıyoruz.

![](https://raw.githubusercontent.com/cagatayceyhan/terminal_Img/main/bur1.PNG)

Daha sonra Proxy sekmesi altındaki Intercept sekmesi altındaki Open Browser butonuna tıklayarak Tarayıcımızı açıyoruz.

![](https://raw.githubusercontent.com/cagatayceyhan/terminal_Img/main/bur2.PNG)

Tarayıcımızı açtıktan sonra lab ortamına erişiyoruz.

![](https://raw.githubusercontent.com/cagatayceyhan/terminal_Img/main/bur3.PNG)

Daha sonra My account linkine tıklıyoruz ve log in sayfasına erişiyoruz.

![](https://raw.githubusercontent.com/cagatayceyhan/terminal_Img/main/bur4.PNG)

Bağlanma sırasında HTTP history sekmesi altında HTTP isteklerini kontrol ediyoruz.Log in sırasında POST isteği ile gitmiş authenticate isteğini yakalıyoruz

![](https://raw.githubusercontent.com/cagatayceyhan/terminal_Img/main/bur5.PNG)

Yakaladığımız isteğin request kısmına gelerek sağ tıklayıp "Send to repeater" butonuna basıp isteği repeter a yolluyoruz.

![](https://raw.githubusercontent.com/cagatayceyhan/terminal_Img/main/bur6.PNG)

Repeater sekmesi altına geliyoruz burada e-mail,username,token gibi bilgilere ulaşıyoruz.Bize lab başlamadan önce verilen **carlos@carlos-montoya.net.** adresini şu an ki mail adresi ile değiştiriyoruz ve "Send" butonuna basıyoruz.

![](https://raw.githubusercontent.com/cagatayceyhan/terminal_Img/main/bur7.PNG)

İstekde bir hata ile karşılaşıyoruz.Bu yüzden Request kısmına gelip sağ tıklayarak Request in browser butonunun altında "In original sessions" butonuna tıklıyoruz.


![](https://raw.githubusercontent.com/cagatayceyhan/terminal_Img/main/bur8.1.PNG)

Daha sonra karşımıza çıkan linki "copy" diyoruz ve yeni sekmeye linki kopyalıyoruz.

![](https://raw.githubusercontent.com/cagatayceyhan/terminal_Img/main/bur8.PNG)

My account kısmını kontrol ettiğimizde bilgilerin değiştiğini işlemin başarılı olduğunu görüyoruz.


![](https://raw.githubusercontent.com/cagatayceyhan/terminal_Img/main/bur9.PNG)