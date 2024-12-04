#Yazılım #Docker 

Docker kurulumunu yaptıktan sonra, Docker’ı doğru bir şekilde çalıştığından emin olmak için birkaç temel komutu kullanabilirsiniz. İşte Docker’ın doğru bir şekilde kurulduğunu kontrol etmek ve konteynerlerle etkileşim kurmak için kullanabileceğimiz bazı temel komutlar:

1. **Docker Versiyonunu Kontrol Etmek**
Docker’ın doğru bir şekilde kurulduğunu ve hangi sürümde olduğunu görmek için şu komutu kullanabilirsiniz:
```bash
docker --version

```

2. **Docker Daemon Durumunu Kontrol Etmek**
Docker daemon’ı, Docker’ı çalıştıran arka planda bir süreçtir. Docker daemon’ının düzgün çalışıp çalışmadığını kontrol etmek için:
```bash
sudo systemctl status docker

```
Buradaki `Active: active (running)` ifadesi, Docker’ın aktif olduğunu gösterir.

3. **Çalışan Konteynerleri Görüntülemek**
Docker ile oluşturduğunuz ve çalışan konteynerleri görmek için şu komutu kullanabilirsiniz:
```bash
docker ps // aktif konteynerları görüntülemek
docker ps -a // tüm konteynerları görüntülemek
```

4. **Bir Konteyneri Durdurmak**
Bir konteyneri durdurmak için, konteyner ID’sini veya ismini kullanabilirsiniz. Örnek:
```bash
docker stop <container_id>

```

5.  **Bir Konteyneri Silmek**
Durdurulmuş bir konteyneri silmek için:
```bash
docker rm <container_id>

```

6. **Docker İmajlarını Görüntülemek**
Docker sisteminde yüklü olan imajları listelemek için:
```bash
docker images

```

7. **Bir Docker İmajını Çekmek (Pull)**
Docker Hub’dan bir imaj çekmek için:
```bash
docker pull <image_name>

```

8. **Bir Docker İmajını Silmek**
Bir imajı silmek için:
```bash
docker rmi <image_id>

```

9. **Docker Konteyner Loglarını Görüntülemek**
Bir konteynerin loglarını görmek için:
```bash
docker logs <container_id>

```

10. **Docker Help (Yardım)**
Docker hakkında daha fazla bilgi almak ve mevcut komutları görmek için:
```bash
docker --help

```
Bu temel komutlarla Docker’ın kurulumunun düzgün yapıldığını ve temel işlevselliğini test etmiş oluruz. Docker'ı kullanarak konteyner oluşturma, çalıştırma, durdurma ve silme gibi temel işlemleri bu komutlarla gerçekleştirebiliriz.

---
***Abdullah TANRIVERDİ***





