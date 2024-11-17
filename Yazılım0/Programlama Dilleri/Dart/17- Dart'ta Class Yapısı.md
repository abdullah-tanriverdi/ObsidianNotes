#Yazılım #ProgramlamaDilleri #Dart

Dart'ta bir sınıf, `class` anahtar kelimesi ile tanımlanır. Sınıf, bir nesnenin özelliklerini (değişkenler) ve davranışlarını (metotlar) içerir.
```dart
class Araba {
  String renk;
  int yil;

  // Yapıcı (constructor) metot
  Araba(this.renk, this.yil);

  void bilgiGoster() {
    print('Arabanın rengi: $renk, Yılı: $yil');
  }
}

```

> [!info]  Constructor Metotlar (Yapıcı)
> Class yapısı içerisinde değişkenler ve metotlar tanımlanabilir. Classın bir nesnesini oluşturmak için `new` anahtar kelimesi kullanılabilir. Ancak Dart'ta `new` anahtar kelimesi isteğe bağlıdır.


```dart
class Hayvan {
  String isim;
  int yas;

  // Constructor
  Hayvan(this.isim, this.yas);

  void bilgiGoster() {
    print('Hayvanın İsmi: $isim, Yaşı: $yas');
  }
}

void main() {
  // Hayvan sınıfından bir nesne oluşturma
  var benimHayvan = Hayvan('Kedi', 3);
  
  // Bilgileri gösterme
  benimHayvan.bilgiGoster(); // "Hayvanın İsmi: Kedi, Yaşı: 3" yazdırır
}

```

- **Getter ve Setter:**   Dart, özelliklere erişimi kontrol etmek için  getter ve setter yöntemlerini destekler.
```dart
   class Araba {
  String _renk; // Özel değişken
  int _yil;

  Araba(this._renk, this._yil);

  // Getter
  String get renk => _renk;

  // Setter
  set renk(String yeniRenk) {
    _renk = yeniRenk;
  }
}
```

- **Inheritance (Miras Alma):** Dart, bir sınıfın başka bir sınıftan türemesine olanak tanır. Alt sınıf, üst sınıfın tüm özelliklerini ve metotlarını miras alır.

```dart
class Araba {
  String renk;
  int yil;

  // Yapıcı (constructor) metot
  Araba(this.renk, this.yil);

  void bilgiGoster() {
    print('Arabanın rengi: $renk, Yılı: $yil');
  }
}

  
  class ElektrikliAraba extends Araba {
  int bataryaKapasitesi;

  ElektrikliAraba(String renk, int yil, this.bataryaKapasitesi) : super(renk, yil);

  void bataryaBilgisi() {
    print('Batarya Kapasitesi: $bataryaKapasitesi kWh');
  }
}
```






- **Abstract Sınıfı (Soyut):**  Soyut sınıflar, temel işlevselliği tanımlamak ve bazı metotların alt sınıflar tarafından gerçekleştirilmesini sağlamak için kullanılır.

```dart

  abstract class Hayvan {
  // Soyut metot
  void sesCikar();

  void bilgiGoster() {
    print('Ben bir hayvanım.');
  }
}

class Kedi extends Hayvan {
  @override
  void sesCikar() {
    print('Miyav!');
  }
}

class Kopek extends Hayvan {
  @override
  void sesCikar() {
    print('Hav!');
  }
}

void main() {
  Hayvan kedi = Kedi();
  Hayvan kopek = Kopek();

  kedi.bilgiGoster(); // "Ben bir hayvanım." yazdırır
  kedi.sesCikar();    // "Miyav!" yazdırır

  kopek.bilgiGoster(); // "Ben bir hayvanım." yazdırır
  kopek.sesCikar();    // "Hav!" yazdırır
}
```




- **Nested Classes (İç İçe):**  Dart, bir sınıfın içinde başka bir sınıf tanımlamaya da izin verir.
```dart
  class DışSınıf {
  class İçSınıf {
    void mesajYaz() {
      print('İç Sınıftan Merhaba!');
    }
  }
}
```


- **Statik Değişkenler ve Metotlar:**  Statik değişkenler ve metotlar, sınıfın bir örneği olmadan erişilebilen özelliklerdir
```dart
  class Matematik {
  static int toplama(int a, int b) {
    return a + b;
  }
}

void main() {
  print(Matematik.toplama(5, 10)); // Çıktı: 15
}
```


- **Mixins:**  Dart, birden fazla sınıfın özelliklerini bir arada kullanmak için mixin'leri destekler.
```dart
  mixin Hızlı {
  void hızlıGit() {
    print('Hızlı gidiyor.');
  }
}

class YarışAraba with Hızlı {
  void yarış() {
    hızlıGit();
  }
}
```

***
***Abdullah TANRIVERDİ***