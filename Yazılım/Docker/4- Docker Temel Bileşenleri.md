#Yazılım  #Docker 

![[dockerdeamon.jpg]]

**Docker’ın Temel Bileşenleri**

Docker, bir konteynerizasyon platformudur ve temel olarak 3 ana bileşenden oluşur: **Docker Engine**, **Docker Daemon** ve **Docker CLI (Command Line Interface)**. Bu bileşenler, Docker’ın temel işleyişini sağlar ve konteyner tabanlı uygulamaların yönetimini kolaylaştırır.

 1. ==**Docker Engine**==

Docker Engine, Docker’ın çalışma sistemini sağlayan yazılımın tamamıdır. Bu, konteynerlerin oluşturulmasını, çalıştırılmasını ve yönetilmesini sağlayan tüm bileşenleri içerir. Docker Engine, genellikle iki ana bileşenden oluşur:

- **Docker Daemon** (docker daemon)
- **Docker CLI** (Command Line Interface)

Docker Engine, sistemde çalışan ve konteynerler üzerinde işlemler gerçekleştiren ana yazılım bileşenidir. Docker Engine sayesinde, kullanıcılar uygulama ve hizmetlerini hızlı bir şekilde konteynerlerde çalıştırabilir.

 **Docker Engine’ın Temel İşlevleri:**

- Konteynerleri başlatmak, durdurmak ve yönetmek.
- Docker images (görüntüleri) oluşturmak, saklamak ve paylaşmak.
- Docker Compose ile çoklu konteyner uygulamalarını yönetmek.
- Container ağı, veri paylaşımı (volumes) gibi temel özellikleri sağlamak.

 2. ==**Docker Daemon**==

Docker Daemon, Docker Engine’ın arka planda çalışan ve tüm işlemleri yöneten ana bileşenidir. Genellikle `dockerd` olarak adlandırılır. Daemon, konteynerlerin oluşturulması, çalıştırılması, durdurulması ve silinmesi gibi işlemleri kontrol eder. Daemon ayrıca Docker API’sine istekler alır ve bu istekleri işler.

**Docker Daemon’ın Temel Görevleri:**

- Konteynerlerin oluşturulması ve yönetilmesi.
- Docker image’larının (görüntülerinin) oluşturulması ve saklanması.
- Konteynerler arasında ağ yapılandırması yapmak.
- Daemon, genellikle her zaman arka planda çalışır ve sürekli olarak Docker işlemlerini izler.

Docker Daemon, Docker CLI ve Docker REST API aracılığıyla Docker ile iletişim kurar. Docker CLI komutları, genellikle Docker Daemon’a istek gönderir ve daemon bu istekleri yerine getirir.

3. ==**Docker CLI (Command Line Interface)**==

Docker CLI, kullanıcıların Docker ile etkileşime girdiği bir komut satırı aracıdır. CLI, Docker Daemon’a komutlar gönderir ve bunun sonucunda Docker konteynerlerini yönetmeye imkan tanır. CLI aracılığıyla, konteyner başlatabilir, durdurabilir, güncelleyebilir, yapılandırabilir ve yönetebilirsiniz.

 **Docker CLI Kullanım Örnekleri:**

- `docker run`: Yeni bir konteyner çalıştırır.
- `docker build`: Bir Dockerfile kullanarak yeni bir image (görüntü) oluşturur.
- `docker ps`: Çalışan konteynerleri listeler.
- `docker stop`: Çalışan bir konteyneri durdurur.
- `docker exec`: Çalışan bir konteynerda komut çalıştırmanızı sağlar.

Docker CLI, Docker Daemon’a bağlanarak işlemleri başlatır ve komutları çalıştırır. CLI, kullanıcıların Docker ile etkileşime girmesi için en yaygın kullanılan araçtır.


 ==**Docker Bileşenlerinin Etkileşimi**==

- **Docker CLI**, kullanıcıdan aldığı komutları Docker Daemon'a gönderir.
- **Docker Daemon** bu komutları işler, konteynerleri yönetir, Docker image’larını oluşturur ve ağ yapılandırmasını yapar.
- **Docker Engine** ise tüm bu işlemleri koordine eder ve kullanıcıya Docker'ın konteynerizasyon özelliklerini sunar.

Bu üç bileşen bir arada çalışarak, Docker'ın tüm işlevselliğini sağlar ve konteyner tabanlı uygulama yönetimini çok daha kolay hale getirir.

---

***Abdullah TANRIVERDİ***
