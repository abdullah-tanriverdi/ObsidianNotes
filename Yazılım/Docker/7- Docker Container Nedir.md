
#Yazılım #Docker 
![[dockercontainer.jpg|500]]
**Docker Container Nedir?**

- Docker container, uygulamalar ve onların bağımlılıklarını bir araya getiren, hafif ve taşınabilir bir çalışma ortamıdır.
- Host işletim sistemi üzerinde çalışan izole edilmiş süreçlerdir.
- Konteynerler, uygulamaların her ortamda aynı şekilde çalışmasını sağlar.


 **Docker Container Özellikleri**

- **Hafiflik:** Bir işletim sistemi sanallaştırma katmanı olmadığı için çok az kaynak kullanır.
- **Taşınabilirlik:** Bir konteyner birden fazla platformda aynı şekilde çalışabilir.
- **İzole Çalışma:** Her bir konteyner kendi dosya sistemine, CPU, bellek ve ağ kaynaklarına sahiptir.
- **Hızlı Başlangıç:** VM'lere göre daha hızlı başlatılır.


**Container Nasıl Çalışır?**
- Docker, bir Image'den container oluşturur.
- Bir container, işletim sistemi çekirdeğini ana makineyle paylaşır ancak kendi dosya sistemine ve ağ ortamına sahiptir.
- **Örnek Akış**:
    1. Docker Image oluşturulur veya çekilir (örneğin, `nginx:latest`).
    2. Bu imajdan bir container başlatılır (`docker run nginx`).



**Temel Komutlar**

|Komut|Açıklama|
|---|---|
|`docker ps`|Çalışan container'ları listeler|
|`docker ps -a`|Tüm container'ları listeler|
|`docker run <image>`|Belirtilen bir image'den container oluşturur ve başlatır|
|`docker start <container>`|Var olan bir container'ı başlatır|
|`docker stop <container>`|Çalışan bir container'ı durdurur|
|`docker rm <container>`|Bir container'ı siler|
|`docker logs <container>`|Container loglarını gösterir|

**Container Oluşturma Ve Yönetimi**
Container oluştur:
```bash
docker run -it --name my_container ubuntu

```
- `-it`: İnteraktif terminal açar.
- `--name`: Container'a özel bir isim verir.
- `ubuntu`: Kullanılan Docker Image.

Container'ı Durdurma ve Başlatma:
```bash
docker stop my_container  
docker start my_container

```

Geçici Container:
`--rm`: Container kapandığında otomatik olarak silinir.
```bash
docker run --rm ubuntu echo "Geçici Container"

```

==**Bir Uygulamayı Container İçinde Çalıştırma**==
Python Flask uygulaması çalıştırma
1. `app.py` dosyasını oluştur
```python
from flask import Flask
app = Flask(__name__)

@app.route('/')
def hello_world():
    return 'Hello, Docker!'

if __name__ == '__main__':
    app.run(host='0.0.0.0', port=5000)

```
2. Dockerfile oluştur
```bash
FROM python:3.9
WORKDIR /app
COPY . /app
RUN pip install flask
CMD ["python", "app.py"]

```
3. Image oluştur ve container çalıştır:
```bash
docker build -t flask-app .
docker run -p 5000:5000 flask-app

```

---

***Abdullah TANRIVERDİ***  