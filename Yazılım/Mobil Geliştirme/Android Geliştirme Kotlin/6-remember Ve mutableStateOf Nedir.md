#Yazılım #MobilGeliştirme #AndroidGeliştirmeKotlin 

- ==**`remember {}`**==Jetpack Compose'da bir değer veya objeyi bellekte tutmak için kullanılır. UI yeniden oluşturulurken (örneğin, kullanıcı arayüzü güncellendiğinde) bile aynı değerin saklanmasını sağlar. Bu, yeniden oluşturma sırasında durumu kaybetmemek için önemlidir.
    
- ==**`mutableStateOf()`**==: Bir durumu (state) tanımlamak için kullanılır. Değeri değiştirildiğinde, Compose bu durumu izler ve değişiklik olduğunda ilgili UI bileşenini yeniden çizer.

Bu iki yapı birlikte kullanıldığında, UI bileşenlerinin duruma dayalı olarak dinamik bir şekilde güncellenmesini sağlar.

==**`remember { mutableStateOf() }` Nasıl Çalışır?**==
`mutableStateOf()`, bir değeri tutar ve bu değer değiştirildiğinde, Jetpack Compose bu değişikliği algılar ve bağlı olan UI bileşenlerini yeniden oluşturur. `remember` ise bu durumu bellekte saklar ve bileşen yeniden oluşturulsa bile (örneğin, bir state değişikliği, ekran döndürme vb. durumlarda) durumu korur.
```kotlin
import androidx.compose.material.Button
import androidx.compose.material.Text
import androidx.compose.runtime.*

@Composable
fun Counter() {
    // remember ile state tanımlanır
    var count by remember { mutableStateOf(0) }

    // UI bileşenleri duruma göre yeniden çizilir
    Button(onClick = { count++ }) {
        Text(text = "Tıklama sayısı: $count")
    }
}

```
**Açıklama:**
- **`var count by remember { mutableStateOf(0) }`**: `count` adında bir durum (state) oluşturulur ve başlangıç değeri 0 olarak belirlenir. `remember`, bu değerin bileşen yeniden çizildiğinde korunmasını sağlar.
- **`Button(onClick = { count++ })`**: Butona her tıklandığında, `count` değeri artırılır. Değer değiştiği anda Jetpack Compose, bu durumu algılayıp UI bileşenini (butonun içindeki metin) günceller.



==**State ile UI Güncellemeleri**==
Jetpack Compose, durumu değiştirdiğinizde (örneğin, bir `Button`'a tıklayıp `mutableStateOf()` ile sakladığınız değeri artırdığınızda) ilgili UI bileşenini yeniden çizer.
```kotlin
import androidx.compose.material.Button
import androidx.compose.material.Text
import androidx.compose.runtime.*

@Composable
fun Greeting() {
    var name by remember { mutableStateOf("Dünya") }

    Button(onClick = { name = "Jetpack Compose" }) {
        Text(text = "Merhaba, $name!")
    }
}

```
**Açıklama:**
- **`var name by remember { mutableStateOf("Dünya") }`**: Başlangıçta "Dünya" olan bir metin durumu oluşturulur.
- **Butona Tıklanıldığında**: `name` değeri "Jetpack Compose" olarak güncellenir ve Compose bu değişikliği algılayarak metni yeniden çizer.


==**`remember` ve `mutableStateOf`'un Performans Etkisi**==
Jetpack Compose, UI'yi sadece gerekli olduğunda yeniden oluşturur. Bu, performansı optimize eder çünkü yalnızca durumu değişen bileşenler yeniden çizilir. `remember`, bu yeniden çizim sırasında durumu saklayarak performansın korunmasına yardımcı olur. Eğer `remember` kullanılmazsa, her bileşen yeniden oluşturulduğunda durum sıfırlanır ve beklenen davranış elde edilemez.

****
***Abdullah TANRIVERDİ***




