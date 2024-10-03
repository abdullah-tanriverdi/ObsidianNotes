#Yazılım #ProgramlamaDilleri #Dart 

Dart dilindeki `assert` yapısı, bir koşulun doğru olup olmadığını kontrol etmek ve geliştirme sürecinde hataları yakalamak için kullanılan bir araçtır.

**`assert` Nedir:**Geliştirme aşamasında belirli bir koşulun doğru olup olmadığını kontrol eden bir yapıdır. Eğer koşul **false** dönerse, program çalışmayı durdurur ve bir hata mesajı verir. Bu, programda beklenmedik durumları tespit etmenin ve bu durumlara erken müdahale etmenin bir yoludur. `assert` yalnızca **debug modunda** (geliştirme sırasında) çalışır. **Release modunda** `assert` satırları dikkate alınmaz. 

```dart
void main() {
  int age = 15;
  assert(age >= 18, 'Yaş 18\'den büyük olmalı.'); // Eğer koşul false olursa hata fırlatılır
  print('Program devam ediyor...');
}

```

```dart
assert(5 < 3, '5 sayısı 3\'ten küçük olamaz.'); // Bu mesaj koşul yanlış olunca gösterilecek.

```

> [!warning] UYARI
> `assert` sadece geliştirme sürecinde hata ayıklama amacıyla kullanılmalıdır. Üretim kodunda hata yönetimi için `try-catch` yapısı tercih edilmelidir.

**Kullanımın Avantajları:** 
- Erken hata tespiti
- Debug moduna özel
- Kolay kullanım

*** 
***Abdullah TANRIVERDİ***






