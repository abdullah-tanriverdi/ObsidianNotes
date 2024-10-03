#Yazılım #ProgramlamaDilleri #Dart 

Dart dilinde `var`, değişken tanımlamak için kullanılan bir anahtar kelimedir. Değişkenin türünü belirtmeden, Dart’ın otomatik olarak tür çıkarımı yapmasına olanak tanır. Değişkene ilk atanan değere bakarak Dart, o değişkenin türünü belirler.
```dart
var name = "Abdullah"; // String olarak algılanır.
var age = 25;          // int olarak algılanır.

```
`var` kullanarak değişkeni tanımladığında, ilk atanan değere göre değişkenin türünü sabitler. Yani, tür atandıktan sonra değiştirilemez.
```dart
var age = 25; // Türü int
age = "yirmi beş"; // Hata: String atanamaz, çünkü tür int olarak belirlenmiştir.

```
İlk değer atandığında Dart, değişkenin türünü tahmin eder ve o türü kullanır. Dolayısıyla, `var` ile değişken tanımlarken türü belirtmezsin, ancak tür yine de sabittir.

`var`, her zaman bir değer ile başlatılmalıdır. Başlatılmadan önce bir değere sahip olması zorunludur, çünkü Dart dilinde `var` kullanarak null değer atanamaz (null safety). Eğer null değere izin verilmesi gerekiyorsa, `int?`, `String?` gibi türler kullanılabilir.

**`var` Ne Zaman Kullanılır**

- Tür çıkarımını Dart’a bırakmak istediğinde `var` kullanmak uygundur.
- Kodun okunabilirliğini artırmak için `var` kullanabilirsin, ama kodun ne yaptığı anlaşılmalı. Eğer türü açıkça belirtmek daha uygun olacaksa, `int`, `String`, vb. kullanmak daha iyidir.

***
***Abdullah TANRIVERDİ***

  



