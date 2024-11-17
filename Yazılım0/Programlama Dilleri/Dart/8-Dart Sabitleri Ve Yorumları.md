#Yazılım #ProgramlamaDilleri #Dart 

==**Dart Sabitleri (Constants):**== Dart dilinde sabitler, bir kez tanımlandıktan sonra değişmeyen değerlerdir. Dart’ta sabitler iki farklı anahtar kelime ile tanımlanır: `const`  ve `final`. Her ikisi de sabit değerler oluşturmak için kullanılır, ancak aralarındaki farklar önemlidir.

**`final` Sabitleri:**  Değişkenin değerini sadece bir kez atamamıza izin verir. Bu değer, programın çalışması sırasında atanabilir ancak atandıktan sonra değiştirilemez.`final` değişkenlerin değeri çalışma zamanında belirlenebilir.

```dart
final int age = 30;
final currentTime = DateTime.now(); // Çalışma zamanında atanır

```

**`const` Sabitleri:**  Derleme zamanında bilinen ve sabit olan değerlerdir. `const` ile tanımlanan bir değişkenin değeri derleme sırasında belirlenmelidir ve asla değiştirilemez.`const` değerleri, hem derleme zamanında hem de çalışma zamanında sabit olmalıdır.

```dart
const int year = 2024;
const pi = 3.14159; // Sabit bir matematiksel değer

```
**`final` Ve `const` Arasındaki Farklar:** 
- `final` değişkenler çalışma zamanında (runtime) atanabilir, ancak `const` değişkenler derleme zamanında (compile-time) sabitlenmiş olmalıdır.
- `const` ile tanımlanan değerler sabittir ve her zaman sabit kalır. `final` ile tanımlanan değişkenler de sabittir, ancak sadece ilk atamadan sonra sabitlenir.
```dart
final a = DateTime.now();  // Geçerli zaman çalışma zamanında belirlenir
const b = 5;               // Derleme zamanında sabit bir değer

```
<br>

==**Dart Yorum Satırları (Comments):**== Yorum satırları, kod içerisinde açıklamalar yaparak kodunuzu daha anlaşılır hale getirmek için kullanılır. Dart’ta üç farklı türde yorum kullanılır.

-  **Tek Satırlık Yorumlar:** `//` ile başlar ve sadece o satırdaki açıklamayı içerir.
  
- **Çok Satırlı Yorumlar:** `/*` ile başlar ve `*/` ile biter. Birden fazla satırda açıklama yapmanız gerektiğinde kullanılır.
  
- **Dökümantasyon Yorumlar:**   `///` ile başlayan yorumlar dokümantasyon amaçlı kullanılır. Bu tür yorumlar, bir sınıf veya fonksiyon hakkında detaylı bilgi vermek için kullanılır.
  

>[!tldr] KISACA
>Yorumlar, özellikle büyük projelerde kodun daha anlaşılır kılmak ve başkalarının (veya gelecekte kendinizin) kodu daha kolay anlamasını sağlamak için önemlidir. Sabitler ise sabit kalan verileri kodunda güvenli ve tutarlı bir şekilde kullanmanı sağlar.

***Abdullah TANRIVERDİ***


