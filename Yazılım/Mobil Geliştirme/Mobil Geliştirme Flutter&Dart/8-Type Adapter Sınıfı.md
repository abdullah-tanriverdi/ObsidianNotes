#Yazılım #MobilGeliştirme #MobilGeliştirmeFlutterDart

Type Adapter, Hive veritabanında özel sınıfları (objeleri) saklamak için kullanılan bir yapıdır. Hive, veri saklamak için temel veri türlerini destekler, ancak kendi oluşturduğunuz karmaşık veri yapılarınızı da saklamak isterseniz, Type Adapter'ları kullanmanız gerekir.

==**Kullanım Senaryoları**==
- **Özel Sınıfların Saklanması**: Kullanıcı bilgileri, ürün detayları gibi özel veri yapılarının saklanması.
- **Karmaşık Veri Yapıları**: Listeler, haritalar veya başka nesne türleri içeren karmaşık veri yapıları.

==**TypeAdapter Oluşturma**==
**Sınıf Tanımlama** Öncelikle, saklamak istediğin özel sınıfı tanımla. Örneğin, bir `User` sınıfı:
```dart
class User {
  final String username;
  final int age;

  User(this.username, this.age);
}

```
**TypeAdapter Sınıfını Oluşturma** `TypeAdapter` sınıfını oluştur ve gerekli metotları (read ve write) implement et:
```dart
import 'package:hive/hive.dart';

class UserAdapter extends TypeAdapter<User> {
  @override
  final int typeId = 1; // Her adapter için benzersiz bir ID olmalı

  @override
  User read(BinaryReader reader) {
    final username = reader.readString(); // String okuma
    final age = reader.readInt(); // Integer okuma
    return User(username, age); // Okunan verilerle User nesnesi oluştur
  }

  @override
  void write(BinaryWriter writer, User obj) {
    writer.writeString(obj.username); // Kullanıcı adını yaz
    writer.writeInt(obj.age); // Yaşı yaz
  }
}

```

**TypeAdapter'ı Kaydetme** Uygulaman başlarken oluşturduğun Type Adapter'ı kaydetmen gerekiyor:
```dart
void main() async {
  await Hive.initFlutter();
  Hive.registerAdapter(UserAdapter()); // Adapter'ı kaydet
  runApp(MyApp());
}

```

==**Veri Yazma ve Okuma**==

**Veri Yazma**:
```dart
var box = await Hive.openBox<User>('userBox');
await box.put('user1', User('abdullah', 30)); // User nesnesini kaydet

```

**Veri Okuma**:
```dart
User user = box.get('user1'); // User nesnesini oku
print('Username: ${user.username}, Age: ${user.age}'); // Çıktı: Username: abdullah, Age: 30

```
==**Sınırlamalar**==
- Her Type Adapter için benzersiz bir `typeId` belirlemelisin. Aynı `typeId`'ı kullanmak, veri çakışmalarına neden olabilir.
- Okuma ve yazma işlemlerinde uyumlu olman önemli; yani `read` ve `write` metodlarının doğru şekilde veri okuması ve yazması gerekiyor.


> [!NOTE] Özetle
> Type Adapter'lar, Hive ile özel sınıflarımı saklamama olanak tanır. Karmaşık veri yapılarımın veritabanında yönetimi için bu yapıyı kullanarak, verilerimi kolayca saklayabilir ve gerektiğinde erişebilirim. Bu, uygulamalarımda veri yönetimini oldukça esnek hale getiriyor.

****
***Abdullah TANRIVERDİ***