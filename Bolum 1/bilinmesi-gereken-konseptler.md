
  

  

#  Yazılım Geliştirme Döngüsü

  

  

Yazılım yaşam döngüsü, herhangi bir yazılımın, ihtiyaç durumundan gerçekleştirilmesi ve sonrasında bakımına kadar geçen tüm süreçtir ve 6 parçadan oluşmaktadır.

  

  

![Kaynak](https://images.mendix.com/wp-content/uploads/Artboard-1@2x-701x700.png)

  

  

  

Belirtilen 6 Parça [bu bağlantı üzerinde](http://ybsansiklopedi.com/wp-content/uploads/2015/08/Yaz%C4%B1l%C4%B1m-Geli%C5%9Ftirme-Modelleri-Yaz%C4%B1l%C4%B1m-Ya%C5%9Fam-D%C3%B6ng%C3%BCs%C3%BCSDLCYBS.pdf) eksik veya unutulan kısımları ilgili bağlantı üzerinden tekrar okuyup hatırlayabiliriz.

  

  

#  Yazılım Dağıtım Süreci (CI/CD)

  

Sürekli entegrasyon ve sürekli dağıtım, kod kalitesini iyileştirmek için tasarlanmış yazılım geliştirmeye yönelik yaklaşımdır.

  

Yazılan kodun veya geliştirilen modülün , geliştirme ortamından gelen bir parçanın projeye dahil edilmesi esnasında bir takım süreçlerden geçirilmesine verilen isimdir.

  

  

En çok kullanılan CI/CD araçları ise aşağıdaki resimdeki gibidir.

  

  

![](https://miro.medium.com/max/1305/1*y06Tg8lPcoSUNkHSMHcNFA.png)

  

  

CD Gelirsek yazılan projenin veya geliştirilen ortamın sunucu üzerinde hazırlanması ve bu konfigrasyonları sağlayıp işlemlerin hepsinin otomatize bir şekilde yapılmasıdır.

  

  

Çok basit bir örnek vermek gerekirse bir yazılım ekibisiniz tüm yazdığınız kodları jetkins birleştirdi ve bir sürüm haline getirdi daha sonra cd devreye girerek yazılımınızın çalışması gereken tüm ortamları hazırlayıp deploy edilerek yazılımınız bir web sunucu üzerinde çalışır hale getirilmesidir.

  

  

#  Devops

  

Devops Engineer nedir , yoksa bir meslek midir ?

Kesinlikle bu sorunun cevabı hayır , devops bir meslek değildir , bir kültür olduğunu anlamamız gerekir öncelikle.

  
  
  

![](https://miro.medium.com/max/605/0*TivrYUJ7f-RywS7C.png)

  

DevOps, kurumların ürünleri geleneksel yazılım geliştirme ve altyapı yönetim süreçlerini kullanan kurumlara göre daha hızlı geliştirmesini ve iyileştirmesini sağlayarak, uygulama ve hizmetleri yüksek hızda sunma becerisini artıran kültürel felsefelerin, yöntemlerin ve araçların birleşimidir. Bu hız, kurumların müşterilerine daha iyi hizmet sunmasına ve piyasada daha etkili bir şekilde rekabet etmesine imkan tanır.

  

DevOps'un Avantajları

Hız , Hızlı Teslim , Güvenilirlik Ölçek , Geliştirilmiş İş Birliği ve Güvenlik.

  

#  Micro Services

  

Bir çok alt servisin bir arada tek bir amaca hizmet eden, birbirinden bağımsız yazılım servislerdir. örnek vermek gerekirse bir eticaret sistemininin sepet kısmı ayrı bir servis , ürünler ayrı bir servis , ürün stok göstergeleri ayrı bir servis olarak yapılandırılabilir ve bu yapılandırılar servisler bir arada çalışmasına micro servisler denir.

**Avantajları**

 - Servisler farklı dillerde ve farklı framework’lerde geliştirilebilir.
 - Birbirlerinden bağımsız olarak her bir servis değişebilir, kolay test ve build yapılabilir.
 - Continuous delivery’e olanak sağlar ve hızlı deployment’lar gerçekleştirilebilinir.
 
 - Her bir servisi birbirinden bağımsız olarak scale edebilme olanağı sağlar.

**Dezavantajları**

 -  Birbirlerinden bağımsızlaşan farklı servisler aynı objeleri kullanacaklarından dolayı kaçınılmaz bir kod tekrarı meydana gelecektir.

 -   Servisler farklı platform ve ortamlarda çalışabileceklerinden dolayı yönetim ve monitoring maliyeti ortaya çıkacaktır.

 -   Birden çok database ve transaction’ların yönetimi zor olabilir.

  

#  Api

  

Bir uygulamaya ait yeteneklerin, başka bir uygulamada da kullanılabilmesi için, yeteneklerini paylaşan uygulamanın sağladığı arayüzdür.

  

Örnek vermek gerekir ise her gün belli bir saat aralığında tweet göndermek istiyorsunuz bunun için twitter giriş yapmak zorundasınız ve belirleyeceğiniz saat aralığında tweet göndermeniz gerekmektedir , tweeter'ın sağlamış olduğu api sayesinde yazılımınız üzerinden istediğiniz saat aralığında istediğiniz içeriği otomatik olarak göndermesini sağlayabilirsiniz işte bunu bize sağlatan arayüz aslında bir api yazılımı bu api sayesinde twitter giriş yapmadan bir çok işlem yapmamızı sağlamaktadır.

  

#  Container

İlk önce container neden kullanıyoruz sorsunu kendimize sormamız gerektiğini düşünmekteyim.
Bilirsiniz bir çok hypervisor mevcut ve bunların en popüler olanları vmware kvm xen gibi say say bitmez :)

Yine örnek üzerinden gidelim , bir adet sunucunuz mevcut ve bu sunucunuza sanallaştırma yazılımı yüklemeniz gerekmekte , seçim olarak vmware yapalım ve sunucumuza esxi kurduğumuzu varsayalım kurulum için bir miktar disk bir miktarda ram ile cpu kullanacağız kaynağaımızın ortalama %5 civarında bir kayıp oluşacak.

Peki sadece bununla bitiyor mu ? , tabiki hayır , sanal sunucularınızı oluşturabilmeniz için diskinize kuracağınız imajları indirmeniz gerekecek ve bir den fazla sanal sunucu kuracaksanız ve imaj olarak çeşitlilik istiyorsanız bir windows imajı 5GB civarındayken linux imajları ortalama 2GB yakın bunlarıda eklediğimizde bize kalan disk alanı iyice azalacaktır işte container tam bu noktada devreye giriyor. Makineniz ve bir linux işletim sistemi kurulduktan sonra lxc veya docker kurmanız yeterli arada bir hypervisor olmayacağı ek kaynak tüketimi gibi gereksiz giderler olmayacaktır bu da donanımızın kaynağını daha çok kullanmanızı sağlayacaktır.

Yani kısacası boş yere sistem kaynaklarını kullanmayacak bir teknolojiye ihyicamız vardı buda container olarak karşımıza çıkmış durumdadır.

![](https://miro.medium.com/max/960/1*3A6h3vLtQUPJw8jl4aVX6A.png)