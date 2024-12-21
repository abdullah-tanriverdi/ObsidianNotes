#Yazılım #Docker 

![[dockervolumes.png]]

==**Volume Nedir?**==

- Volume, Docker container'larının veri depolamak ve paylaşmak için kullandığı bir mekanizmadır.
- Host işletim sisteminde saklanır, ancak container'lar tarafından erişilebilir.
- Container silindiğinde bile veriler kalıcı olarak saklanabilir.


==**Volume Türleri**==
**a. Bind Mounts**
- Host makinesindeki belirli bir dizini container'a bağlar.
- Esnek fakat Docker tarafından tamamen yönetilmez.
- Örnek: `/home/user/data:/data`

**b. Volumes**
- Docker tarafından tamamen yönetilen bir depolama alanıdır.
- Veriler Docker'ın belirttiği bir dizinde saklanır (genelde `/var/lib/docker/volumes/`).
- Daha güvenli ve kolay yedekleme seçenekleri sunar.

 **c. tmpfs Volumes**
- Geçici bellekte saklanır ve container durduğunda kaybolur.
- Hassas ve hızlı veriler için uygundur.


==**Volume Kullanımı**==

| **İşlem**                                | **Açıklama**                                  | **Komut**                             |
| ---------------------------------------- | --------------------------------------------- | ------------------------------------- |
| **Volume Oluşturma**                     | Yeni bir volume oluşturur.                    | `docker volume create <volume_name>`  |
| **Volume Listeleme**                     | Tüm volume'ları listeler.                     | `docker volume ls`                    |
| **Volume Detayları Görüntüleme**         | Belirli bir volume'un detaylarını görüntüler. | `docker volume inspect <volume_name>` |
| **Volume Silme**                         | Belirli bir volume'u siler.                   | `docker volume rm <volume_name>`      |
| **Kullanılmayan Volumes'leri Temizleme** | Kullanılmayan tüm volumes'leri temizler.      | `docker volume prune`                 |
|                                          |                                               |                                       |

==**Volume'ların Avantajları**==
- Verilerin kalıcılığı sağlanır.
- Birden fazla container arasında veri paylaşımı kolaydır.
- Host sistemiyle bağımsız çalışır.
- Daha güvenlidir ve yedekleme/geri yükleme işlemleri daha kolaydır.

--- 
***Abdullah TANRIVERDİ***

