#Yazılım #ProgramlamaDilleri #Dart 

![[Dart_Operatörleri.png]]

Bir operatör, değerleri işlemek veya işleneni üzerinde işlemler gerçekleştirmek için kullanılan bir semboldür.Dart, çeşitli türdeki işlemleri gerçekleştirmek için kapsamlı bir yerleşik operatörler kümesi sağlar. Operatörler tekli veya ikili olabilir, yani tekli yalnızca bir işlenen alır ve ikili operatörlerle iki işlenen alır. Birkaç tür operatör vardır

**Operatör Türleri**
- Aritmetik Operatörleri
- Tekli Operatörler
- Atama Operatörleri
- İlişkisel Operatörleri
- Tip Testi Operatörleri
- Mantıksal Operatörleri
- Bitsel Operatör
- Koşullu Operatörler
- Casecade Notasyonu(..) Operatörleri
<br>

==**Aritmetik Operatörler:**== Matematiksel işlemler yapmak için kullanılır.

- `+` : Toplama
- `-` : Çıkarma
- `*` : Çarpma
- `/` : Bölme
- `~/` : Tam sayı bölme (kesirli kısım atılır)
- `%` : Mod alma (kalan)
  
```dart
int a = 10;
int b = 3;
print(a + b); // 13
print(a - b); // 7
print(a * b); // 30
print(a / b); // 3.3333...
print(a ~/ b); // 3
print(a % b); // 1

```

<br>

==**Tekli Operatörler:**== İki şekilde kullanılabilir - sonek ve önek. ++ sonek olarak kullanılırsa (x++ gibi), önce operand değerini döndürür, sonra x değerini artırır. -- önek olarak kullanılırsa (++x gibi), x değerini artırır.

|Sıra|Operatör Adı|Tanım|Örnek|
|---|---|---|---|
|1.|++ (Önek)|İşlenenin değerini artırır.|`++x`|
|2.|++ (Sonek)|Arttırmadan önce işlenenin gerçek değerini döndürür.|`x++`|
|3.|-- (Önek)|İşlenenin değerini azaltır.|`--x`|
|4.|-- (Sonek)|Azaltma işleminden önce işlenenin gerçek değerini döndürür.|`x--`|
<br>

==**Atama Operatörleri:**==   Bir değişkene bir değer atamak için kullanılır. Dart'ta atama işlemi için `=` kullanılır. Ayrıca, kısayol atama operatörleri de bulunmaktadır.

- `=` : Atama
- `+=` : Toplayarak atama
- `-=` : Çıkararak atama
- `*=` : Çarparak atama
- `/=` : Bölerek atama
- `%=` : Mod alarak atama


```dart
int a = 5;
a += 3; // a = a + 3
print(a); // 8
a -= 2; // a = a - 2
print(a); // 6

```
<br>

==**İlişkisel Operatörler:**==  İki değer arasındaki ilişkiyi karşılaştırmak için kullanılır.

|Operatör|Açıklama|Örnek|
|---|---|---|
|`==`|Eşitlik operatörü. İki değerin eşit olup olmadığını kontrol eder.|`a == b`|
|`!=`|Eşitsizlik operatörü. İki değerin eşit olmaması durumunu kontrol eder.|`a != b`|
|`>`|Büyük olma durumu. Sol operandın sağ operandan büyük olup olmadığını kontrol eder.|`a > b`|
|`<`|Küçük olma durumu. Sol operandın sağ operandan küçük olup olmadığını kontrol eder.|`a < b`|
|`>=`|Büyük veya eşit olma durumu. Sol operandın sağ operandan büyük veya eşit olup olmadığını kontrol eder.|`a >= b`|
|`<=`|Küçük veya eşit olma durumu. Sol operandın sağ operandan küçük veya eşit olup olmadığını kontrol eder.|`a <= b`|

<br>

==**Tip Test Operatörler:**==  Bir nesnenin belirli bir türde olup olmadığını kontrol etmek için kullanılır. Bu operatörler, nesne yönelimli programlama dillerinde tür güvenliğini sağlamaya yardımcı olur.

|Operatör|Açıklama|Kullanım Örneği|Hata Durumu|
|---|---|---|---|
|`is`|Bir nesnenin belirtilen türde olup olmadığını kontrol eder.|`if (x is String)`|Yok (true veya false döner)|
|`is!`|Bir nesnenin belirtilen türde **olmaması** durumunu kontrol eder.|`if (x is! int)`|Yok (true veya false döner)|
|`as`|Bir nesneyi belirtilen bir türe dönüştürmeye çalışır.|`String str = x as String;`|TypeError (dönüşüm mümkün değilse)|
```dart
void main() {
  var value = 42; // value bir int

  // is operatörü
  if (value is int) {
    print('value bir int.'); // Çalışır
  }

  // is! operatörü
  if (value is! String) {
    print('value bir String değil.'); // Çalışır
  }

  // as operatörü
  var anotherValue = 'Dart'; // anotherValue bir String
  String strValue = anotherValue as String; // Dönüşüm başarılı
  print(strValue); // "Dart" yazdırır

  // Hatalı dönüşüm örneği
  try {
    int intValue = anotherValue as int; // Hata fırlatılır
  } catch (e) {
    print('Hata: $e'); // Hata mesajını yazdırır
  }
}

```
<br>

==**Mantıksal Operatörler:**==  Bir veya daha fazla koşulun doğruluğunu kontrol etmek için kullanılır. Bu operatörler, Boolean değerler (true veya false) ile çalışır ve genellikle `if` koşullarında, döngülerde ve diğer mantıksal ifadelerde kullanılır.

| Operatör | Açıklama                                                                       | Örnek               |
| -------- | ------------------------------------------------------------------------------ | ------------------- |
| \|\|     | VEYA operatörüdür. İki koşuldan birisi doğruysa(true), true değerini döndürür. | 8>5 \|\| 5<4 (true) |
| &&       | VE operatörüdür.İki koşulda doğruysa(true), true değerini döndürür.            | 8>5 && 5<4 (false)  |
| !        | DEĞİL operatörüdür. Koşulun tersi olan değeri döndürür.                        | !(4>5) (true)       |
<br>

==**Bitsel Operatörler:**==  İki işlenenin değeri üzerinde bit bit işlem gerçekleştirir.

| **Operatör** | **Açıklama**                                                                             |
| ------------ | ---------------------------------------------------------------------------------------- |
| `&`          | İkili VE: Her iki bit de 1 ise 1 döner.                                                  |
| \|           | İkili VEYA: Herhangi bir bit 1 ise 1 değerini döndürür.                                  |
| `^`          | İkili XOR: Her iki bit farklıysa 1 döner.                                                |
| `~`          | Birler Tamamlayanı: Bitin tersini döner (0, 1 olur; 1, 0 olur).                          |
| `<<`         | Soldan Kaydırma: Sol operanın değerini sağ operandaki bit sayısı kadar sola kaydırır.    |
| `>>`         | Sağdan Kaydırma: Sağ operanın değerini soldaki operandın bit sayısı kadar sağa kaydırır. |

<br>

==**Koşullu Operatörler:**== Belirli koşullara bağlı olarak farklı değerler döndürmek için kullanılır.

|**Operatör**|**Açıklama**|
|---|---|
|`? :`|Koşul Operatörü (Ternary Operator): Bir koşulun doğru veya yanlış olmasına göre farklı değerler döndürür.|
|`??`|Null Koalesans Operatörü: Sol taraf `null` ise sağ tarafın değerini döner.|
|`??=`|Null Koalesans Atama Operatörü: Eğer sol taraf `null` ise sağ tarafın değerini sol tarafa atar.|
- ***Ternary Opearatör***
```dart
int a = 5;
String result = (a > 3) ? 'Büyük' : 'Küçük';
print(result); // 'Büyük' döner

```

- ***Null Koalesans Opearatör***
```dart
String? name;
String displayName = name ?? 'Misafir';
print(displayName); // 'Misafir' döner

```

- ***Null Koalesans Atama Operatörü***
```dart
String? name;
name ??= 'Misafir';
print(name); // 'Misafir' döner

```
<br>

==**Cascade Notasyonu(..) Operatörü:**==  Bir nesne üzerinde birden fazla işlem yapmayı kolaylaştırır. Bu operatör, aynı nesne üzerinde birden fazla özellik veya metot çağrısı yapmanıza olanak tanır. Bu sayede kodun okunabilirliği artar ve daha az tekrar yazım yapılır.
```dart
class Cat {
  String name = '';
  int age = 0;

  void meow() {
    print('$name says: Meow!');
  }
}

void main() {
  var myCat = Cat()
    ..name = 'Minnoş'  // Kedi ismini atıyoruz
    ..age = 2          // Kedi yaşını atıyoruz
    ..meow();          // Kedi havlamasını sağlıyoruz
}
//ÇIKTI: Minnoş says: Meow!
```
**Kod Açıklaması**

- **Kedi Sınıfı**: `Cat` adında bir sınıf tanımlıyoruz. Bu sınıfın `name` (isim) ve `age` (yaş) adında iki özelliği ve `meow` (havlama) adında bir metodu var.
- **Cascade Notasyonu**: `myCat` nesnesi oluşturulurken cascade notasyonu kullanıyoruz.
    - Önce `name` özelliğini `Minnoş` olarak ayarlıyoruz.
    - Ardından `age` özelliğini `2` olarak ayarlıyoruz.
    - Son olarak, `meow` metodunu çağırarak kedimizin havlamasını sağlıyoruz.
<br>

***Abdullah TANRIVERDİ***