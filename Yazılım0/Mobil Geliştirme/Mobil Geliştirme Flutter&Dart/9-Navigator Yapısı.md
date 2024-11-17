#Yazılım #MobilGeliştirme #MobilGeliştirmeFlutterDart 

Flutter’da **Navigator** widget'ı, uygulama içerisinde farklı ekranlar (veya sayfalar) arasında geçiş yapmayı sağlayan bir yapı olarak çalışır. Navigator, uygulamanın "yığın" (stack) mantığıyla ekranları yönetmesine olanak tanır. Bu yığındaki her bir ekran, kullanıcı arayüzünde sıralı bir şekilde gösterilip geri dönüldüğünde aynı sırayı izler.

==**Navigator Yığını**==
Flutter'da Navigator, sayfaları bir yığın (stack) üzerinde tutar:
- Yığına eklenen her yeni sayfa, önceki sayfanın üzerine konur ve kullanıcıya gösterilir.
- Kullanıcı geri döndüğünde, yığındaki en üstteki sayfa kaldırılır, alttaki sayfa tekrar gösterilir.

Bu yapı sayesinde önceki sayfalara geri dönme  veya yeni sayfalar ekleme işlemleri basit ve etkili bir şekilde yönetilir.

==**Sayfa Yönlendirme Yöntemleri**==
Flutter'da Navigator ile sayfalar arasında yönlendirme yapmak için birkaç temel yöntem vardır:

- **push()**: Yeni bir sayfayı Navigator yığınına ekler. Bu işlem, kullanıcıyı yeni bir ekrana götürür ve o ekranı aktif hale getirir.
```dart
Navigator.push(
  context,
  MaterialPageRoute(builder: (context) => YeniEkran()),
);

```

- **pop()**: Navigator yığınının en üstündeki sayfayı kaldırır ve bir önceki ekrana geri dönülmesini sağlar.
```dart
Navigator.pop(context);

```


- **pushReplacement()**: Yığındaki mevcut sayfayı yeni bir sayfayla değiştirir. Bu yöntemle geçiş yapılan sayfa geri dönülemeyecek şekilde yer değiştirilmiş olur.
```dart
Navigator.pushReplacement(
  context,
  MaterialPageRoute(builder: (context) => YeniEkran()),
);

```

- **pushAndRemoveUntil()**: Belirtilen koşula göre tüm sayfaları Navigator yığından temizler ve yeni bir sayfa açar. Bu, genellikle uygulama içerisindeki bir ana ekrana geri dönme işlemi için kullanılır.
```dart
Navigator.pushAndRemoveUntil(
  context,
  MaterialPageRoute(builder: (context) => AnaEkran()),
  (Route<dynamic> route) => false,
);

```
==**Navigator 2.0 ve Route Management**==
Flutter’ın Navigator yapısı, temel yönlendirme işlemleri için oldukça işlevsel olsa da, karmaşık uygulamalarda yönetimi zorlaşabilir. Bu yüzden Flutter 2.0 ile birlikte daha gelişmiş bir yönlendirme çözümü olan **Router API** tanıtılmıştır.
- Router API, daha karmaşık navigasyon gereksinimlerini karşılar, özellikle web uygulamaları veya çok sayfalı projelerde daha iyi bir kullanıcı deneyimi sağlar.
- Router API ile uygulama rotalarını doğrudan yapılandırmak ve durum yönetimini kullanarak ekran geçişlerini kontrol etmek mümkündür.

> [!tip] İPUCU
> Router API hakkında bilgi almak için bağlantıya tıkla [[-Router API]]


Flutter’da Navigator, uygulamanın farklı ekranlar arasında geçiş yapmasını sağlayan güçlü bir yönlendirme aracıdır. Yığın tabanlı yapısı ile kullanıcı deneyimini basit ve akıcı hale getirir. Flutter’ın sunduğu Navigator özellikleri, uygulamanın ihtiyaçlarına göre kolayca uyarlanabilir ve gerektiğinde Router API gibi gelişmiş çözümlerle desteklenebilir.
****

***Abdullah TANRIVERDİ***




