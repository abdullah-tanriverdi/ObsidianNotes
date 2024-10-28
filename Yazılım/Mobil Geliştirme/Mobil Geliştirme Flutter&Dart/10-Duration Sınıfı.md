#Yazılım #MobilGeliştirme #MobilGeliştirmeFlutterDart 

**Duration**, Flutter’da ve Dart dilinde zaman aralıklarını temsil etmek için kullanılan bir sınıftır. Bir işlemi belirli bir süre boyunca bekletmek, animasyonların hızını ayarlamak, zamanlayıcılar veya gecikmeler gibi işlemler için Duration sınıfı kullanılır. Bu sınıf sayesinde saniye, dakika, saat gibi çeşitli birimlerde süre tanımlanabilir ve bu süreler uygulamanın farklı alanlarında kolayca kullanılabilir.

==**Duration Sınıfının Yapısı**==
`Duration` sınıfı, milisaniye, saniye, dakika, saat ve gün gibi farklı birimlerde süreyi ifade etmek için çeşitli yapıcı fonksiyonlar sunar.
```dart
Duration(seconds: 2);     // 2 saniye
Duration(milliseconds: 500); // 500 milisaniye
Duration(minutes: 1);      // 1 dakika
Duration(hours: 5);        // 5 saat
Duration(days: 3);         // 3 gün

```
==**Duration ile Zamanlayıcılar ve Gecikmeler**==
Duration sınıfı, zamanlayıcı fonksiyonlar ve gecikmeler ile birlikte sıklıkla kullanılır.

- **Future.delayed**: Belirli bir süre gecikmeyle bir işlemi başlatmak için kullanılır.
```dart
Future.delayed(Duration(seconds: 3), () {
  print('Bu mesaj 3 saniye sonra gösterilecek');
});

```
- **Timer**: Bir işlemi periyodik veya belirli bir süre sonra başlatmak için Timer sınıfı Duration ile birlikte kullanılır.
```dart
Timer(Duration(seconds: 5), () {
  print('Bu mesaj 5 saniye sonra gösterilecek');
});

```

- **Animasyonlar (`AnimationController`)**: Animasyonların süresini belirlemek için Duration kullanılır.
```dart
AnimationController controller = AnimationController(
  vsync: this,
  duration: Duration(seconds: 2),
);

```

-  **Geçiş Efektleri (`AnimatedContainer`, `AnimatedOpacity`)**: Görsel geçişlerde belirli sürelerle efekt oluşturmak için Duration kullanılır.
```dart
AnimatedOpacity(
  opacity: 0.5,
  duration: Duration(milliseconds: 500),
  child: Container(
    color: Colors.blue,
  ),
);

```

==**Duration Değerini Okuma**==
Bir Duration nesnesinin toplam süresini belirli birimlerde almak için çeşitli özellikler bulunur:
- `inDays`: Toplam günü döner.
- `inHours`: Toplam saati döner.
- `inMinutes`: Toplam dakikayı döner.
- `inSeconds`: Toplam saniyeyi döner.
- `inMilliseconds`: Toplam milisaniyeyi döner.
- `inMicroseconds`: Toplam mikrosaniyeyi döner.
****
***Abdullah TANRIVERDİ***

