#Yazılım #Docker 

![[dockerhub.png|500]]

==**Docker Hub Nedir?**==
- Docker Hub, Docker imajlarının (images) depolandığı ve paylaşıldığı bir çevrimiçi platformdur.
- Resmi Docker imajlarının yanı sıra topluluk tarafından oluşturulan imajları da barındırır.
- **Kullanım Alanları:**
    - Uygulama imajlarını paylaşmak.
    - Var olan imajları indirip özelleştirmek.
    - CI/CD süreçlerinde imajları merkezi bir konumda saklamak.

==**Docker Hub’a Erişim**==
- Web arayüzü: Docker Hub
- Komut satırı aracı: Docker CLI ile `docker pull`, `docker push` komutları.

==**Temel Kavramlar**==
- **Repository (Depo):**
    
    - İmajların saklandığı yer.
    - Örneğin: `library/nginx` bir resmi depodur.
- **Image (İmaj):**
    
    - Konteyner oluşturmak için kullanılan şablon.
    - Örneğin: `ubuntu`, `python`.
- **Tag (Etiket):**
    
    - İmajların farklı sürümlerini ayırmak için kullanılır.
    - Örneğin: `python:3.9` (3.9 sürümü).
- **Resmi İmaj (Official Image):**
    
    - Docker tarafından doğrulanan, güvenilir imajlardır.
- **Kullanıcı İmajları:**
    
    - Topluluk veya bireysel kullanıcılar tarafından oluşturulan imajlar.


==**Docker Hub Komutları Tablosu**==

|**Komut**|**Açıklama**|**Örnek Kullanım**|
|---|---|---|
|`docker search <image_name>`|Docker Hub üzerinde belirli bir imajı arar.|`docker search nginx`|
|`docker pull <image_name>:<tag>`|Docker Hub’dan bir imajı indirir.|`docker pull ubuntu:latest`|
|`docker images`|Yerel makinedeki tüm Docker imajlarını listeler.|`docker images`|
|`docker login`|Docker Hub’a giriş yapar. Kullanıcı adı ve şifre ister.|`docker login`|
|`docker tag <image_id> <repo:tag>`|Yerel bir imajı, bir Docker Hub deposuna göndermek için etiketler.|`docker tag myapp:latest myuser/myapp:v1`|
|`docker push <repo:tag>`|Etiketlenmiş bir imajı Docker Hub’a yükler.|`docker push myuser/myapp:v1`|
|`docker rmi <image_id>`|Yerel bir Docker imajını siler.|`docker rmi 12345abcde`|
|`docker inspect <image_name>`|Bir imajın detaylı bilgilerini gösterir (metadata).|`docker inspect ubuntu`|
|`docker logout`|Docker Hub’dan çıkış yapar.|`docker logout`|
|`docker build -t <repo:tag> .`|Dockerfile kullanarak bir imaj oluşturur ve bir Docker Hub deposu için etiketler.|`docker build -t myuser/myapp:v1 .`|

---

***Abdullah TANRIVERDİ***
