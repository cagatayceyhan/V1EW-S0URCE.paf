# Linux Challenges

**What is flag 1?**

flag1'i bulmak için bulunduğumuz dizinde ls komutu ile listeleme yapıyoruz daha sonra çıkan sonuçta cat flag1.txt dosyasını açıp flag'i alıyoruz.

![]()

**What is flag 2?**
flag2'yi bulmak için dizinler arası dolaşıyoruz.bob dizini içerisine girdiğimizde ls ile listeleme yapıyoruz.Listeleme sonucu flag2 ye ulaşıyoruz cat flag2.txt açıp içerisinden flag 2 yi alıyoruz.

![]()

Flag 3 is located where bob's bash history gets stored.


**Flag 3 is located where bob's bash history gets stored.**

bob dizini altında ls-lah komutunu kullanarak detaylı şekilde listeleme yapıyoruz çıkan sonuçta cat .bash_history komutunu çalıştırıp flag3ê ulaşıyoruz.

![]()

**Flag 4 is located where cron jobs are created.**

Crontab'a ulaşmak için bob kullanıcısına su komutu ile geçiyoruz.Geçtikten sonra locate komutu ile crontabs konumunu arıyoruz.çıkan sonuçtaki yola cd komutu ile gidiyoruz akabinde crontab -l komutu ile içeriden flagi alıyoruz.

![]()

**Find and retrieve flag 5.**

İlk olarak locate flag5.txt dosyasının konumunu öğrenmek için locate komutunu kullanıyoruz akabinde locake komutunun çıkardığı sonuçtaki yola gidiyoruz.cat komutu ile flag5.txt komutunun içindeki flag değerini alıyoruz.

![]()



**"Grep" through flag 6 and find the flag. The first 2 characters of the flag is c9.**

home dizini gidiyoruz ls komutu ile listeleme yapıyoruz.listeleme sonucu flag6.txt bu dizinde olduğunu görüyoruz.soruda belirtilmesi üzerine flag içerisinde c9 ifadesi geçtiğini biliyoruz bu yüzden grep ile c9 ifadesi geçen değeri arıyoruz ve flagi buluyoruz.

![]()

**Look at the systems processes. What is flag 7.**

7 numaralı flagin  süreçlerde olduğunu biliyoruz bu yüzden ps aux komutu ile flage ulaşıyoruz.