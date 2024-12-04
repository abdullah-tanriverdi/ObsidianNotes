#Yazılım #Docker 
![[dockercompose.png|500]]

Docker Compose, birden fazla container’ı bir arada yönetmek için kullanılan bir araçtır. Özellikle, çoklu hizmetlerin (services) bir arada çalışması gerektiği durumlarda kullanılır. Docker Compose, YAML formatında yazılan bir konfigürasyon dosyasını (`docker-compose.yml`) kullanarak bu container’ları tanımlar.

==**Docker Compose Kurulumu**==

Docker Compose, Docker Desktop ile birlikte gelir, ancak manuel olarak kurulumu da yapılabilir. Ubuntu üzerinde kurulumu şu şekilde yapabilirsiniz:
```bash
sudo apt-get update
sudo apt-get install -y docker-compose

```
Kurulum sonrası Compose sürümünü kontrol etmek için:
```bash
docker-compose --version

```

==**`docker-compose.yml` Dosyası**==

Docker Compose, her bir container için yapılandırmayı tek bir dosya içinde tanımlar. Bu dosya, YAML formatında yazılır ve tüm servislerin, ağların ve volume'lerin yapılandırmasını içerir.
Örnek `docker-compose.yml` dosyası:
```bash
version: '3'
services:
  web:
    image: nginx:alpine
    ports:
      - "8080:80"
    networks:
      - front-tier
  db:
    image: postgres:alpine
    environment:
      POSTGRES_USER: user
      POSTGRES_PASSWORD: password
      POSTGRES_DB: mydb
    networks:
      - back-tier
volumes:
  postgres-data:
    driver: local
networks:
  front-tier:
  back-tier:

```

- **`version:`**: Compose dosyasının sürümünü belirtir.
- **`services:`**: Çalışacak container'ları tanımlar. Her bir container bir servis olarak tanımlanır.
    - **`web:`**: Bir web servisi, burada Nginx container’ı kullanılıyor.
    - **`db:`**: Bir veritabanı servisi, burada PostgreSQL container’ı kullanılıyor.
    - **`ports:`**: Container içindeki portu dışa aktarır.
    - **`environment:`**: Container’a çevresel değişkenler gönderir (örneğin, veritabanı kullanıcı adı ve şifresi).
    - **`networks:`**: Container'lar arasında ağ bağlantısı kurar. Bu örnekte iki ayrı ağ tanımlanmıştır: `front-tier` ve `back-tier`.
- **`volumes:`**: Veritabanı verilerini kalıcı hale getirmek için bir volume tanımlanır. Bu sayede container yeniden başlatıldığında veriler kaybolmaz.


==**Compose Dosyasının Temel Yapısı**==

- **`services:`**: Her bir container (servis) tanımlanır. Her bir servis için bir `image` (container için kullanılacak imaj) veya `build` (Dockerfile kullanarak imaj oluşturma) belirtilir.
- **`networks:`**: Container’lar arasında ağ yapılandırması.
- **`volumes:`**: Verilerin kalıcı hale getirilmesi için volume tanımlanır.
Basit bir yapı:
```yaml
version: '3'
services:
  web:
    image: nginx
    ports:
      - "8080:80"
  db:
    image: postgres
    environment:
      POSTGRES_PASSWORD: example

```

==**Docker Compose Komutları**==

| **Komut**                                 | **Açıklama**                                                                  |
| ----------------------------------------- | ----------------------------------------------------------------------------- |
| `docker-compose up`                       | Docker Compose dosyasındaki tüm container'ları başlatır.                      |
| `docker-compose up -d`                    | Container'ları arka planda başlatır (detached mode).                          |
| `docker-compose down`                     | Çalışan container'ları durdurur ve siler.                                     |
| `docker-compose ps`                       | Çalışan container'ları listeler.                                              |
| `docker-compose logs`                     | Çalışan container'ların loglarını gösterir.                                   |
| `docker-compose exec <service> <command>` | Çalışan container içinde komut çalıştırır (örneğin, terminal açar).           |
| `docker-compose build`                    | Compose dosyasındaki servisler için yeni bir imaj oluşturur.                  |
| `docker-compose stop`                     | Tüm container'ları durdurur, ancak verileri silmez.                           |
| `docker-compose start`                    | Durdurulmuş container'ları başlatır.                                          |
| `docker-compose restart`                  | Çalışan container'ları yeniden başlatır.                                      |
| `docker-compose pull`                     | Docker Compose dosyasındaki servisler için en son imajları indirir.           |
| `docker-compose push`                     | Değişiklik yapılmış bir imajı Docker Hub veya başka bir registry'ye gönderir. |

==**Sonuç**==

Docker Compose, çoklu container’ları kolayca yönetmenizi sağlar ve uygulamanızın bağımlılıklarını, ağ yapılandırmalarını, veri kalıcılığını tek bir dosyada tanımlayarak büyük kolaylık yaratır. Birden fazla servisi aynı anda başlatma, durdurma ve yapılandırma işlemlerini tek bir komutla gerçekleştirmek Docker ile uygulama geliştirmeyi çok daha verimli hale getirir.


---
***Abdullah TANRIVERDİ***
