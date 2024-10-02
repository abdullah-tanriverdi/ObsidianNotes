#Yazılım #ProgramlamaDilleri #Dart 

Dart, güçlü bir tip sistemine sahip bir programlama dili olduğundan, her değişkenin bir veri tipi vardır.

**Dart Temel Veri Tipleri**

-  ==***int(Tam Sayılar):***== `int` veri tipi, tam sayıları (negatif,pozitif ve sıfır) temsil eder.

```dart
int yas = 25;
int negatifSayi = -10;

```


- ==***double(Ondalıklı Sayılar):***== `double`, ondalıklı sayıları temsil eder ve kayan noktalı sayılarla çalışır.

```dart
double sicaklik = 36.5;
double pi = 3.14159;

```


- ==***String(Metin):***== `String` tipi, metin ya da karakter dizilerini temsil eder. 

```dart
String isim = 'Abdullah';
String selamlama = "Merhaba, Dünya!";

```


- ==***bool(Mantıksal Tip):***== `bool`, mantıksal değerleri temsil eder. Sadece true veya false değerlerini alabilir.

```dart
bool aktif = true;
bool hatali = false;

```


- ==***List(Dizi/Listeler):***== `List` bir veri koleksiyonunu saklar. Aynı veri tipindeki birden fazla öğeyi bir arada tutabilir.Sıfırdan başlayan indeksleme kullanılarak erişilir.


```dart
List<int> sayilar = [1, 2, 3, 4, 5];
List<String> isimler = ['Ali', 'Ayşe', 'Mehmet'];

```

- ==***Map(Anahtar-Değer Çifti):***== `Map`, anahtar-değer çiftlerini saklar.Her anahtar bir değere karşılık gelir.

```dart
Map<String, int> yaslar = {
  'Ali': 25,
  'Ayşe': 30,
  'Mehmet': 40
};

```

- ==***Set(Benzersiz Değerler):***== `Set`, benzersiz değerlerden oluşan bir koleksiyondur. Aynı değer birden fazla kez eklenemez.

```dart
Set<String> meyveler = {'elma', 'armut', 'muz'};

```

- ==***Null:***== `null` değeri, bir değişkenin değerinin olmadığını ifade eder. Dart'ın yeni sürümüyle birlikte, null güvenliği sağlanmıştır.

```dart
String? ad = null;

```
Bu veri tipleri, Dart programlama dilinde değişkenleri tanımlarken ve verileri işleriken sıkça kullanılır.Her bir veri tipi, belirli bir amaca hizmet eder ve programın ihtiyaçlarına göre seçilir.

***Abdullah TANRIVERDİ***

