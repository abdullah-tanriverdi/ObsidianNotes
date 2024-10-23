#Yazılım #MobilGeliştirme #AndroidGeliştirmeKotlin 

**Scaffold**, Jetpack Compose içerisinde temel bir uygulama yapısı ve düzeni sağlamak için kullanılan bir bileşendir. Uygulamanın ana yapısını oluşturmak ve genel tasarım kurallarına uygun bir görünüm sunmak için kullanılır. Scaffold, birçok UI bileşenini (örn. AppBar, BottomNavigation, FloatingActionButton vb.) düzenli bir şekilde yerleştirmek için gereken yapıyı sağlar.

```dart
import androidx.compose.foundation.layout.fillMaxSize
import androidx.compose.material3.*
import androidx.compose.runtime.Composable
import androidx.compose.ui.Modifier
import androidx.compose.ui.tooling.preview.Preview

@OptIn(ExperimentalMaterial3Api::class)
@Composable
fun MyScaffoldExample() {
    Scaffold(
        topBar = {
            // AppBar tanımı
            TopAppBar(
                title = { Text("Scaffold Örneği") },
                actions = {
                    IconButton(onClick = { /* Action */ }) {
                        Icon(Icons.Default.Settings, contentDescription = "Ayarlar")
                    }
                }
            )
        },
        bottomBar = {
            // Alt navigasyon çubuğu
            BottomAppBar {
                Text("Alt Navigasyon")
            }
        },
        floatingActionButton = {
            // Floating Action Button
            FloatingActionButton(onClick = { /* Action */ }) {
                Icon(Icons.Default.Add, contentDescription = "Ekle")
            }
        },
        content = { paddingValues ->
            // Ana içerik alanı
            Column(
                modifier = Modifier
                    .fillMaxSize()
                    .padding(paddingValues) // İçeriğin altındaki boşluğu ayarla
            ) {
                Text("Merhaba, Jetpack Compose!")
                // Diğer içerikler buraya eklenebilir
            }
        }
    )
}

@Preview(showBackground = true)
@Composable
fun PreviewMyScaffoldExample() {
    MyScaffoldExample()
}

```

 ![[Pasted image 20241023180025.png|250]]
 
- **paddingValues**: Scaffold, içeriği belirli bir boşlukla çevreler. Bu nedenle `content` fonksiyonuna bir `paddingValues` parametresi gönderir. Bu parametre, diğer bileşenlerin üstündeki AppBar veya altındaki BottomBar ile çakışmaması için gerekli olan boşluğu sağlar.
- **Dinamik İçerik**: Scaffold, içeriğin dinamik olarak değişebilmesi için esneklik sunar. Farklı durumlarda farklı içerikler göstermek mümkündür.

****
***Abdullah TANRIVERDİ***