
#Yazılım #MobilGeliştirme #AndroidGeliştirmeKotlin 


`@Preview` anotasyonu, Jetpack Compose'da kullanıcı arayüzü bileşenlerinin önizlemesini yapmanızı sağlayan bir araçtır. Android Studio içerisinde Compose bileşenlerini çalıştırmadan önce veya daha hızlı bir şekilde, geliştirme ortamında arayüzünüzü görmenize olanak tanır. Bu anotasyon sayesinde, UI bileşenlerinizin nasıl görüneceğini doğrudan kodunuzun yanında görebilirsiniz.

```kotlin
import androidx.compose.material.Text
import androidx.compose.runtime.Composable
import androidx.compose.ui.tooling.preview.Preview

@Composable
fun Greeting(name: String) {
    Text(text = "Merhaba, $name!")
}

@Preview
@Composable
fun PreviewGreeting() {
    Greeting(name = "Dünya")
}

```
**Açıklama:**
- **`@Preview`**: Bu anotasyon, `Greeting` composable fonksiyonunun nasıl göründüğünü Android Studio'nun "Preview" penceresinde göstermeye olanak tanır. "Dünya" metni ile "Merhaba, Dünya!" mesajı görüntülenir.
- **`@Composable`**: Fonksiyonun bir composable olduğunu belirtir

==**`@Preview` İle Farklı Senaryoları Test Etme**==

```kotlin
@Preview(name = "Telefon", widthDp = 360, heightDp = 640)
@Preview(name = "Tablet", widthDp = 800, heightDp = 1280)
@Composable
fun PreviewDeviceLayouts() {
    Greeting(name = "Dünya")
}

```

Bu örnekte, bir telefon ve bir tablet ekranı için iki ayrı önizleme yapılır. Android Studio'da her iki önizleme de aynı anda görüntülenebilir.

```kotlin
@Preview(name = "Açık Mod")
@Preview(name = "Koyu Mod", uiMode = Configuration.UI_MODE_NIGHT_YES)
@Composable
fun PreviewThemeModes() {
    Greeting(name = "Dünya")
}

```

Koyu ve açık tema modları arasında geçiş yaparak bileşenlerinizin her iki modda nasıl göründüğünü test edebilinir.


> [!info] Sonuç
>`@Preview` anotasyonu, Jetpack Compose'da UI geliştirme sürecini hızlandırmak ve optimize etmek için son derece kullanışlı bir araçtır. Farklı cihazlar ve ekran boyutları için bileşenlerin nasıl görüneceğini test etmenizi sağlar ve gerçek zamanlı geri bildirim almanıza olanak tanır. Özelleştirilebilir parametreler sayesinde, bileşenlerinize daha fazla kontrol kazandırır ve kullanıcı arayüzünü geliştirmeyi daha verimli hale getirir.

***
***Abdullah TANRIVERDİ***






