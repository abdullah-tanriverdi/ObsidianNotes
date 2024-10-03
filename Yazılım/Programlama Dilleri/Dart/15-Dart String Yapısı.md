#Yazılım #ProgramlamaDilleri #Dart 

![[Dart_String.jpg|500]]
`String` yapısı, metin verilerini temsil eden bir veri tipidir. Dart, Unicode karakter setini destekler, bu da farklı dillerdeki karakterlerin kullanılmasına olanak tanır.

-  **String Tanımlama:**  Dart'ta `String` değerleri, tek tırnak (`'`) veya çift tırnak (`"`) içinde tanımlanabilir. İkisi arasında bir fark yoktur.

```dart
String greeting = 'Merhaba, dünya!';
String anotherGreeting = "Merhaba, Dart!";

```

-  **String İçinde Değişken Kullanımı:** Dart'ta string içerisinde değişken kullanmak için `'$değişken'` veya `"${değişken}"` biçiminde kullanılır. Bu, string interpolasyonu olarak adlandırılır.

```dart
String name = 'Abdullah';
String greeting = 'Merhaba, $name!'; // Merhaba, Abdullah!
String ageGreeting = "Yaşım ${22}"; // Yaşım 22

```

-  **String Uzunluğu:** `String`'in uzunluğunu bulmak için `length` özelliği kullanılır.
```dart
String text = 'Dart';
print(text.length); // 4

```

-  **String Birleştirme:**  `String`'leri birleştirmek için `+` operatörü veya `StringBuffer` sınıfı kullanılabilir.

```dart
String firstName = 'Abdullah';
String lastName = 'Tanrıverdi';
String fullName = firstName + ' ' + lastName; // Abdullah Tanrıverdi

```
```dart
StringBuffer sb = StringBuffer();
sb.write('Abdullah');
sb.write(' ');
sb.write('Tanrıverdi');
String fullName = sb.toString(); // Abdullah Tanrıverdi

```


> [!NOTE] String Buffer
> Çok sayıda string değişimi veya birleştirilmesi gereken durumlarda kullanılan bir veri yapısıdır. Bu yapı, değişken uzunluktaki metinleri etkili bir şekilde yönetmek için tasarlanmıştır.

<br>

-  **Temel String Metotları** 

|Metot|Açıklama|
|---|---|
|`toUpperCase()`|Tüm karakterleri büyük harfe çevirir.|
|`toLowerCase()`|Tüm karakterleri küçük harfe çevirir.|
|`trim()`|Başındaki ve sonundaki boşlukları kaldırır.|
|`substring(start, end)`|Belirtilen aralıktaki alt dizeyi döner.|
|`contains(value)`|Dizede belirtilen değerin olup olmadığını kontrol eder.|
|`split(separator)`|Dizeyi belirtilen ayırıcıya göre parçalara böler.|

- **Kaçış Karakterleri:** String içinde özel karakterler kullanmak için kaçış karakteri (`\`) kullanılabilir.
```dart
String quote = 'Dart, "geliştirmenin geleceğidir."'; // Çift tırnak içinde
String singleQuote = 'Dart\'ta \'kaçış\' karakterleri var!'; // Tek tırnak içinde

```

- **Raw Stringler:**  Raw stringler (`r'...'`), kaçış karakterlerini dikkate almadan kullanmanıza olanak tanır. Bu, özellikle dosya yolları gibi durumlarda kullanışlıdır.

```dart
String path = r'C:\Kullanıcılar\Abdullah\Belgeler'; // Kaçış karakteri gerekmez.

```
- **String İle Dizi Dönüşümü:** Bir `String`'i karakter dizisine dönüştürmek için `split('')` metodu kullanılabilir.

```dart
String text = 'Dart';
List<String> characters = text.split(''); // ['D', 'a', 'r', 't']

```

***
***Abdullah TANRIVERDİ***
