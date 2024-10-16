#Yazılım #MobilGeliştirme #AndroidGeliştirmeKotlin 


`@Composable` anotasyonu, Jetpack Compose'da bir fonksiyonun **composable** olduğunu belirtmek için kullanılır. Composable fonksiyonlar, UI bileşenlerini oluşturmak ve bir araya getirmek için kullanılan temel yapı taşlarıdır. `@Composable` anotasyonu, Compose'un bu fonksiyonları nasıl işleyeceğini ve hangi kurallar altında çalışacağını belirler.

==**`@Composable` Anotasyonunun Temel Özellikleri**==

1. **UI Bileşeni Oluşturma**: `@Composable` anotasyonu ile işaretlenmiş bir fonksiyon, UI bileşeni oluşturmak için kullanılabilir. Bu fonksiyon, kullanıcı arayüzünü oluşturan diğer bileşenlerle bir araya getirilebilir.
    
2. **State Yönetimi**: Composable fonksiyonlar, değişken bir durumu (state) izleyebilir ve duruma bağlı olarak arayüzü güncelleyebilir. Jetpack Compose, değişiklikleri otomatik olarak algılar ve sadece gerekli bileşenleri yeniden oluşturur.
    
3. **Zincirleme ve Hiyerarşi**: Composable fonksiyonlar, diğer Composable fonksiyonlar içinde çağrılabilir. Bu, UI bileşenlerinin hiyerarşik olarak düzenlenmesini sağlar. Örneğin, bir `Column` veya `Row` içinde diğer Composable bileşenler yer alabilir.
    
4. **İşlevsellik**: `@Composable` anotasyonu, fonksiyonların yan etkisiz bir şekilde çalışmasını sağlar. Yani, bu fonksiyonlar, dış durumlardan bağımsız olarak çalışmalı ve yalnızca giriş argümanlarına dayanmalıdır. Bu, daha öngörülebilir ve test edilebilir bir yapı oluşturur.



```kotlin
import androidx.compose.material.Text
import androidx.compose.runtime.Composable

@Composable
fun Greeting(name: String) {
    Text(text = "Merhaba, $name!")
}

```
**Açıklama:**
- **Fonksiyon Tanımı**: `Greeting` adlı bir fonksiyon, `@Composable` ile işaretlenmiştir. Bu fonksiyon bir `String` türünde `name` argümanı alır.
- **Metin Bileşeni**: `Text` bileşeni, verilen ismi kullanarak bir selamlaşma mesajı gösterir.

```kotlin
import androidx.compose.foundation.layout.Column
import androidx.compose.material.Button
import androidx.compose.material.Text
import androidx.compose.runtime.Composable
import androidx.compose.ui.tooling.preview.Preview

@Composable
fun MyScreen() {
    Column {
        Greeting(name = "Ali")
        Greeting(name = "Ayşe")
        
        Button(onClick = { /* Butona tıklandığında yapılacak işlemler */ }) {
            Text("Butona Tıkla")
        }
    }
}

@Preview
@Composable
fun PreviewMyScreen() {
    MyScreen()
}

```

***Açıklama:**
- **`MyScreen` Fonksiyonu**: Bu fonksiyon, bir `Column` içinde iki adet `Greeting` fonksiyonu çağırır ve bir buton içerir.
- **Buton**: Tıklandığında işlem yapacak bir buton tanımlanmıştır.
- **`@Preview` Anotasyonu**: Bu, Jetpack Compose'un arayüzü önizlemenizi sağlar.


> [!tip] İPUCU
> `@Preview` anotasyonu hakkında daha fazla bilgi almak için bağlantıya tıkla [[-@Preview Anotasyonu Nedir]]


****
***Abdullah TANRIVERDİ***
