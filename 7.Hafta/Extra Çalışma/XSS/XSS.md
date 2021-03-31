# XSS Nedir? 

Genellikle web uygulamalarında bulunan bir güvenlik açık türüdür. Web sayfalarına dışarıdan müdahale ile HTML ve JavaScript kodları çalıştırılabilir.Saldırgan kişiler yazdıkları zararlı Javascript kodlarıyla kurban kişilerin cookie,tarayıcı ip bilgileri gibi ve daha fazlasını bu güvenlik açığını kullanarak çalabilirler.

## XSS nerelerde kullanılabilir:

Kullanıcıların veri girişi yapabileceği arama, yorum vb text bölümlerinde bulunur.

# XSS Türleri:

## REFLECTED XSS:

Bu saldırı türü güvenlik açığı bulunan sitelerde uygun alanlara yazılan JavaScript kodlarının çalıştırılması ile olur. ilgili javascript kodu o an çalıştırılabilir. veritabanına kaydedilmez.Kurban Kişiye e-mail yada benzeri iletişim araçları kullanılıp doğrudan gönderilerek istismar gerçekleştirilir.

## STORED XSS:

Bu saldırı türü REFLECTED XSS'e göre daha tehlikelidir.Saldırgan kişinin yazmış olduğu kodlar veri tabanına kayıtedilir ve sayfayı ziyaret eden herkes bu zararlı javascript kodlarının istismarına uğrar.

## DOM XSS: 

Bu saldırı türü en tehlikeli olandır.Virus trojen zararlı kodlar sayfaya entegre edilebilir.Sitede gezerken başka sayfalara yönlendirebilir.DOM XSS sayfa bazlı değil tüm sitede etkin zaralı yerleştirmeye olanak sağlar.Ancak Stored de sadece a sayfasında bulunduysa zararlının etki alanı sadece a sayfası kadar ve sadece o bölgeyi etkiliyor.


