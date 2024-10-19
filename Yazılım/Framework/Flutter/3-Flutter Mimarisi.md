#Yazılım #Framework #Flutter 

Flutter, yüksek performanslı ve güzel uygulamalar oluşturmak için güçlü bir mimariye sahiptir.

1. ==**Temel Bileşenler**==
Flutter mimarisi, dört ana bileşenden oluşur:

**Flutter Engine**:
- C++ dilinde yazılmıştır ve Flutter’ın temel yapı taşını oluşturur.
- Grafik render işlemlerini yapar ve Dart kodunun çalıştırılmasını sağlar.
- Skia adlı 2D grafik motorunu kullanarak, yüksek performanslı grafikler sunar.
- Platforma özgü hizmetlerle (örneğin, dosya sistemine erişim, ağ iletişimi) etkileşim kurmak için bir köprü görevi görür.


**Foundation Library**:
- Dart dilinde yazılmış olan temel kütüphanedir. UI bileşenleri, animasyonlar, dokunmatik olayları ve diğer temel fonksiyonlar burada bulunur.
- Geliştiricilerin daha yüksek seviyede bileşenler oluşturmalarını sağlayan temel sınıfları içerir.


> [!tip] İPUCU
> Foundation Library hakkında bilgi almak için tıkla [[-Foundation Library Nedir]]




**Widgets**:
Flutter’daki tüm şeyler widget’tır. Stateless ve Stateful olmak üzere iki ana türü vardır:
- **Stateless Widget**: Durumu olmayan, yalnızca oluşturulduklarında aldıkları verilere dayanarak görüntülenen widget’lar.
- **Stateful Widget**: Durumu olan, kullanıcı etkileşimlerine veya diğer olaylara göre değişiklik gösterebilen widget’lar.

**Framework**:
- Geliştiricilere kolay bir kullanıcı arayüzü oluşturma imkanı sunan üst düzey kütüphanedir.
- Material Design ve Cupertino tasarım ilkeleri ile uyumlu, platforma özgü görünüm ve hissiyat sunan widget’lar içerir.



2. ==**Mimari Katmanları**==

**UI Katmanı**:
- Kullanıcı arayüzünün oluşturulduğu katmandır. Geliştiriciler, bu katmanda widget’ları bir araya getirerek uygulama arayüzünü tasarlar.
- Flutter, çok katmanlı bir mimari sunarak, her bir widget’ın nasıl görüneceğini ve davranacağını belirler.

**Dart Platformu**:
- Flutter, Dart programlama dilini kullanarak uygulamaları geliştirir. Dart, hem istemci hem de sunucu tarafında kullanılabilen bir dildir.
- Dart, hızlı geliştirme süreci ve yüksek performans sunmak için tasarlanmıştır.

**Flutter Engine**:
- Önceden bahsedildiği gibi, Flutter Engine, C++ ile yazılmıştır ve grafik işleme, ağ, dosya yönetimi gibi görevleri üstlenir.
- Dart kodunun çalıştırılmasını sağlar ve platforma özgü özelliklerle etkileşimde bulunur.


3. ==**Event Loop ve Yapılandırma**==
- Flutter, bir **event loop** mekanizması kullanır. Kullanıcı etkileşimleri (dokunma, kaydırma vb.) ve zamanlayıcı olayları, bu mekanizma aracılığıyla yönetilir.
- Flutter, bir widget değiştiğinde veya yeni bir widget oluşturulduğunda, bu değişiklikleri bir yapılandırma süreci ile işleme alır. Böylece UI, hızlı ve etkili bir şekilde güncellenir.


> [!tip] İPUCU
> Event Loop mekanizması hakkında daha fazla bilgi almak için bağlantıya tıkla [[-Event Loop Mekanizması Nedir]]




4. ==**State Management (Durum Yönetimi)**==
Flutter’da durum yönetimi, uygulamanın veri durumunu kontrol etmenin önemli bir parçasıdır.

- **Provider**: Basit ve etkili bir durum yönetimi çözümü.
- **Riverpod**: Provider’ın evrim geçirmiş hali; daha güçlü ve esnek bir yapı sunar.
- **Bloc (Business Logic Component)**: Reactive programlama mantığını kullanarak durum yönetimini sağlar.
- **GetX, MobX, Redux** gibi diğer popüler kütüphaneler de mevcuttur.


> [!tip] İPUCU
> State Management hakkında detaylı bilgi için bağlantıya tıkla [[-Flutter State Management]]
> 


5. ==**Platform Kanalı**==
Flutter, platforma özgü özelliklere erişmek için **Platform Channels** kullanır. Bu, Flutter uygulamasının, Android veya iOS gibi yerel platformlarla etkileşimde bulunmasına olanak tanır.Örneğin, bir Android uygulaması için Java veya Kotlin, iOS uygulaması için ise Swift veya Objective-C kullanılarak yazılmış kodlarla iletişim kurar.


> [!tip] İPUCU
> Platform Kanalı hakkında bilgi için bağlantıya tıkla [[-Flutter Platform Channels]]





> [!note] ÖZETLE
> Flutter mimarisi, kullanıcı arayüzü bileşenleri, grafik işleme ve durum yönetimi gibi birçok önemli bileşeni bir araya getirerek etkili ve yüksek performanslı uygulamalar geliştirmeye olanak tanır. Dart dilinin ve Flutter Engine’in sunduğu olanaklarla, geliştiriciler, çeşitli platformlarda tutarlı ve çekici uygulamalar oluşturabilir. Flutter, kullanıcı dostu bir geliştirme deneyimi sunarken, modern uygulama geliştirme ihtiyaçlarını karşılamak için sürekli olarak gelişmektedir.

***
***Abdullah TANRIVERDİ***









