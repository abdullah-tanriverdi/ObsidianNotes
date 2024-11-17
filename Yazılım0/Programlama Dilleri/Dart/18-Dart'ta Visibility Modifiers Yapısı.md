
#Yazılım #ProgramlamaDilleri #Dart 

Dart dilinde **Visibility Modifiers** (Görünürlük Değiştiricileri), bir sınıfın, özelliğin veya metodun başka bir sınıf veya kütüphane tarafından erişilebilirliğini kontrol etmek için kullanılır. 

-  **Public:** Varsayılan görünürlük dizeyidir.Sınıfın , metodun önüne ` public` anahtar kelimesi eklemeden doğrudan erişilebilir. Diğer tüm sınıflar tarafından erişilebilinir.

```dart
class MyClass {
  int publicField = 10; // Genel alan
  
  void publicMethod() { // Genel metot
    print('Public Method');
  }
}

```


- **Private:**  Sınıfın içinde tanımlanan bir özelliğin veya metodun yalnızca tanımlandığı sınıf içinde erişilebilir olmasını sağlar. Dart’ta özel görünürlük, isimlerin önüne `_` (alt çizgi) eklenerek belirtilir.

```dart
class MyClass {
  int _privateField = 20; // Özel alan
  
  void _privateMethod() { // Özel metot
    print('Private Method');
  }
}

```


- **Protected:** Dart'ta doğrudan bir "korunan" görünürlük modu yoktur, ancak özel bir alan veya metodu bir alt sınıfta erişilebilir hale getirmek için `protected` görünürlük işlevselliği sağlanabilir. Bunu yapmak için, özel alan veya metodu alt sınıfta kullanmanız gerekir.

```dart
class Base {
  int _protectedField = 30; // Özel alan
}

class Derived extends Base {
  void accessProtected() {
    print(_protectedField); // Erişim burada mümkündür
  }
}

```

>[!info] NOT
>Özel değişkenler veya metotlar dışarıdan erişilemez, bu nedenle veri kapsülleme ve nesne yönelimli programlama ilkelerine göre daha güvenli bir tasarım sağlar.

***
***Abdullah TANRIVERDİ***



