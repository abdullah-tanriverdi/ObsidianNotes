#Yazılım #ProgramlamaDilleri #Dart 

Bir program çalışırken beklenmedik durumlar (hatalar veya istisnalar) ortaya çıkabilir. `try-catch` yapısı, bu hataları yakalayarak programın çökmesini önler ve hatayı kontrollü bir şekilde işleme imkânı sağlar.

- **`try` Bloğu:** Hata oluşturabilecek kodlar `try` bloğuna yazılır. Eğer `try` bloğu içinde bir hata meydana gelirse, bu hata yakalanarak `catch` bloğuna iletilir.`try` bloğu çalıştığında hata oluşmazsa, `catch` bloğu devreye girmez.
  
```dart
try {
  var result = 10 ~/ 0; // Bu satır hata verecek (sıfıra bölme hatası)
}

```

- **`catch` Bloğu:** `try` bloğu içinde meydana gelen hatayı yakalar ve bu hataya uygun işlemler yapmanı sağlar. `catch` bloğu parametre olarak hatayı alabilir. Bu parametre genellikle `e` olarak adlandırılır ve hata hakkında bilgi verir.
```dart
try {
  var result = 10 ~/ 0; // Sıfıra bölme hatası
} catch (e) {
  print('Bir hata oluştu: $e');
}

```

- **`on` Anahtar Kelimesi:**  Eğer sadece belirli bir hata türünü yakalamak istersen, `on` anahtar kelimesini kullanabilirsin. `on`, belirli türdeki hatalar için kullanılır.

```dart
try {
  int number = int.parse("abc"); // FormatException hatası verecek
} on FormatException {
  print('Format hatası oluştu!');
} catch (e) {
  print('Bilinmeyen bir hata: $e');
}

```

- **`finally` Bloğu:**  `try` veya `catch` bloklarında hata oluşup oluşmadığına bakmaksızın her durumda çalıştırılan bir koddur. Genellikle kaynakları temizlemek veya işlemi sonlandırmak için kullanılır.
```dart
try {
  var result = 10 ~/ 2;
} catch (e) {
  print('Hata: $e');
} finally {
  print('Bu kod her zaman çalışacak.');
}

```

-  **`rethrow` Bloğu:** Bazen bir hatayı yakalayıp işledikten sonra, aynı hatayı başka bir koda iletmek isteyebilirsin. Bunun için `rethrow` kullanılır. `rethrow`, hatayı tekrar fırlatır.

```dart
try {
  var result = 10 ~/ 0;
} catch (e) {
  print('Hata yakalandı: $e');
  rethrow; // Hata tekrar fırlatılır
}

```


> [!info] HATA TÜRLERİ
> - **`Exception`**: Genel hata sınıfıdır. Çoğu hata bu sınıftan türetilir.
>- **`Error`**: Programın devam edemeyeceği ciddi hatalar için kullanılır.
>- **`throw:`**: Dart’ta kendi hata sınıflarını oluşturabilir ve `throw` ile bu hataları fırlatabilirsin.


***
***Abdullah TANRIVERDİ***

  
