#Yazılım #MobilGeliştirme #MobilGeliştirmeFlutterDart 

Flutter’da **Flex** widget’ı, esnek düzenler oluşturmak için kullanılan güçlü bir widget’tır. Flex, çocuk widget'ları bir yönde (dikey veya yatay) hizalayarak yerleşim sağlar. Flex widget'ı genellikle **Row** ve **Column** widget'larının temeli olarak çalışır; Row ve Column, Flex widget'ının özel durumlarıdır ve yatay veya dikey hizalama sağlar. Flex widget, **direction** özelliği ile çocuk widget'ların yatay (`Axis.horizontal`) veya dikey (`Axis.vertical`) olarak hizalanmasını sağlar.

==**Flex Widget’ının Kullanımı***==
Flex widget kullanılırken, çocuk widget’ların düzenlenmesini belirlemek için **direction** özelliği zorunludur. Diğer Row ve Column özellikleri gibi, Flex de `mainAxisAlignment` ve `crossAxisAlignment` gibi hizalama özellikleri sunar.

```dart
Flex(
  direction: Axis.horizontal, // Yatay düzen
  children: [
    Expanded(
      child: Container(
        color: Colors.blue,
        height: 100,
      ),
    ),
    Expanded(
      child: Container(
        color: Colors.red,
        height: 100,
      ),
    ),
  ],
)

```
Bu örnekte, iki Expanded widget yatay olarak yan yana yerleştirilmiştir. `Axis.horizontal` olarak ayarlandığı için, çocuk widget'lar yatay düzlemde hizalanır.

==**Flex Widget’ın Özellikleri**==

- **direction**: Çocuk widget'ların hizalanma yönünü belirler (`Axis.horizontal` veya `Axis.vertical`).
- **mainAxisAlignment**: Çocuk widget'ların ana eksen boyunca (yani `direction` yönünde) nasıl hizalanacağını belirler.
    - Örneğin, `MainAxisAlignment.center`, çocuk widget'ları ortalar.
- **crossAxisAlignment**: Çocuk widget'ların çapraz eksende nasıl hizalanacağını belirler (yani direction’ın dik açısı).
    - Örneğin, `CrossAxisAlignment.stretch`, çocuk widget'ların çapraz eksende genişletilmesini sağlar.
- **mainAxisSize**: Ana eksen boyutunun ne kadar olacağını belirler (`MainAxisSize.max` veya `MainAxisSize.min`). `MainAxisSize.max`, widget’ın tüm kullanılabilir alanı kaplamasını sağlarken, `MainAxisSize.min` çocuk widget'ların kapladığı alan kadarını almasını sağlar.


==**Flex Widget ile Expanded ve Flexible Kullanımı**==
Flex widget'ı, çocuk widget'ların ekran alanını daha esnek bir şekilde paylaşmasını sağlamak için **Expanded** ve **Flexible** widget'larıyla sıkça birlikte kullanılır. `flex` değeri ile her bir widget'ın ne kadar alan kaplayacağını ayarlayabilirsiniz.
```dart
Flex(
  direction: Axis.vertical, // Dikey düzen
  children: [
    Expanded(
      flex: 2,
      child: Container(
        color: Colors.green,
      ),
    ),
    Expanded(
      flex: 1,
      child: Container(
        color: Colors.yellow,
      ),
    ),
  ],
)

```
Bu örnekte, yeşil widget, sarı widget'tan iki kat daha fazla alan kaplayacaktır

==**Flex Widget Kullanım Senaryoları**==

- **Responsive Tasarım**: Flex, farklı ekran boyutlarına göre yerleşimin dinamik olarak ayarlanmasını sağlar.
- **Modüler UI**: Bir ekranı bölmek veya bir düzen içinde farklı bileşenlere esnek alan sağlamak için kullanılır.
- **Yer Paylaşımı ve Ekran Yönetimi**: Bir alanın, içerik yoğunluğuna veya kullanıcının cihazına göre uyarlanması gereken durumlarda faydalıdır.

==**Flex Kullanırken Dikkat Edilmesi Gerekenler**==

- **Direction Özelliğinin Zorunlu Olması**: Flex, `direction` olmadan çalışmaz, yön belirtmek zorunludur.
- **Expanded Veya Flexible Gereksinimi**: Flex içerisinde, genişliği esnek hale getirmek istediğiniz çocuk widget'lar için Expanded veya Flexible kullanmak önemlidir. Aksi takdirde çocuk widget'ların konumlandırılması veya genişletilmesi doğru çalışmayabilir.
- **Düzenin Karmaşıklığı**: Büyük ve karmaşık düzenlerde fazla sayıda Flex widget kullanmak, kodun okunabilirliğini düşürebilir. Bu nedenle, Flex yapısı içinde sadelik sağlanmalıdır.
****

***Abdullah TANRIVERDİ***
