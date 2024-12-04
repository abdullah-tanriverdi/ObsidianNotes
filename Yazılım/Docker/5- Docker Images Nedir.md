#Yazılım  #Docker 

**Docker Image Nedir?**
- Bir container'ın oluşturulabilmesi için gerekli bir şablondur.
- Dosya sistemi katmanlarından oluşur (katmanlı yapı).
- Değişmez (immutable) bir yapıya sahiptir.

==**Docker Image ile Çalışma**==
- Docker Hub'dan Image Çekmek
```bash
docker pull [image_name]:[tag]

```
- Yerel Image''leri Listeleme
```bash
docker images

```
- Image Silme
```bash
docker rmi [image_id]

```

==**Docker Image Oluşturma**==
<br>

**Dockerfile Nedir**
- Docker image oluşturmak için kullanılan bir dosyadır.
- Talimatları içerir (`FROM`, `RUN`, `CMD` gibi).

```dockerfile
# Base image
FROM ubuntu:latest  

# Yazar bilgisi
LABEL maintainer="your_email@example.com"  

# Paket güncelleme ve uygulama kurulumu
RUN apt-get update && apt-get install -y python3  

# Çalışma dizini
WORKDIR /app  

# Çalıştırılacak komut
CMD ["python3"]

```

**Docker Image Oluşturma**
```bash
docker build -t [image_name]:[tag] [dockerfile_path]
docker build -t my-python-app:v1 . //örnek


```


==**Docker Image’lerin Katmanlı Yapısı**==

- Her komut (`RUN`, `COPY` vb.) bir katman oluşturur.
- Daha az değişiklik, daha küçük ve hızlı image'ler oluşturur.
- Katmanlar **cache** olarak saklanır.

 **Katmanlı Yapının Avantajları**
- Aynı katman birden fazla image'de kullanılabilir.
- Daha hızlı image oluşturma ve çekme.


==**Sık Kullanılan Komutlar**==

|Komut|Açıklama|
|---|---|
|`docker pull [image_name]`|Image’i çekmek|
|`docker images`|Yerel image’leri listelemek|
|`docker build -t [name] .`|Yeni bir image oluşturmak|
|`docker rmi [image_id]`|Image silmek|
|`docker tag [src] [dst]`|Image etiketlemek|
|`docker push [repo]:[tag]`|Docker Hub’a image yüklemek|


---

***Abdullah TANRIVERDİ***

