
# Lab Ortamı için Sistem Domain Yönlendirme 

Web For Pentester için oluşturduğumuz adrese gitmek için IP adresimizi kullanıyoruz. Adrese her seferinde IP adresi ile  gitmek yerine  Domain adresi ile gitmek için local de tanımladığımız Domain adresi ile Web for Pentester 'a ulaşabiliriz.

Bunun için Linuxda:

leafpad yada nano gibi bir araçla etc dizini altındaki hosts dosyasını açıyoruz.Açılan düzenleme aracında sanal makinemizin IP adresini yazıyoruz.

![](https://raw.githubusercontent.com/cagatayceyhan/terminal_Img/main/domain1.PNG)

Düzenleme işlemi bittikten sonra kali linux üzerinden tarayıcımızı açıyoruz ve hosts dosyasının içine yazdığımız domain adresine gidiyoruz. 

![](https://raw.githubusercontent.com/cagatayceyhan/terminal_Img/main/domain2.PNG)

Windows için :

C:\Windows\System32\drivers\etc\hosts Dosyasına sağ tıklayıp düzenliyoruz.Burada linux da olduğu gibi bir editör tarafından düzenleme yapmamız gerekiyor.

![](https://raw.githubusercontent.com/cagatayceyhan/terminal_Img/main/domain3.PNG)

Burada Linuxda yaptığımız gibi Notepad++ aracını kullanarak hosts dosyasınının içerisine IP adresini yazıyoruz.

![](https://raw.githubusercontent.com/cagatayceyhan/terminal_Img/main/domain5.PNG)

Gerekli işlemler yapıldıktan sonra tarayıcımızdan domain adresini yazarak Web For Pentester adresine gidiyoruz.

![](https://raw.githubusercontent.com/cagatayceyhan/terminal_Img/main/domain6.PNG)