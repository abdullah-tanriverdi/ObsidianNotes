#Yazılım #MobilGeliştirme #AndroidGeliştirmeKotlin 


Jetpack Compose'ta **`Surface`**, bir UI bileşeninin arka planını ve şekillendirilmesini tanımlamak için kullanılan bir container’dır. Diğer Composable bileşenleri içerir ve onlara belirli görsel özellikler kazandırır. Surface, özellikle **Material Design** ile uyumlu uygulamalar geliştirmek için kullanılır ve **arka plan rengi, şekil, gölge (elevation)** gibi stil özelliklerini ayarlayarak UI bileşenlerine görsel zenginlik katar.

==**Surface'ın Temel Kullanımı**==
`Surface`, genellikle bir bileşenin düzenini veya stilini yönetmek için bir kapsayıcı olarak kullanılır. Bu sayede, içindeki Composable bileşenler belirli bir tasarım ve görsel stil çerçevesinde yer alır. Örneğin, kart, buton, diyalog gibi bileşenler Surface kullanılarak özelleştirilebilir.

```kotlin
import androidx.compose.foundation.layout.fillMaxSize
import androidx.compose.material.Surface
import androidx.compose.material.Text
import androidx.compose.runtime.Composable
import androidx.compose.ui.Modifier
import androidx.compose.ui.graphics.Color

@Composable
fun MySurfaceExample() {
    Surface(
        modifier = Modifier.fillMaxSize(),
        color = Color.LightGray
    ) {
        Text(text = "Bu bir Surface içinde görüntüleniyor", color = Color.Black)
    }
}

```

**Bu örnekte ne oluyor?**
- **`Surface`**: `Surface`, `fillMaxSize` modifiyer'iyle tüm ekranı kapsayacak şekilde ayarlandı ve arka plan rengi açık gri (LightGray) olarak belirlendi.
- **`Text`**: Surface'ın içinde bir metin bileşeni yerleştirildi, bu metin bileşeni Surface'ın sağladığı arka plan rengi ve boyut gibi stil özellikleriyle birlikte görüntülendi.


> [!tip] İPUCU
> Modifier hakkında bilgi almak için bağlantıya tıkla [[4-Modifier Nedir]]




==**Surface'ın Özellikleri**==

-  **`color`:** Arka plan rengini ayarlamak için kullanılır. Material Design teması içindeki renklerden biri kullanılabilir ya da sabit bir renk atanabilir.
```kotlin
Surface(color = Color.LightGray) { /* İçerik */ }
```

- **`shape`:** Surface'ın şeklini belirler. Köşeleri yuvarlatılmış kareler veya tamamen yuvarlak bir görünüm gibi şekil değişiklikleri yapılabilir. Örneğin `RoundedCornerShape` kullanarak köşeleri yuvarlayabilirsiniz.
```kotlin
Surface(shape = RoundedCornerShape(8.dp)) { /* İçerik */ }
```

- **`elevation`:** Surface'a gölge ve derinlik etkisi eklemek için kullanılır. Material Design prensiplerinde, yüksekliği simgeleyen "elevation", UI bileşenlerinin hiyerarşisinde belirli bir derinlik katmanı oluşturarak onları öne çıkarır.
```kotlin
Surface(elevation = 4.dp) { /* İçerik */ }
```

- **`border`:** Surface’ın kenarlarına sınır (border) ekleyebilirsiniz. Bu, çizgi kalınlığı ve rengiyle bir çerçeve oluşturur.
```kotlin
Surface(border = BorderStroke(1.dp, Color.Black)) { /* İçerik */ }
```

- **`contentColor`:** İçindeki bileşenlerin varsayılan rengini belirler. Eğer arka plan rengi koyuysa, içerikte kullanılacak renk açık olabilir ve tersine.
 ```kotlin
 Surface(contentColor = Color.White) { /* İçerik */ }

```

==**Surface Kullanım Senaryoları**==

**Kart Bileşenleri (Card):** Bir kart (Card) UI elemanını oluştururken `Surface` kullanarak arka plan, köşe yuvarlama ve gölge eklenebilir.

```kotlin
import androidx.compose.foundation.layout.padding
import androidx.compose.foundation.shape.RoundedCornerShape
import androidx.compose.material.Surface
import androidx.compose.material.Text
import androidx.compose.runtime.Composable
import androidx.compose.ui.Modifier
import androidx.compose.ui.graphics.Color
import androidx.compose.ui.unit.dp

@Composable
fun CardExample() {
    Surface(
        modifier = Modifier.padding(16.dp),
        color = Color.White,
        shape = RoundedCornerShape(8.dp),
        elevation = 8.dp
    ) {
        Text(
            text = "Bu bir kart bileşenidir",
            modifier = Modifier.padding(16.dp)
        )
    }
}

```

**Diyaloglar (Dialogs):** Bir uyarı veya diyalog kutusu oluşturmak için `Surface` kullanılabilir. Bu durumda Surface, diyalog kutusunun genel yapısını ve stilini kontrol eder.

```kotlin
@Composable
fun DialogSurfaceExample() {
    Surface(
        color = Color.White,
        shape = RoundedCornerShape(12.dp),
        elevation = 16.dp
    ) {
        Text(
            text = "Bu bir diyalog",
            modifier = Modifier.padding(24.dp)
        )
    }
}

```

**Butonlar (Buttons):** Material Design butonlarının temelini oluşturan `Surface` bileşeni, özelleştirilmiş butonlar oluşturmak için kullanılabilir. Bu sayede, butonlar gölge, arka plan ve şekil gibi görsel efektlerle zenginleştirilebilir.

```kotlin
@Composable
fun ButtonSurfaceExample() {
    Surface(
        color = Color.Blue,
        shape = RoundedCornerShape(50), // Tamamen yuvarlak köşeler
        elevation = 4.dp
    ) {
        Text(
            text = "Buton",
            modifier = Modifier.padding(16.dp),
            color = Color.White
        )
    }
}

```

==**Surface'ın Avantajları**==

1. **Material Design Uyumu:** Surface, Material Design prensiplerine göre tasarlanmıştır ve arka plan renkleri, gölge ve şekil gibi özelliklerle UI tasarımında tutarlılık sağlar.
    
2. **Kolay Özelleştirme:** Surface, şekil, arka plan rengi, gölge (elevation) ve diğer stil özellikleri ile kolayca özelleştirilebilir.
    
3. **Bileşenleri Gruplama:** Surface, bir UI bileşenini gruplamak ve ona belirli stil kuralları eklemek için ideal bir kapsayıcıdır. Örneğin, bir kartın içindeki tüm bileşenler Surface ile gruplanabilir ve genel bir stil uygulanabilir.


> [!tip] İPUCU
> Material Design hakkında daha fazla bilgi almak için bağlantıya tıkla [[-Material Design Nedir]]

***
***Abdullah TANRIVERDİ***
