#Yazılım #MobilGeliştirme #AndroidGeliştirmeKotlin 

![[Automated_Test_Anroid.jpg|600]]

Automated Test, uygulamamızın UI bileşenleri,davranışları  ve performansını test etmek için kullanılan bir tekniktir. Bu testler uygulamızın çeşitli durumlar altında nasıl davrandığını doğrulamak için otomatikleştirilmiş test seneryoları yazarak gerçekleştirilir. Jetpack Compose bu test süreçlerini kolaylaştırmak için bir dizi araç ve kütüphane sağlar.

==**Automated Test**==

Jetpack Compose'da üç ana test türü bulunmaktadır:

- **Unit Tests (Birim Testleri)**: Tek bir bileşenin veya fonksiyonun doğru çalışıp çalışmadığını kontrol eder. Genellikle, küçük ve izole testlerdir.
    
- **UI Tests (Kullanıcı Arayüzü Testleri)**: Uygulamanın kullanıcı arayüzünün işlevselliğini ve görünümünü test eder. Kullanıcı etkileşimlerini simüle eder ve UI bileşenlerinin doğru şekilde render edilip edilmediğini kontrol eder.
    
- **Integration Tests (Entegrasyon Testleri)**: Farklı bileşenlerin ve sistemlerin bir arada nasıl çalıştığını test eder. Birden fazla bileşenin birbirleriyle etkileşimini ve veri alışverişini kontrol eder.


==**Unit Tests (Birim Testleri)**==
Tek bir bileşen veya fonksiyonun işlevselliğini bağımsız olarak doğrulayan küçük testlerdir. Amaç, izole edilmiş olarak her bileşenin tek başına doğru çalıştığını garanti etmektir. Birim testleri, genellikle iş mantığı, veri dönüşümleri, veya tek bir fonksiyon üzerinde uygulanır.

 **Unit Testlerde Öne Çıkanlar:**
- **Hızlıdır**: Kodun çok küçük bir bölümünü test ettiği için daha hızlı çalışır.
- **İzole**: Başka bileşenlerle bağımsız olduğundan, dış etkiler (UI, ağ, vs.) testleri etkilemez.
- **Güvenilir**: Hataların kaynağını doğrudan bulmak kolaydır.

**Örnek Senaryolar:**
- Verilen iki sayının toplandığını doğrulamak.
- Bir sınıfta belirli bir mantığın doğru çalışıp çalışmadığını kontrol etmek.

Aşağıdaki örnek, `calculateValue()` isimli bir fonksiyonun doğru sonucu döndürüp döndürmediğini test eder:
```kotlin
@Test
fun calculateValue_correctOutput() {
    val result = calculateValue(3, 4)
    assertEquals(7, result)
}

```


==**UI Tests (Kullanıcı Arayüzü Testleri)**==
Compose bileşenlerinin görünürlüğü ve kullanıcı etkileşimleri ile ilgili doğrulamalarda bulunur. UI testleri, kullanıcı davranışlarını simüle eder ve ekran üzerindeki bileşenlerin doğru bir şekilde render edilip edilmediğini ve kullanıcı etkileşimleri sonrasında beklenen değişimlerin gerçekleşip gerçekleşmediğini kontrol eder.

**UI Testlerinde Öne Çıkanlar:**
- **Etkileşim Testleri**: Kullanıcı etkileşimlerini simüle ederek, buton tıklamaları veya liste kaydırmaları gibi işlemleri test eder.
- **Görünürlük ve Doğrulama**: Belirli bir bileşenin görünür olup olmadığını ve beklenen metinlerin doğru olup olmadığını kontrol eder.
- **Dinamik Değişiklikler**: Kullanıcı etkileşimlerinden sonra bileşenlerin durum değişikliklerini gözlemler.

**Örnek Senaryolar:**
- Bir butona tıklandığında bir metin güncelleniyor mu?
- Belli bir etiketle (tag) belirtilen bileşen ekranda görünüyor mu?
```kotlin
@get:Rule
val composeTestRule = createComposeRule()

@Test
fun button_click_updatesText() {
    composeTestRule.setContent {
        MyComposable() // Test edilecek bileşeni çağırıyoruz
    }
    
    // "Click Me" butonunu bul ve tıklama işlemi yap
    composeTestRule.onNodeWithText("Click Me").performClick()
    
    // Buton tıklandıktan sonra, metnin "Clicked" olup olmadığını doğrula
    composeTestRule.onNodeWithText("Clicked").assertIsDisplayed()
}

```

==**Integration Tests (Entegrasyon Testleri)**==
Uygulamanın farklı bileşenlerinin veya modüllerinin bir arada nasıl çalıştığını doğrulamak için kullanılır. Bu testlerde birden fazla bileşen veya sınıf bir araya getirilir ve bu bileşenlerin doğru veri alışverişi yapıp yapmadığı test edilir.


**Entegrasyon Testlerinde Öne Çıkanlar:**
- **Birlikte Çalışabilirlik**: Farklı bileşenlerin birlikte çalışabilirliğini test eder.
- **Veri Alışverişi**: Ekranlar veya bileşenler arasında veri aktarımının doğru olup olmadığını kontrol eder.
- **Dış Bağlantılar**: Veri tabanı veya ağ işlemleri gibi dış bağlantıları simüle ederek, uygulamanın bütünsel performansını gözlemler.

**Örnek Senaryolar:**
- Bir liste elemanına tıklandığında ayrıntılı bilgi ekranının doğru bilgiyle açılması.
- Bir bileşende yapılan değişikliklerin başka bir bileşende güncellenip güncellenmediğini kontrol etmek.

```kotlin
@get:Rule
val composeTestRule = createComposeRule()

@Test
fun list_click_opensDetailScreen() {
    composeTestRule.setContent {
        MyComposableApp()
    }
    
    // Listede "Item 1" olan bir öğeyi bul ve tıklama işlemi yap
    composeTestRule.onNodeWithText("Item 1").performClick()
    
    // Detay ekranının açıldığını ve "Item 1 Detail" metninin göründüğünü doğrula
    composeTestRule.onNodeWithText("Item 1 Detail").assertIsDisplayed()
}

```
==**Test Anotasyonları ve Araçlar**==

**`@VisibleForTesting` Anotasyonu**
Bir metodun veya bileşenin yalnızca test amaçlı kullanılmak üzere görünür yapılmasını sağlar. Bu şekilde, test senaryolarında kullanılan bileşenlerin gereksiz yere genel API’de görünür olması engellenir.
```kotlin
@VisibleForTesting
fun calculateValue(): Int {
    return 42
}

```

`ComposeTestRule`
Compose bileşenlerinin test ortamında başlatılmasını ve yönetilmesini sağlayan bir kuraldır. Testleri yönetir, bileşenleri başlatır ve kullanıcı etkileşimlerini simüle eder.

```kotlin
@get:Rule
val composeTestRule = createComposeRule()

```

**Diğer Test Araçları ve Fonksiyonlar**
- **`onNodeWithTag`**: Belirli bir etiketle işaretlenmiş (tagged) bileşeni bulur.
- **`performClick`**: Bir bileşen üzerinde tıklama eylemini simüle eder.
- **`assertIsDisplayed`**: Bileşenin görünür olduğunu doğrular.
- **`assertTextEquals`**: Bileşendeki metnin belirli bir değere eşit olduğunu doğrular.
- **`performTextInput`**: Bir metin giriş alanına metin girişi yapılmasını simüle eder

****
***Abdullah TANRIVERDİ***
