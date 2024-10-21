#Yazılım #MobilGeliştirme #MobilGeliştirmeFlutterDart

Splash screen, uygulamanız açıldığında ilk olarak görünen ekranı temsil eder. Genellikle markanın logosu veya uygulamanın adı gibi içerikler barındırır.


==**Gerekli Paketleri Yükleme**==

Splash screen'iniz için `flutter_native_splash` adlı paketi kullanarak yerel ayarların da yapılır. Bu paket, hem Android hem de iOS için özelleştirilebilir bir splash screen sağlar.
Projenin `pubspec.yaml` `dependencies` altına bağımlılık eklenmelidir.Bağımlılık eklendikten sonra `pub get` ile projeye import et.

```yaml
dependencies:
  flutter:
    sdk: flutter
  flutter_native_splash: ^2.4.1  # Son sürümü kontrol edin

```
==**Splash Screen Ayarları**==

`flutter_native_splash` paketini kullanarak splash screen ayarları yapmak için,
ek bir dosya oluşturup orada özelleştirilebilinir`native_splash_screen.yaml` .
```yaml
flutter_native_splash:  
  # Android için splash ekranını etkinleştiriyoruz.  
  android: true  
  
  # iOS için splash ekranını etkinleştiriyoruz.  
  ios: true  
  
  # Web için splash ekranını devre dışı bırakıyoruz.  
  web: false  
  
  # Splash ekranının arka plan resmini belirliyoruz.  
  background_image: "assets/image/background.png"  
  
  # Splash ekranında gösterilecek logoyu belirtiyoruz.  
  image: "assets/image/logo.png"  
  
  # Splash ekranında kullanılacak markalama resmini belirliyoruz.  
  branding: "assets/image/branding.png"  
  
  # Koyu tema için arka plan resmini belirliyoruz.  
  background_image_dark: "assets/image/background_dark.png"  
  
  # Koyu tema için gösterilecek logoyu belirtiyoruz.  
  image_dark: "assets/image/logo.png"  
  
  # Koyu tema için kullanılacak markalama resmini belirliyoruz.  
  branding_dark: "assets/image/branding.png"  
  
  # Android 12 için özel ayarlar.  
  android_12:  
    # Android 12 splash ekranı için arka plan rengini belirtiyoruz.  
    color: "#1a1967"  
  
    # Android 12'de gösterilecek logoyu belirtiyoruz.  
    image: "assets/image/android12_logo.png"  
  
    # Android 12'de kullanılacak markalama resmini belirtiyoruz.  
    branding: "assets/image/android12_branding.png"
```
Düzenleme yapıldıktan sonra terminal istemcisinde ==`flutter pub run flutter_native_splash:create --path=native_splash_screen.yaml`== bu komutu çalıştırıp dosyayı güncel tutabilirsin. 

==**Görsel Ekleme**==
`assets` adlı bir klasör oluşturup orada gerekli dosyaları yükledikten sonra `pubspec.yaml` dosyasında `assets` kısmında tanımlamaları yap
```yaml
flutter:
  assets:
    - assets/logo.png

```
==**Görsel Ayarları**==

![[asset_dimensions_ios_android11below.png]]![[asset_dimensions_ios_android12above.png]]

==**Kod Kısmı**==
Gerekli kütüphane import edilmeli 
```dart
// flutter_native_splash kütüphanesini içe aktarıyoruz. Bu kütüphane, uygulamanın başlangıcında bir splash ekranı göstermemizi sağlar.  
import 'package:flutter_native_splash/flutter_native_splash.dart';
```

```dart
void main() {  
  
  // Flutter uygulamasını başlatmak için gerekli olan WidgetsBinding'i oluşturuyoruz.  
  WidgetsBinding widgetsBinding = WidgetsFlutterBinding.ensureInitialized();  
  
  // Uygulamanın splash ekranını korumak için FlutterNativeSplash kütüphanesini kullanıyoruz.  
  FlutterNativeSplash.preserve(widgetsBinding: widgetsBinding);  
  
// Uygulamayı başlatıyoruz.  
  runApp(const MyApp());  
}
```
**Açıklama:**

==WidgetsBinding.initialize():==

- **Amacı**: Flutter'ın gerekli kaynakları yüklemesini ve uygulamanın düzgün bir şekilde başlatılmasını sağlar.
- **Kullanımı**: `WidgetsFlutterBinding.ensureInitialized();`


==FlutterNativeSplash.preserve():==

- **Amacı**: Splash screen'i başlatma sırasında korur ve uygulama tamamen yüklenene kadar görünür kalmasını sağlar.
- **Kullanımı**: `FlutterNativeSplash.preserve(widgetsBinding: widgetsBinding);`


```dart
void initialization() async {  
  // Uygulama açılışında 3 saniye beklemek için bir gecikme ekliyoruz.  
  print ("pausing...");  
  await Future.delayed(const Duration(seconds: 3));  
  print("unpausing...");  
  // Gecikme tamamlandıktan sonra splash ekranını kaldırıyoruz.  
  FlutterNativeSplash.remove();  
}

```
**Açıklama:**

==Future.delayed():==

- **Amacı**: Belirli bir süre boyunca (örneğin, 3 saniye) işlemi durdurur ve splash screen'i gösterir.
- **Kullanımı**: `await Future.delayed(Duration(seconds: 3));`

==FlutterNativeSplash.remove():==

- **Amacı**: Splash screen süresi dolduktan sonra splash ekranını kaldırır.
- **Kullanımı**: `FlutterNativeSplash.remove();`

```dart
void initState(){  
  super.initState();  
  // Uygulama başlatıldığında initialization fonksiyonunu çağırıyoruz  
  initialization();  
}
```

Tüm bu konfigürasyonlar uygulama açıldığında, belirttiğimiz süre boyunca splash screen gösterilecek ve ardından istenildiği sayfaya yönlendirilir.
***
***Abdullah TANRIVERDİ***

