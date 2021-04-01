# OAuth grant types

## 1. Authorization request / Yetkilendirme İsteği

İstemci uygulaması, belirli kullanıcı verilerine erişim izni isteyen OAuth hizmetinin/ yetkilendirme uç noktasına bir istek gönderir.Bununla birlikte her zaman talepte kullanılan parametrelere göre uç noktayı tanımlayabilmelisiniz.

    GET /authorization?client_id=12345&redirect_uri=https://client-app.com/callback&response_type=code&scope=openid%20profile&state=ae13d489bd00e3c24 HTTP/1.1
    GET /authorization?client_id=12345&redirect_uri=https://client-app.com/callback&response_type=code&scope=openid%20profile&state=ae13d489bd00e3c24 HTTP/1.1
    Host: oauth-authorization-server.com Host: oauth-authorization-server.com 

Bir istek genellikle sorgu dizesinde sağlanan aşağıdaki dikkate değer parametreleri içerir.

**Client id**
İstemci uygulamasının benzersiz tanımlayıcısını içeren zorunlu parametre.Bu değer,istemciuygulaması OAuth hizmetine kayıt olduğunda oluşturulur.

**redirect_uri**
Yetkilendirme kodunu istemci uygulamasına gönderirken kullanıcının tarayıcısının yeniden yönlendirilmesi gereken URI.Aynı zamanda "geri alma URI'sı" yada "geri arama uç noktası" olarakda bilinir.Çoğu OAuth saldırısı,bu parametrenin doğrulamasındaki kusurlardan yararlanmaya dayanır.

**response_type**
İstemci uygulamasının ne tür bir yanıt beklediğini ve dolayısıyla hangi akışı başlatmak istediğini belirler.

**scope**
İstemci uygulamasının hangi kullanıcı verilerinin alt kümesine erişmek istediğini belirtmek için kullanılır.

**state**
İstemci uygulamasındaki geçerli oturuma bağlı benzersiz,tahmin edilemez bir değer depolar.OAuth hizmeti,yetkilendirme koduyla birlikte yanıtta bu tam değeri döndürmelidir.Bu parametre / geri çağrı uç noktasına yapılan isteğin OAuth akışını başlatan kişiden gelmesini sağlayarak istemci uygulaması için bir CSRF belirteci biçimi görevi görür.

## 2. User login and consent / Kullanıcı Girişi ve Onayı

Yetkilendirme sunucusu ilk isteği aldığında,kullanıcıyı bir giriş sayfasına yönlendirecek ve kendisinden OAuth sağlayıcısıyla hesaplarında oturum açma istenecektir.Örneğin,Sosyal medya hesapları.Daha sonra, istemci uygulamasının erişmek istediği verilerin bir listesi sunulur.Bu yetkilendirme talebinde tanımlanan kapsamlara dayanır.Kullanıcı bu erişime izin verip vermemeyi seçebilir.

Kullanıcı bir istemci uygulaması için belirli bir kapsamı onayladıktan sonra,kullanıcının OAuth hizmetine geçerli bir oturumu olduğu sürece bu adımın otomatik olarak tamamlanacağını unutmamak gerekir.Kısaca,kullanıcı ilk kez "Sosyal medya ile giriş yap" ı seçtiğinde,manuel olarak giriş yapmaları ve onay vermeleri gerekecektir,ancak istemci uygulamasını daha sonra tekrar ziyaret ederse bu işlem otomatik şekilde gerçekleşecektir.

## 3. Authorization code grant / Yetki kodu verilmesi

Kullanıcı istenen erişime izin verirse,tarayıcısı yetkilendirme isteğinin redirect_uri parametresinde belirtilen /callback uç noktasına yeniden yönlendirecektir.Ortaya çıkan GET isteği ,yetkilendirme kodunu bir sorgu parametresi olarak içerecektir.Konfigürasyona bağlı olarak,yetkilendirme talebindeki ile aynı değerde durum parametreside gönderebilir.
    GET /callback?code=a1b2c3d4e5f6g7h8&state=ae13d489bd00e3c24 HTTP/1.1
    Host: client-app.com 

## 4. Access token request /Erişim Belirteci İsteği

İstemci uygulaması yetkilendirme kodunu aldıktan sonra,bunu bir erişim belirteci ile değiştirmesi gerekir.Bunu yapmak için,OAuth hizmetinin/belirteç uç noktasına sunucudan sunucuya POST isteği gönderilir.Bu noktadan itibaren tüm iletişim güvenli bir arka planda gerçekleşir. ve bu nedenle genellikle bir saldırgan tarafından izlenemez veya kontrol edilemez.

    POST /token HTTP/1.1
    Host: oauth-authorization-server.com
    …
    client_id=12345&client_secret=SECRET&redirect_uri=https://client-app.com/callback&grant_type=authorization_code&code=a1b2c3d4e5f6g7h8 

Client_id ve yetkilendirme koduna ek olarak, aşağıdaki yeni parametreleri görürüz.

**client_secret**

İstemci uygulaması OAuth hizmetine kayıt olurken atandığı gizli anahtarı ekleyerek kendi kimliğini doğrulamalıdır.

**grant_type**

Yeni uç noktanın istemci uygulamasının hangi izin türünü kullanmak istediğini  bildiğinden emin olmak için kullanılır.Bu durumda bu, authorization_code olarak ayarlanmalıdır.

## 5. Access token grant / Erişim belirteç izni

OAuth hizmetierişim belirteç iznini doğrular.Her şey beklediği gibiyse,sunucu,istemci uygulamasınaistenen kapsamda bir erişim belirteci vererek yanıt verir.

    {
    "access_token": "z0y9x8w7v6u5",
    "token_type": "Bearer",
    "expires_in": 3600,
    "scope": "openid profile",
    …
    }

## 6. API call

Artık istemci uygulamasının erişim kodu vardır,sonunda kullanıcının verilerini kaynak sunucusundan alabilir.Bunu yapmak için OAuth hizmetinin / userinfo uç noktasına bir API çağrısı yapar.Erişim belirteci,istemci uygulamasının bu verilerin erişim iznine sahip olduğunu kanıtlamak için Authorization: Bearer başlığını gönderir.

    GET /userinfo HTTP/1.1
    Host: oauth-resource-server.com
    Authorization: Bearer z0y9x8w7v6u5 

# 7. Resource grant / Kaynak İzni

Kaynak sunucusu,belirtecin geçerli olduğunu ve geçerli istemci uygulamasına ait olduğunu doğrulamalıdır.

    {
     "username":"carlos",
     "email":"carlos@carlos-montoya.net",
    …
    } 

İstemci uygulaması nihayet bu verileri amaçlanan amacı için kullanabilir.OAuth kimlik doğrulaması durumunda,bu genellikle kullanıcıya kimliği doğrulanmış bir oturum vermek ve etkin bir şekilde oturum açmak için bir kimlik olarak kullanılır.

## Implicit grant type / Örtük izin türü

Örtük izin türü daha basittir.İstemci uygulaması , ilk önce bir yetkilendirme kodu elde etmek ve ardından bunu bir erişim belirteci ile değiştirmek yerine, kullanıcı onayını verdikten sonra erişim jetonunu alır.Örtük izin türünü kullanırken, tüm iletişim tarayıcı yeniden yönlendirmeleri aracılıyla gerçekleşir yetkilendirme kodu akışındaki gibi güvenli bir kanal yoktur.Buda onu daha az güvenli durumuna getirir.bu hassas erişim belirtecinin ve  kullanıcının verilerinin potansiyel saldırılara daha açık olduğu anlamına gelir.Örtük izin türü client_secret'i arka uçta kolayca depolamayan ve bu nedenle,yetkilendirme kodu verme kullanmaktan çok fazla fayda sağlamayan tek sayfalı uygulamalara ve yerel masaüstü uygulamalarına daha uygundur.

![](https://portswigger.net/web-security/images/oauth-implicit-flow.jpg)

## 1. Authorization request

Örtülü akış yetkilendirme kodu hemen hemen aynı şekilde başlar.Tek  büyük fark response_type parametresinin belirteç olarak ayarlanması gerektiğidir.

    GET /authorization?client_id=12345&redirect_uri=https://client-app.com/callback&response_type=token&scope=openid%20profile&state=ae13d489bd00e3c24 HTTP/1.1
    Host: oauth-authorization-server.com

## 2. User login and consent / Kullanıcı Girişi ve Onayı

Kullanıcı oturumu açar ve istenilen izinleri kabul edip etmeyeceğine karar verir.Bu süreç,yetkilendirme kodu akışıyla tamamen aynıdır.

## 3. Access token grant / Erişim belirteç izni

Kullanıcı istenilen erişime izin verirse,işlerin farklılaşmaya başladığı yer burasıdır.OAuth hizmeti kullanıcının tarayıcısını yetkilendirme isteğinde belirtilen redirect_uri'ye yönlendirir.ancak,bir yetkilendirme kodu içeren bir sorgu parametresi göndermek yerine,erişim jetonunu ve diğer jetone özgü verileri bir URL parçası olarak gönderir.

    GET /callback#access_token=z0y9x8w7v6u5&token_type=Bearer&expires_in=5000&scope=openid%20profile&state=ae13d489bd00e3c24 HTTP/1.1
    Host: client-app.com 

Erişim belirteci bir URL parçası olarak gönderildiği için hiçbir zaman doğrudan istemci uygulamasına doğrudan gönderilmez.Bunun yerine,istemci uygulamasının parçayı çıkartmak ve depolamak için uygun  bir komut dosyası kullanması gerekir.

# 4. API call

İstemci uygulaması,erişim jetonu URL parçasından başarıyla çıkarıldıktan sonra, OAuth hizmetinin / User info uç noktasına API çağrıları yapmak için kullanılabilir.Yetkilendirme kodu akışının aksine,bu aynı zamanda tarayıcı aracılığıyla gerçekleşir.

    GET /userinfo HTTP/1.1
    Host: oauth-resource-server.com
    Authorization: Bearer z0y9x8w7v6u5 
## 5. Resource grant

Kaynak sunucusu,belirtecin geçerli olduğunu ve geçerli istemci uygulamasına ait olduğunu doğrulamalıdır.Öyleyse,istenen kaynağı,yani kullanıcıların verilerini,erişim belirteciyle ilişkili kapsama göre göndererek yanıt verecektir.

    {
    "username":"carlos",
     "email":"carlos@carlos-montoya.net"
    } 

İstemci uygulaması bu verileri amaçlanan amacı için kullanabilir.OAuth kimlik doğrulaması durumunda,bu genellikle kullanıcıya kimliği doğrulanmış bir oturum vermek ve etkin bir şekilde oturum açmak için bir kimlik olarak kullanılır.




























