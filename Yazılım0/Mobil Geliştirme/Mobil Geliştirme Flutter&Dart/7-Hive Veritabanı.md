#Yazılım #MobilGeliştirme #MobilGeliştirmeFlutterDart 

![[Hive_Database.jpg]]

Hive, Flutter uygulamalarında kullanılan hafif, hızlı ve NoSQL bir veritabanıdır. Mobil uygulama geliştirme sürecimde veri yönetimi için sıklıkla tercih ettiğim bir kütüphane.

==**Hive Nedir?**==
Hive, özellikle mobil uygulamalarda veri saklamak için kullanılan bir NoSQL veritabanıdır. Uygulamaların yerel verilerini depolamak için mükemmel bir çözümdür. Kullanıcı ayarları, uygulama verileri ve diğer geçici veriler için idealdir.

==**Kurulum**==
Hive’ı projemize eklemek için `pubspec.yaml` dosyamıza aşağıdaki bağımlılıkları eklememiz gerekiyor:
```yaml
dependencies:
  hive: ^2.0.0
  hive_flutter: ^1.0.0

```
Daha sonra terminalde `flutter pub get` komutunu çalıştırarak bu bağımlılıkları indiriyoruz.

Hive, verileri anahtar-değer çiftleri şeklinde saklar. Bu, verileri organize etmenin esnek bir yolunu sağlar. Örneğin, bir kullanıcı bilgilerini saklamak istiyorsak, aşağıdaki gibi bir yapı oluşturabiliriz:

```dart
await Hive.initFlutter();
 
var box = await Hive.openBox('userBox');
await box.put('username', 'abdullah');
await box.put('age', 22);

```

==**Veri Okuma**==
```dart
String username = box.get('username');
int age = box.get('age');
print('Username: $username, Age: $age'); // Çıktı: Username: abdullah, Age: 22

```

==**Özel Sınıfların Depolanması**==
Hive, sadece temel veri türlerini değil, aynı zamanda özel sınıflarımı da depolama yeteneğine sahiptir. Bunun için, sınıfımıza `TypeAdapter` eklememiz gerekir. Örneğin, bir `User` sınıfımız varsa:

> [!tip] İPUCU 
>  `TypeAdapter` hakkında bilgi almak için bağlantıya tıkla [[8-Type Adapter Sınıfı]]


```dart
class User {
  final String username;
  final int age;

  User(this.username, this.age);
}

```
Bu sınıf için bir `TypeAdapter` oluşturarak verimizi saklayabiliriz:
```dart
class UserAdapter extends TypeAdapter<User> {
  @override
  final int typeId = 1;

  @override
  User read(BinaryReader reader) {
    final username = reader.readString();
    final age = reader.readInt();
    return User(username, age);
  }

  @override
  void write(BinaryWriter writer, User obj) {
    writer.writeString(obj.username);
    writer.writeInt(obj.age);
  }
}

```
Sınıfı kaydettikten sonra şu şekilde kullanabiliriz:
```dart
Hive.registerAdapter(UserAdapter());
var box = await Hive.openBox<User>('userBox');
await box.put('user1', User('abdullah', 30));

```

==**Veri Şifreleme**==
Hive, verileri güvenli bir şekilde saklamak için şifreleme desteği sunar. Bu, hassas verilerimizi korumak için önemli bir özelliktir. Şifreleme için aşağıdaki şekilde bir kutu açabiliriz:
```dart
var box = await Hive.openBox('secureBox', 
  encryptionCipher: HiveAesCipher(yourEncryptionKey));

```
==**Veri Silme**==
Verileri silmek de oldukça kolaydır. Belirli bir anahtara sahip veriyi silmek için:
```dart
await box.delete('username');

```
==**Veri Dinleme**==
Hive, verileri dinlemek için `ValueListenableBuilder` bileşenini destekler. Bu, veriler değiştiğinde UI'nin otomatik olarak güncellenmesini sağlar.
```dart
ValueListenableBuilder(
  valueListenable: box.listenable(),
  builder: (context, Box box, _) {
    return Text('Username: ${box.get('username')}');
  },
)

```

==**Kullanım Senaryoları**==
- Kullanıcı ayarlarını saklamak için.
- Offline modda uygulama verilerini yönetmek için.
- Uygulama içi geçici verileri depolamak için.


> [!NOTE] İPUCU
> Hive DB hakkında dökümantasyona ulaşmak için bağlantıya tıkla [Hive DB](https://github.com/isar/hive)



****
***Abdullah TANRIVERDİ***