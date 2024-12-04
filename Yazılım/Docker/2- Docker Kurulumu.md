#Yazılım #Docker 
![[dockerdesktopwslubuntu.png|400]]



==**Docker Kurulumu ve Docker Desktop ile Bağlantı Ayarları (WSL Üzerinde)**==


 ==**1. Docker Desktop'ı Yükleme**==
1. **Docker Desktop**'ı indirmek için Docker’ın resmi sitesine gidin ve Windows için indirilen dosyayı çalıştırarak kurulum işlemini tamamlayın.
2. Kurulum tamamlandıktan sonra **Docker Desktop** uygulamasını başlatın.

==**2. WSL 2'yi Aktif Etme**==
Docker Desktop, **WSL 2**'yi kullanarak konteynerleri çalıştırır. Bu nedenle WSL 2'nin aktif olduğundan emin olmanız gerekmektedir.

- PowerShell (Admin) açın.
- WSL 2'yi aktif hale getirmek için şu komutu çalıştırın:
```powershell
wsl --set-default-version 2

```
- Ubuntu'nuzun WSL 2 üzerinde çalıştığından emin olmak için:
```powershell
wsl --list --verbose
```
- Eğer Ubuntu'nuz WSL 1 üzerinde çalışıyorsa, şu komutla WSL 2'ye geçirebilirsiniz:
```powershell
wsl --set-version Ubuntu-20.04 2
```

==**WSL Üzerinde Ubuntu'ya Docker Kurulumu**==


Ubuntu terminalini açın ve paket listenizi güncelleyin:
```bash
sudo apt update

```

Gerekli paketleri yükleyin:
```bash
sudo apt install apt-transport-https ca-certificates curl software-properties-common

```

Docker'ın GPG Anahtarını ekleyin:
```bash
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /usr/share/keyrings/docker-archive-keyring.gpg

```


Docker deposunu ekleyin:
```bash
echo "deb [arch=amd64 signed-by=/usr/share/keyrings/docker-archive-keyring.gpg] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null

```

Docker servisini kontrol edin:
```bash
sudo systemctl status docker

```


==**Docker Desktop ile Bağlantı Kurulumu**==

Docker Desktop, WSL 2 ile Docker'ı entegre eder ve WSL üzerinde çalışan Docker daemon ile bağlantı kurar.

 **Docker Desktop Ayarlarını Yapılandırma:**
1. **Docker Desktop**'ı açın.
2. **Settings (Ayarlar)** sekmesine gidin.
3. **General** sekmesinde **"Use the WSL 2 based engine"** seçeneğinin işaretli olduğundan emin olun.
4. **Resources** sekmesinde **WSL Integration** kısmında, Ubuntu dağıtımınızın (örneğin **Ubuntu-20.04**) seçili olduğundan emin olun.
5. Ayarları kaydedin ve Docker Desktop'ı yeniden başlatın.

==**Docker'ı WSL Üzerinde Test Etme**==
Docker’ın doğru şekilde çalıştığından emin olmak için terminal üzerinden şu komutu çalıştırabilirsiniz:

```bash
`docker run hello-world`
```
Eğer her şey doğru bir şekilde kurulmuşsa, Docker başarılı bir şekilde çalıştığını belirten bir mesaj verecektir.

==**Sonuç**==
Docker’ı WSL 2 üzerinde kurarak, Docker Desktop ile başarılı bir şekilde entegrasyon sağlayarak konteynerleri çalıştırabilirsiniz. Hem Windows tarafında Docker Desktop üzerinden, hem de Ubuntu üzerinden Docker komutlarıyla işlemler yapabilirsiniz.
***


***Abdullah TANRIVERDİ***
