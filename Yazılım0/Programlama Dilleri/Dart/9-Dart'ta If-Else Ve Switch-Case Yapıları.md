#Yazılım #ProgramlamaDilleri #Dart 

==**If-Else Yapısı:**==  Belirli bir koşulun doğru olup olmadığını kontrol eder ve bu koşula göre farklı kod bloklarını çalıştırır.

```dart
void main() {
  int number = 10;

  if (number > 0) {
    print("Pozitif bir sayı");
  } else if (number < 0) {
    print("Negatif bir sayı");
  } else {
    print("Sayı sıfır");
  }
}

```
<br>

==**Switch-Case Yapısı:**== Bir değişkenin değerine göre farklı durumlar arasında seçim yapmanızı sağlar. Bu yapı, özellikle birden fazla koşulu kontrol etmek için kullanışlıdır.
```dart
void main() {
  String day = "Pazar";

  switch (day) {
    case "Pazartesi":
      print("Haftanın birinci günü");
      break;
    case "Salı":
      print("Haftanın ikinci günü");
      break;
    case "Çarşamba":
      print("Haftanın üçüncü günü");
      break;
    case "Perşembe":
      print("Haftanın dördüncü günü");
      break;
    case "Cuma":
      print("Haftanın beşinci günü");
      break;
    case "Cumartesi":
      print("Haftanın altıncı günü");
      break;
    case "Pazar":
      print("Haftanın yedinci günü");
      break;
    default:
      print("Geçersiz gün");
  }
}

```
****
***Abdullah TANRIVERDİ***