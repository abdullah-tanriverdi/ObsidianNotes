#Yazılım #MobilGeliştirme #AndroidGeliştirmeKotlin 


![[JetpackCompose.png|500]]


**Jetpack Compose:** Android için tamamen yeni bir UI araç setidir. Geleneksel Android UI geliştirme yöntemlerinden (XML tabanlı) farklı olarak, Compose ile UI bileşenleri tamamen Kotlin kodu ile tanımlanır. Bu sayede daha fazla esneklik ve daha az kod yazma imkanı sağlar.

==**Temel Özellikler**==
- **Deklaratif Programlama:** Compose, UI bileşenlerini tanımlarken "ne" yapılacağını belirtir, "nasıl" yapılacağını değil. Bu, kodun okunabilirliğini artırır ve daha az hata olasılığı sağlar.
    
- **State Management:** UI durumu yönetimi kolaydır. Compose, durum değişikliklerini otomatik olarak algılar ve UI'yi günceller.
    
- **Modülerlik:** Compose ile oluşturulan bileşenler, diğer projelerde yeniden kullanılabilir. Bu, geliştirme sürecini hızlandırır.
    
- **Kotlin ile Tam Entegrasyon:** Compose, Kotlin dilinin tüm özelliklerini kullanır; yüksek dereceli fonksiyonlar, lambda ifadeleri ve genişletme fonksiyonları gibi.

==**Temel Kullanım**==
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
fun DefaultPreview() {
    Greeting("Dünya")
}

```

Bu kodda, `Greeting` adında bir fonksiyon tanımlanır. Bu fonksiyon, bir metin bileşeni oluşturur ve `Preview` ile bileşenin nasıl görüneceği önizlenir.

==**UI Bileşenleri**==
Jetpack Compose, çeşitli yerleşik bileşenler sunar. İşte bazıları:

***Text:*** Metin bileşeni oluşturur.

```kotlin
Text(text = "Merhaba, Compose!")

```

**Button:** Tıklanabilir butonlar oluşturur.
```kotlin
Button(onClick = { /* Eylem */ }) {
    Text("Butona Tıkla")
}

```

**Column ve Row:** Bileşenleri dikey veya yatay olarak düzenler.
```kotlin
Column {
    Text("Birinci Satır")
    Text("İkinci Satır")
}

Row {
    Text("Solda")
    Text("Sağda")
}

```


**Image:** Görüntüleri göstermek için kullanılır.
```kotlin
Image(painter = painterResource(id = R.drawable.image), contentDescription = "Görsel")

```

**LazyColumn:** Uzun listeleri verimli bir şekilde gösterir. Liste elemanları gerektiğinde oluşturulur.

```kotlin
LazyColumn {
    items(list) { item ->
        Text(text = item)
    }
}

```

==**Durum Yönetimi**== 
Compose, durumu yönetmek için çeşitli yöntemler sunar. İşte temel bir sayaç örneği:
```kotlin
import androidx.compose.material.Button
import androidx.compose.material.Text
import androidx.compose.runtime.*

@Composable
fun Counter() {
    var count by remember { mutableStateOf(0) }

    Button(onClick = { count++ }) {
        Text(text = "Sayaç: $count")
    }
}

```

- `remember`: Durumu kaydetmek için kullanılır. Değiştiğinde UI otomatik olarak güncellenir.
- `mutableStateOf`: Değişkenin durumunu yönetmek için kullanılır.


==**Temalar ve Stiller**==
Compose, kullanıcı arayüzü bileşenlerinin görünümünü özelleştirmek için temalar ve stiller tanımlamanıza olanak tanır. **Material Design** bileşenleri, uygulamanızın tutarlı bir görünüm kazanmasını sağlar.
Örneğin, bir tema oluşturmak için:
```kotlin
import androidx.compose.material.MaterialTheme
import androidx.compose.material.Typography

private val MyTypography = Typography(
    // Yazı tipleri burada özelleştirilebilir
)

@Composable
fun MyTheme(content: @Composable () -> Unit) {
    MaterialTheme(
        typography = MyTypography,
        content = content
    )
}

```

==**Navigasyon**==
Compose, `navigation-compose` kütüphanesini kullanarak sayfalar arası geçişleri yönetir.
```kotlin
import androidx.compose.material.Button
import androidx.compose.material.Text
import androidx.compose.runtime.Composable
import androidx.navigation.compose.NavHost
import androidx.navigation.compose.composable
import androidx.navigation.compose.rememberNavController

@Composable
fun MyNavHost() {
    val navController = rememberNavController()

    NavHost(navController, startDestination = "home") {
        composable("home") { HomeScreen(navController) }
        composable("details") { DetailScreen() }
    }
}

@Composable
fun HomeScreen(navController: NavController) {
    Button(onClick = { navController.navigate("details") }) {
        Text("Detay Sayfasına Git")
    }
}

```
Bu örnekte, `NavHost` kullanarak iki sayfa arasında geçiş yapıyoruz. `HomeScreen`, butona tıklanarak `DetailScreen`'e geçiş yapıyor.

==**Test**==
Compose ile geliştirdiğiniz bileşenleri test etmek oldukça kolaydır

```kotlin
import androidx.compose.ui.test.junit4.createComposeRule
import androidx.compose.ui.test.onNodeWithText
import androidx.compose.ui.test.performClick
import org.junit.Rule
import org.junit.Test

class CounterTest {
    @get:Rule
    val composeTestRule = createComposeRule()

    @Test
    fun testCounter() {
        composeTestRule.setContent {
            Counter()
        }

        composeTestRule.onNodeWithText("Sayaç: 0").performClick()
        composeTestRule.onNodeWithText("Sayaç: 1").assertExists()
    }
}

```
Bu test, sayaç bileşeninin başlangıç değerini kontrol eder ve bir tıklama sonrası değerin arttığını doğrular.

==**Gelişmiş Özellikler**==
- **Lazy ve Grid:** `LazyColumn`, `LazyRow` ve `LazyVerticalGrid`, verimli şekilde büyük veri kümesi görüntülemek için kullanılır.
    
- **Etkileşimli Animasyonlar:** Compose, animasyonları ve geçişleri kolayca oluşturmanızı sağlar. Örneğin, `animate*AsState` fonksiyonları ile animasyonlar oluşturabilirsiniz.
    
- **Karmaşık Bileşenler:** Compose ile karmaşık UI bileşenleri oluşturabilirsiniz. Özelleştirilmiş bileşenler tasarlamak için mevcut bileşenleri birleştirerek daha zengin arayüzler yaratabilirsiniz.
    
- **Mimari Tasarım:** Compose, MVVM (Model-View-ViewModel) gibi mimari desenlerle iyi çalışır. `LiveData` veya `StateFlow` ile UI durumunu yönetebilir ve güncelleyebilirsiniz.
***
***Abdullah TANRIVERDİ***
