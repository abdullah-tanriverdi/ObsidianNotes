#Yazılım #ProgramlamaDilleri #Dart 

![[Dart_NullSafety.png|500]]
Dart'ta **Null Safety (Null Güvenliği)**,geliştiricilerin yazdığı kodda `null` değerlerin neden olduğu hataları en aza indirmek için tasarlanmış bir özelliktir. Dart 2.12 sürümünden itibaren kullanılabilir hale gelmiştir ve değişkenlerin `null` değer alıp almayacağını açıkça belirtmemizi sağlar. Bu özellik, yazılım geliştirirken daha güvenli ve hatasız bir deneyim sunar.

**Null Safety Temel Kavramlar**

- ==**Null Olabilir Ve Olamaz Değişkenler:**== Dart'ta bir değişkenin `null` olabilmesi için `?` işareti tanımlanmalıdır.Eğer bir değişken `null` olamazsa `?` kullanılmadan tanımlanmalıdır.
```dart
void main() {
  int a = 5; // 'a' null olamaz
  int? b;    // 'b' null olabilir
  b = 10;    // 'b' artık 10
  print(b);  // 10
}

```
<br>
- ==**Null Kontrolü:**==  Null safety, `null` kontrolü yapmanızı kolaylaştırır. `?` operatörüyle `null` değerleri kontrol edebiliriz.

```dart
void main() {
  int? number; // 'number' null olabilir
  
  if (number != null) {
    print(number * 2); // 'number' null değilse bu kod çalışır
  } else {
    print("Number null");
  }
}

```

- ==**Null Dereference Hatasının Önlenmesi:**== Eğer `null` olamayacak bir değişkene erişmeye çalışırsanız, Dart bir hata fırlatır. Bu, geliştiricilerin `null` değerlerin neden olduğu hataları önlemesine yardımcı olur.

```dart
void main() {
  int a = 5;
  // int? b; // Bu hata verir çünkü 'b' null olabilir.
  // print(b * 2); // Bu hata verir çünkü 'b' null.
}

```

**`late` Anahtar Kelimesi:** Bir değişkenin daha sonra başlatılacağını belirtir. `late` anahtar kelimesi, değişkenin başında bir değer olmadan kullanılmasına olanak tanır, ancak kullanılmadan önce kesinlikle bir değer atanmış olmalıdır.
```dart
void main() {
  late String name; // Başlangıçta null, ancak daha sonra atanacak
  
  // name = "Abdullah"; // Burada bir değer atanabilir.
  
  // name = "Ali"; // Değişken geç başlatılabilir.
  print(name); // Bu kod çalıştırıldığında hata fırlatır çünkü 'name' null.
}

```



> [!tldr] ÖZET
> Dart'ta null safety, yazılım geliştirirken daha güvenli ve hatasız bir deneyim sunar. Değişkenlerin `null` alıp almayacağını açıkça belirleyerek, `null` referans hatalarını minimize eder. Bu özellikleri kullanarak daha güvenilir ve sürdürülebilir kod yazılabilinir.
> 

****
***Abdullah TANRIVERDİ***