#Yazılım #ProgramlamaDilleri #Dart 
Dart dilinde konsol girdisi almak için `dart:io` kütüphanesini kullanarak kullanıcıdan veri alınır. Bu kütüphane, konsoldan giriş yapmak için gerekli araçları sağlar.

**Basit Bir Konsol Girdisi Programı**
```dart
import 'dart:io';

void main() {
  // Kullanıcıdan isim girişi al
  stdout.write("Lütfen isminizi girin: "); // Kullanıcıdan girdi almak için yazdırır
  String? name = stdin.readLineSync(); // Kullanıcının girdiği metni okur

  // Girişin null olup olmadığını kontrol et ve ekrana yazdır
  if (name != null) {
    print("Merhaba, $name!");
  } else {
    print("Giriş alınamadı.");
  }
}

```
 **Açıklamalar:** 
 -  **`import 'dart:io';`**: `dart:io` kütüphanesini içe aktararak, konsol girişi ve çıktısı ile ilgili sınıfları ve fonksiyonları kullanılır.
 - **`stdout.write()`**: Kullanıcıdan bir girdi alırken bir mesaj yazdırmak için kullanılır. `print()` yerine `stdout.write()` kullanılması, girdi için beklenen mesajın hemen ardından kullanıcının yanıtını almasına olanak tanır.
 - **`stdin.readLineSync()`**: Konsoldan bir satır girişi alır. Kullanıcı bir metin girdikten sonra, bu metni bir `String` olarak döndürür. Eğer kullanıcı bir değer girmezse, sonuç `null` olacaktır.

> [!NOTE]
> Konsoldan alınan giriş her zaman bir `String` olarak gelir.

```dart
import 'dart:io';

void main() {
  stdout.write("Lütfen bir sayı girin: ");
  String? input = stdin.readLineSync();
  
  // Girişin null olup olmadığını kontrol et
  if (input != null) {
    int number = int.parse(input); // String'i int'e dönüştür
    print("Girdiğiniz sayının karesi: ${number * number}");
  } else {
    print("Giriş alınamadı.");
  }
}

```
***Abdullah TANRIVERDİ***
