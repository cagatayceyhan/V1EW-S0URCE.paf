# OAuth 2.0 authentication vulnerabilities
# OAuth 2.0 kimlik doğrulama güvenlik açıkları

<h3>İnternette gezinirken genellikle sosyal medya hesabımızı kullanarak giriş yapmamıza izin veren sitelere rastlarız.Bu özellik  popüler OAuth 2.0 çerçevesi kullanılarak oluşturulmuştur.OAuth 2.0 saldırganlar için oldukça ilgi çekicidir çünkü hem son derece yaygındır hem de doğası gereği uygulama hatalarına eğilimlidir. Bu saldırganların hasas kullanıcı verilerini elde etmesine ve potansiyel olarak kimlik doğrulamasını tamamen atlamasına olanak tanıyan bir dizi güvenlik açığına neden olabilir.

![](https://portswigger.net/web-security/oauth/images/oauth.jpg)

# What is OAuth?

# OAuth Nedir?

<h3>OAuth, web sitesinin ve web uygulamalarının başka bir uygulamadaki bir kullanıcının hesabına sınırlı erişim istemesine olanak tanıyan yaygın olarak kullanılan bir yetkilendirme çerçevesidir.

En önemlisi OAuth kullanıcısının giriş kimlik bilgilerini talep eden uygulamaya göstermeden bu erişimi vermesine izin verir.Bu hesapların tam kontrolü üçüncü tarafa vermek  zorunda kalmadan  paylaşmak istedikleri verileri paylaşabiliyor olmalarıdır.

Temel OAuth işlemi bir kullanıcının hesabından  belirli verilere erişim gerektiren üçüncü taraf işlevselliğini entegre etmek için yaygın olarak kullanılır.Örneğin,bir uygulama,kişilerin bağlantı kurmasını önerebilmek için e-posta kişi listenize erişim istemek için OAuth kullanabilir.Bununla birlikte,aynı mekanizma,üçüncü taraf kimlik doğrulama hizmetleri sağlamak de kullanılır ve kullanıcıların farklı bir web sitesinde sahip oldukları bir hesapla oturum açmalarına izin verilir.

<h4>NOT

OAuth 2.0 mevcut standart olmasına rağmen,bazı web siteleri hala eski sürüm 1a'yı kullanmaktadır.OAuth 2.0 doğrudan OAuth 1.0'dan geliştirmek yerine yerine sıfırdan yazılmıştır.Sonuç olarak ikisi çok farklı.Lütfen bu materyallerde "OAuth" teriminin yalnızca OAuth 2.0'ı İfade Ettiğini unutmayın.</h4>

# How does OAuth 2.0 work?

# OAuth 2.0 Nasıl çalışır?

 <h3>OAuth 2.0 başlangıçta uygulamalar arasında belirli verilere erişimi paylaşmanın bir yolu olarak geliştirilmiştir.Üç farklı taraf ,yani istemci uygulaması,bir kaynak sahibi, ve OAuth hizmet sağlayıcısı arasındaki bir dizi etkileşimi tanımlayarak çalışır.</h3>

 **Client Application / İstemci Uygulaması = Kullanıcının verilerine erişmek isteyen  web sitesi veya web uygulaması**
 **Resource Owner / Kaynak Sahibi = İstemci uygulamasının verilerine erişmek istediği kullanıcı**
 **OAuth service provider /OAuth Servis Sağlayıcısı = kullanıcının verilerini ve bunlara erişimini kontrol eden web sitesi veya uygulama.Hem bir yetkilendirme sunucusu hem de bir kaynak sunucusuyla etkileşim için bir API sağlayarak OAuth'u destekler.**

 <h3>Gerçek OAuth sürecinin uygulamasının bir çok farklı yolu vardır.Bunlar OAuth "akışları" veya "izin türleri" olarak bilinir.Bu konuda en yaygın olan "yetkilendirme kodu" ve "örtük/implicit" türlerine odaklaacağız genel olarak, bu  türlerin her ikisi de aşağıdaki aşamaları içerir:</h3>

<h3> 1. İstemci Uygulaması, hangi türü kullanmak istediğini ve ne tür erişim istediklerini belirterek kullanıcı verilerinin bir alt kümesine erişim izni ister.</h3>

 <h3>2. Kullanıcının OAuth hizmetine giriş yapması ve istenilen erişim için açıkça izin vermesi istenir.

 <h3>3. İstemci uygulaması, kullanıcıdan istenen verilere erişim iznine sahip olduğunu kanıtlayan benzersiz bir erişim belirteci alır.Bunun tam olarak nasıl gerçekleştiği türüne bağlı olarak önemli ölçüde  değişir.
 <h3>4. İstemci uygulaması, ilgili verileri kaynak sunucusundan getiren API çağrıları yapmak için bu erişim token ını kullanır.

# OAuth grant types

# OAuth İzin Türleri

<h3> Bu bölümde en yaygın iki OAuth Türünün temellerine bakacağız.<h3>

# What is an OAuth grant type?

# OAuth izin türü nedir?

<h3>OAuth izin türü OAuth sürecine dahil olan adımların tam sırasını belirler.izin türü,erişim jetonunu kendisine nasıl gönderileceeği dahil olmak üzere istemci uygulamasının her aşamada  OAuth hizmetiyle nasıl iletişim kuracağıda etkiler.Bu nedenle , izin türleri genellikle OAuth akışları olarak adlandırılır.

Bir AOuth hizmetinini bir istemci uygulamasının karşılık gelen akışı başlatabilmesi için belirli bir izin türünü destekleyecek şekilde  yapılandırılması gerekir.İstemi uygulaması ,OAuth hizmetine gönderdiği ilk yetkilendirme isteğinde hangi izin türünü kullanmak istediğini belirtir.

Her biri farklı düzeylerde karmaşıklık  ve güvenlik hususlarına sahip bir kaç farklı izin türü vardır.Açık ara en yaygın olanları olan "yetkilendirme kodu" ve örtük" izin türlerine odaklanacağız.</h3>

# OAuth Scopes

# OAuth Kapsamları

<h3>Herhangi bir OAuth erişim türü için, istemci uygulamasının hangi verilere erişmek istediğini ve ne tür işlemler gerçekleştirmek istediğini belirtmesi gerekir. Bunu, OAuth hizmetine gönderdiği yetkilendirme isteğinin kapsam parametresini kullanarak yapar.Temel OAuth için, bir istemci uygulamasının  erişim isteyebileceği kapsamlar her OAuth hizmeti için benzersizdir.
Kapsamın adı yalnızca rastgele bir metin dizisi olduğundan,format sağlayıcılar arasında önemli ölçüde değişiklik gösterebilir.Hatta bazıları,bir REST APIuç noktasına benzer şekilde kapsam adı olarak tam bir URI kullanır. Örneğin, bir kullanıcının  kişi listesini okuma erişimi istendiğinde ,kapsam adı,kullanılan OAuth hizmetine bağlı olarak aşağıdaki formlardan herhangi birini alabilir:</h3>
        
    scope=contacts
    scope=contacts.read
    scope=contact-list-r
    scope=https://oauth-authorization-server.com/auth/scopes/user/contacts.readonly 

<h3>Ancak OAuthi kimlik doğrulama için kullanıldığında, bunun yerine genellikle standartlaştırılmış OpenID Connect kapsamı kullanılır.</h3>

# Authorization code grant type

# Yetki kodu verme türü

<h4>Yetkilendirme kodu verme türü başlangıçta oldukça karmaşık görünüyor, ancak birkaç temel bilgiye aşina olduğunuzda aslında düşündüğünüzden daha basit.

Kısacası, istemci uygulaması ve OAuth hizmeti, akışı başlatan bir dizi tarayıcı tabanlı HTTP isteğini değiştirmek için ilk olarak yönlendirmeleri kullanır.Kullanıcıya istenen erişime izin verip vermediği sorulur. Kabul ederlerse, istemci uygulamasına bir "yetki kodu" verilir.İstemci uygulaması daha sonra bu kodu OAuth hizmetiyle değiştirerek ilgili kullanıcı verilerini almak için API çağrıları yapmak için kullanabilecekleri bir "erişim belirteci" alır.

Kod / belirteç değişiminden ileriye doğru gerçekleşen tüm iletişim, güvenli, önceden yapılandırılmış bir arka kanal üzerinden sunucudan sunucuya gönderilir ve bu nedenle son kullanıcı tarafından görünmezdir. Bu güvenli kanal, istemci uygulaması OAuth hizmetine ilk kaydolduğunda oluşturulur.

En hassas veriler (erişim belirteci ve kullanıcı verileri) tarayıcı aracılığıyla gönderilmediğinden, bu hibe türü muhtemelen en güvenli olanıdır. Sunucu tarafındaki uygulamalar ideal olarak her zaman mümkünse bu hibe türünü kullanmalıdır.

![](https://portswigger.net/web-security/oauth/images/oauth-authorization-code-flow.jpg)