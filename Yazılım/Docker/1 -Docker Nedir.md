#Yazılım #Docker

![[docker.png|500]]

Docker, uygulamaları **konteyner** adı verilen hafif ve taşınabilir bir ortamda çalıştırmaya yarayan bir platformdur. Konteynerler, uygulamanın ihtiyaç duyduğu her şeyi (kütüphaneler, bağımlılıklar, konfigürasyonlar vb.) içinde barındırır ve bu sayede uygulama herhangi bir işletim sistemine bağımlı olmadan çalışabilir.

Eskiden bir uygulama geliştirmek ve çalıştırmak için farklı işletim sistemlerinde uyumluluk sorunları yaşanıyordu. Docker bu sorunu ortadan kaldırıyor ve **"Bir yerde çalışıyorsa, her yerde çalışır"** mottosuyla hareket ediyor.

==**Docker Neden Önemlidir?**== 
- **Platform Bağımsızlık**: Uygulamalar bir yerde çalışıyorsa, başka bir yerde de sorunsuz çalışır.
- **Kaynak Verimliliği**: Sanal makinelerden farklı olarak, işletim sistemini yeniden yüklemek yerine ana işletim sistemi çekirdeğini kullanır. Böylece daha az kaynak tüketir.
- **Hızlı Başlangıç**: Konteynerler, sanal makinelerden çok daha hızlı başlar.
- **Taşınabilirlik**: Bir konteyneri alıp farklı bir makinede, bulutta veya sunucuda çalıştırabilirsiniz.
- **Kolay Yedekleme ve Yönetim**: Konteynerler, hızlıca durdurulup başlatılabilir ve kolayca yedeklenebilir.
==**Docker'ın Temel Kavramları**==

- **Image (İmaj):**  
    Docker konteynerlerinin oluşturulması için kullanılan şablondur. Bir imaj, uygulama kodunu, gerekli kütüphaneleri ve çalıştırma ortamını içerir. İmajlar **Docker Hub** gibi depolardan indirilebilir veya `Dockerfile` ile özel olarak oluşturulabilir.
    
- **Container (Konteyner):**  
    İmajdan türetilen çalışan bir ortamdır. Uygulamalarınızı çalıştırdığınız alan burasıdır. Bir konteyner, bir işletim sistemi gibi davranır ancak çok daha hafiftir.
    
- **Docker Engine:**  
    Docker'ın çekirdeği olarak düşünülebilir. Konteynerleri oluşturma, çalıştırma ve yönetme işlerini yapar.
    
- **Docker Hub:**  
    Hazır Docker imajlarının bulunduğu bir çevrimiçi depodur. Geliştiriciler buradan hazır imajları indirip kullanabilir veya kendi imajlarını paylaşabilirler.
    
==**Docker Ve VM Fark**==

Docker, sanal makinelerden farklı bir yaklaşıma sahiptir. Sanal makineler, her biri kendi işletim sistemine ihtiyaç duyarken, Docker konteynerleri **ana işletim sistemi çekirdeğini** paylaşır. Bu fark sayesinde:

- Docker daha az bellek kullanır.
- Konteynerler çok daha hızlı başlatılır.
- Aynı sunucu üzerinde daha fazla uygulama çalıştırılabilir.

|Özellik|Sanal Makine (VM)|Docker|
|---|---|---|
|**İşletim Sistemi**|Her VM kendi OS'ine sahip|Ana OS çekirdeğini paylaşır|
|**Başlatma Süresi**|Dakikalar|Saniyeler|
|**Kaynak Kullanımı**|Ağır|Hafif|
|**Portatiflik**|Kısıtlı|Çok yüksek|

==**Docker Nerelerde Kullanılır?**==
- **Uygulama Geliştirme ve Test**: Geliştiriciler, farklı sistemler arasında uyumluluk sorunlarını minimuma indirir.
- **Mikroservis Mimarisi**: Her mikroservis ayrı bir konteynerde çalıştırılarak bağımsız bir şekilde yönetilir.
- **DevOps Süreçleri**: CI/CD pipeline'ları için mükemmel bir araçtır.
- **Bulut ve Edge Bilişim**: Docker konteynerleri, bulut platformlarında veya IoT cihazlarında çalıştırılabilir.

==**Docker’ın Çalışma Prensibi**==
Docker, üç ana bileşen üzerinde çalışır:

1. **Docker Daemon**: Konteynerlerin ve imajların yönetiminden sorumlu bir arka plan hizmetidir.
2. **Docker CLI**: Komut satırı aracılığıyla Docker ile etkileşim kurmamızı sağlar.
3. **Docker Compose**: Çoklu konteyner içeren uygulamaları kolayca yönetmeye yarar.
****

***Abdullah TANRIVERDİ*** 