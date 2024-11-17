#Yazılım #ProgramlamaDilleri #Dart 

![[Fonksiyon.png|500]]
Fonksiyonlar, belirli bir işlemi gerçekleştirmek için kullanılan kod bloklarıdır. Fonksiyonlar, parametre alabilir, değer döndürebilir ve başka fonksiyonlara argüman olarak geçirilebilir.

**Fonksiyon Tanımlama** 
- Fonksiyonlar, belirli bir dönüş türü, isim ve parametler ile tanımlanır. Dönüş türü olarak `void`, dönüş değeri olmayan bir fonksiyon için kullanılır.

```dart
void greet() {
  print('Merhaba!');
}

int add(int a, int b) {
  return a + b;
}

```

- Tanımlanan bir fonksiyon, adı ile çağrılır.
```dart
void main() {
  greet(); // 'Merhaba!' yazdırır.
  int sum = add(5, 3);
  print(sum); // 8 yazdırır.
}

```

- Fonksiyonlar, zorunlu ve isteğe bağlı parametreler alabilir. İsteğe bağlı parametreler köşeli parantez içinde tanımlanır.

```dart
void greetUser(String name, [String title]) {
  if (title != null) {
    print('Merhaba, $title $name!');
  } else {
    print('Merhaba, $name!');
  }
}

void main() {
  greetUser('Abdullah', 'Jr.'); // Merhaba, Jr. Abdullah!
  greetUser('Ali'); // Merhaba, Ali!
}

```

- Fonksiyonlar, dönüş değeri döndürmek için `return` ifadesi kullanır.
```dart
String greet(String name) {
  return 'Merhaba, $name!';
}

void main() {
  String message = greet('Ayşe');
  print(message); // Merhaba, Ayşe!
}

```

- Fonksiyonlar, başka fonksiyonları çağırabilir.

```dart
int multiply(int a, int b) {
  return a * b;
}

int calculate(int x, int y) {
  return add(x, y) + multiply(x, y);
}

void main() {
  print(calculate(2, 3)); // 11 yazdırır (2 + 3) + (2 * 3)
}

```
- Dart, anonim fonksiyonlar (lambda) tanımlamaya olanak tanır. Bu, belirli bir işlevi yerine getiren fat arrow fonksiyonlardır.

```dart
void main() {
  var list = [1, 2, 3, 4, 5];
  var squares = list.map((number) => number * number);
  print(squares.toList()); // [1, 4, 9, 16, 25]
}

```
- Fonksiyonlar, başka fonksiyonlara argüman olarak geçirilebilir, bu da callback işlevselliği sağlar.

```dart
void performAction(Function callback) {
  // İşlem yapılıyor...
  callback(); // Callback'i çağır
}

void main() {
  performAction(() {
    print('Aksiyon tamamlandı!'); // Callback olarak anonim fonksiyon
  });
}

```

- Dart’ta fonksiyonlar, diğer veri tipleri gibi birinci sınıf vatandaşlardır. Bu, fonksiyonların argüman olarak geçirilebilmesi, değer olarak atanabilmesi ve başka fonksiyonlardan dönebilmesi anlamına gelir.

```dart
Function returnFunction() {
  return (int a, int b) => a + b; // Toplama fonksiyonu döner
}

void main() {
  var addFunction = returnFunction();
  print(addFunction(5, 3)); // 8 yazdırır
}

```

> [!info] Özetle
>Fonksiyonlar, kodun yeniden kullanılabilirliğini artırır ve belirli görevleri yerine getiren modüler yapılardır.

***
***Abdullah TANRIVERDİ***

