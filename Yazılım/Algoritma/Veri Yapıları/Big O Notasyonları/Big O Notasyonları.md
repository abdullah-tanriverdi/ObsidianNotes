#Yazılım #Algoritma #VeriYapıları
Yazılım geliştirme dünyasında, algoritmaların performansını değerlendirmek kritik öneme sahiptir. Bu değerlendirmelerin çoğu Big O notasyonu kullanılarak yapılır. Big O notasyonu, algortimaların zaman ve mekan karmaşıklığını analiz etmek için kullanılan matematiksel bir araçtır. 

Büyük O gösterimi algoritmaların en kötü durum performansını temsil eder. Algoritmaların giriş boyutu (n) arttıkça nasıl davrandığını gösterir. Bu gösterim algoritmaların ne kadar hızlı çalıştığını ve ne kadar bellek kullandıklarını anlamamıza yardımcı olur.

## Yaygın Büyük O Notasyonları 

- ==**O(1) — Sabit Zaman Karmaşıklığı:**== Bu gösterim algoritmaların yürütme süresinin girdi boyutundan bağımsız olduğunu belirtir. Böyle bir algoritma sabit bir sürede tamamlanır; örneğin, bir dizinin ilk öğesine erişim gibi işlemler O(1) karmaşıklığa sahiptir. Bu, en hızlı ve en verimli algortima türü olarak kabul edilir

```java
public class ConstantTimeExample {
    public static void main(String[] args) {
        // Bir dizi tanımla ve bazı değerler ata
        int[] numbers = {10, 20, 30, 40, 50};
        
        // Dizide belirli bir indeksdeki elemana eriş
        int index = 2; // 2. indeks
        int value = getValueAtIndex(numbers, index);
        
        // Sonucu konsola yazdır
        System.out.println("Dizinin " + index + ". indeksindeki değer: " + value);
    }
    
    // O(1) zaman karmaşıklığına sahip metot
    public static int getValueAtIndex(int[] array, int index) {
        return array[index]; // Belirli bir indekse doğrudan erişim
    }
}

```


- ==**O(log n) — Logaritmik Zaman Karmaşıklığı:**==  O(log n) gösterimi, algoritmanın yürütme süresinin giriş boyutunun logaritmasıyla orantılı olarak arttığını gösterir. İkili arama algoritmaları, her adımda arama alanını yarıya indirdikleri için bu tür karmaşıklığa sahiptir.



```java 
public class LogarithmicTimeComplexity { 
    
    public static int binarySearch(int[] arr, int target) { 
        int left = 0; // Arama aralığının sol sınırı 
        int right = arr.length - 1; // Arama aralığının sağ sınırı 
        
        while (left <= right) { // Aralık geçerli olduğu sürece aramaya devam et 
            int mid = left + (right - left) / 2; // Ortadaki dizini hesapla 
            
            if (arr[mid] == target) { 
                return mid; // Hedef bulundu, dizinini döndür
            } 
            
            if (arr[mid] < target) { 
                left = mid + 1; // Hedef ortadaki elemandan büyükse sağ yarıya git
            } else { 
                right = mid - 1; // Hedef ortadaki elemandan küçükse sol yarıya git
            } 
        } 
        
        return -1; // Hedef dizide bulunamadı
    } 

    public static void main(String[] args) { 
        int[] sortedArray = {1, 3, 5, 7, 9, 11, 13, 15, 17, 19}; // Sıralanmış dizi 
        int target = 7; // Aranacak değer 
        
        int result = binarySearch(sortedArray, target); // İkili arama gerçekleştir 
        
        if (result != -1) { 
            System.out.println("Hedef " + target + " dizide " + result + ". dizininde bulundu."); 
        } else { 
            System.out.println("Hedef " + target + " dizide bulunamadı."); 
        } 
    } 
}
```

-  ==**O(n) — Doğrusal Zaman Karmaşıklığı:**== Bu gösterim algoritmanın yürütme süresinin girdinin boyutuyla doğru orantılı olduğunu gösterir. Örneğin, bir dizinin her bir öğesini ayrı ayrı kontrol etmek O(n) karmaşıklığa sahiptir çünkü işlem süresi dizinin uzunluğuna bağlıdır.

```java 
public class LinearTimeExample {
    public static void main(String[] args) {
        // Bir dizi tanımla ve bazı değerler ata
        int[] numbers = {5, 10, 15, 20, 25};
        
        // Dizideki tüm elemanların toplamını hesapla
        int total = sumArray(numbers);
        
        // Hesaplanan toplamı konsola yazdır
        System.out.println("Dizideki tüm elemanların toplamı: " + total);
    }
    
    // O(n) zaman karmaşıklığına sahip metot
    public static int sumArray(int[] array) {
        int sum = 0; // Toplamı tutacak değişkeni başlat
        
        // Dizideki her elemanı toplayarak sum değişkenine ekle
        for (int number : array) {
            sum += number; // Her elemanı toplama ekle
        }
        
        // Toplamı döndür
        return sum;
    }
}

```

- ==**O(n log n) — Doğrusal Zaman Karmaşıklığı:**==O(n log n), bir algoritmanın yürütme süresinin girdi boyutu (n) arttıkça hem doğrusal hem de logaritmik olarak arttığını gösterir. Bu karmaşıklığa sahip algoritmalar genellikle sıralama işlemlerinde kullanılır. Örneğin, Hızlı Sıralama ve Birleştirme Sıralaması gibi algoritmalar büyük veri kümelerinde etkili ve hızlıdır. Bu, veri miktarı arttıkça, işlem süresinin hem n hem de log n faktörleriyle arttığı anlamına gelir.

```java 
public class LinearithmicTimeComplexityQuickSort { 
    // Ana sıralama fonksiyonu 
    public static void quickSort(int[] dizi, int düşük, int yüksek) { 
        if (düşük < yüksek) { 
            // Bölümlemeyi gerçekleştir ve pivot indeksini al 
            int pi = partition(dizi, düşük, yüksek); 

            // Pivottan önceki ve sonraki elemanları yinelemeli olarak sırala
            quickSort(dizi, düşük, pi - 1);   // Sol alt dizi
            quickSort(dizi, pi + 1, yüksek); // Sağ alt dizi
        } 
    } 

    // Bölümleme fonksiyonu: pivot elemanını doğru konuma yerleştirir 
    private static int partition(int[] dizi, int düşük, int yüksek) { 
        int pivot = dizi[yüksek]; // Pivot olarak en sağdaki elemanı seç 
        int i = (düşük - 1); // Daha küçük elemanın indeksi 

        // Pivottan önce daha küçük elemanları taşıyarak diziyi yeniden düzenle 
        for (int j = düşük; j < yüksek; j++) { 
            if (dizi[j] <= pivot) { 
                i++; 
                // i ve j indekslerindeki elemanları değiştir 
                int temp = dizi[i]; 
                dizi[i] = dizi[j]; 
                dizi[j] = temp; 
            } 
        } 

        // Pivot elemanını doğru konuma yerleştir 
        int temp = dizi[i + 1]; 
        dizi[i + 1] = dizi[yüksek]; 
        dizi[yüksek] = temp; 

        // Pivot elemanının indeksini döndür 
        return i + 1; 
    } 

    // Örnek kullanım 
    public static void main(String[] args) { 
        // Sıralanacak örnek dizi 
        int[] dizi = {10, 7, 8, 9, 1, 5}; 

        // Orijinal diziyi yazdır
        System.out.println("Orijinal dizi:"); 
        for (int num : dizi) { 
            System.out.print(num + " "); 
        } 
        System.out.println(); 

        // Diziyi sıralamak için QuickSort algoritmasını uygula
        quickSort(dizi, 0, dizi.length - 1); 

        // Sıralanmış diziyi yazdır
        System.out.println("Sıralanmış dizi:"); 
        for (int num : dizi) { 
            System.out.print(num + " "); 
        } 
    } 
}

```


-  ==**O(n²) — İkinci Dereceden Zaman Karmaşıklığı:**== Bu tür algoritmalar, giriş boyutunun karesine orantılı zaman alır. Örneğin, her bir elemanı iki iç içe döngü kullanarak karşılaştırmak bu kategoriye girer. Bir matrisin her bir elemanını kontrol etmek O(n²) karmaşıklığa sahiptir.

```java 
public class QuadraticTimeExample { 
    public static void main(String[] args) { 
        // 2 boyutlu bir matris tanımla ve bazı değerlerle başlat 
        int[][] matrix = { 
            {1, 2, 3}, 
            {4, 5, 6}, 
            {7, 8, 9} 
        }; 
        
        // Matrisin her bir elemanını yazdır
        printMatrix(matrix); 
    } 
    
    // O(n^2) zaman karmaşıklığına sahip yöntem 
    public static void printMatrix(int[][] matrix) { 
        // Matrisin her bir satırını yinele 
        for (int i = 0; i < matrix.length; i++) { 
            // Geçerli satırdaki her bir elemanı yinele 
            for (int j = 0; j < matrix[i].length; j++) { 
                // Geçerli elemanı yazdır
                System.out.print(matrix[i][j] + " "); 
            } 
            // Mevcut satırdaki tüm elemanları yazdırdıktan sonra bir sonraki satıra geç
            System.out.println(); 
        } 
    } 
}

```

- ==**O(2^n) — Üstel Zaman Karmaşıklığı:**== O(2^n), algoritmanın yürütme süresinin girdi boyutu arttıkça üstel olarak arttığını gösterir. Bu, algoritmanın veri miktarı arttıkça çok hızlı bir şekilde yavaşladığı anlamına gelir. Örneğin, tüm olası kombinasyonları hesaplayan algoritmalar bu tür karmaşıklığa sahiptir. Küçük veri kümelerinde çalışabilirler ancak daha büyük veri kümelerinde çok yavaş hale gelirler.


```java 
import java.util.ArrayList; 
import java.util.List; 

public class ExponentialTimeComplexity { 

    // Ana fonksiyon: Alt kümeleri başlatır ve yazdırır 
    public static void main(String[] args) { 
        int[] nums = {1, 2, 3}; // Örnek dizi
        List<List<Integer>> subsets = new ArrayList<>(); // Alt kümeleri saklamak için liste
        generateSubsets(nums, 0, new ArrayList<>(), subsets); // Alt kümeleri oluştur
        System.out.println(subsets); // Sonuçları yazdır
    } 

    // Alt kümeleri oluşturmak için yardımcı fonksiyon 
    public static void generateSubsets(int[] nums, int index, List<Integer> current, List<List<Integer>> subsets) { 
        // Geçerli alt kümeyi listeye ekle
        subsets.add(new ArrayList<>(current)); 

        // Alt kümeleri oluşturmak için kalan öğeleri işle 
        for (int i = index; i < nums.length; i++) { 
            current.add(nums[i]); // Geçerli öğeyi alt kümeye ekle
            generateSubsets(nums, i + 1, current, subsets); // Özyinelemeli çağrı: Sonraki öğeyle devam et
            current.remove(current.size() - 1); // Son eklenen öğeyi kaldır (geri izleme)
        } 
    } 
}

```

- ==**O(n!) — Faktöriyel Zaman Karmaşıklığı:**== O(n!) gösterimi, bir algoritmanın yürütme süresinin girdi boyutunun faktöriyeli kadar arttığını gösterir. Bu, veri miktarı arttıkça, işlem süresinin çok hızlı arttığı anlamına gelir. Bu tür algoritmalar genellikle permütasyon problemlerinde kullanılır ve büyük veri kümeleriyle çok yavaş hale gelir.

Örneğin, "Gezgin Satıcı Problemi" gibi problemler tüm olası rotaları kontrol etmeyi gerektirir. 4 şehir varsa, tüm olası rotaları hesaplamak 4! (4 faktöriyel) anlamına gelir, bu da 24 farklı rotaya eşittir. Ancak, şehir sayısı arttıkça, bu sayı hızla büyür. Örneğin, 10 şehirle, hesaplanacak rota sayısı 10! (3.628.800) olur. Bu nedenle, bu karmaşıklığa sahip algoritmalar büyük veri kümeleri için önemli miktarda zaman alır.

```java 
import java.util.ArrayList;
import java.util.List;

public class FactorialTimeComplexityPermutationGenerator {

    // Ana fonksiyon: Diziyi başlatır ve tüm permütasyonları yazdırır
    public static void main(String[] args) {
        int[] nums = {1, 2, 3}; // Elemanlara sahip örnek dizi
        List<List<Integer>> permutations = new ArrayList<>(); // Tüm permütasyonları saklamak için liste
        generatePermutations(nums, 0, permutations); // Permütasyonları 0. indeksten itibaren oluştur
        System.out.println(permutations); // Tüm permütasyonları yazdır
    }

    // Dizinin tüm permütasyonlarını oluşturmak için yardımcı fonksiyon
    public static void generatePermutations(int[] nums, int start, List<List<Integer>> permutations) {
        // Eğer başlangıç indeksi son pozisyondaysa, mevcut permütasyonu listeye ekle
        if (start == nums.length - 1) {
            List<Integer> permutation = new ArrayList<>();
            for (int num : nums) {
                permutation.add(num); // Mevcut diziyi permütasyon listesine kopyala
            }
            permutations.add(permutation); // Yeni permütasyonu permütasyonlar listesine ekle
        } else {
            // Her bir elemanı başlangıç indeksi ile değiştirerek permütasyonlar oluştur
            for (int i = start; i < nums.length; i++) {
                swap(nums, start, i); // Mevcut elemanı başlangıç elemanı ile değiştir
                generatePermutations(nums, start + 1, permutations); // Sonraki indeks için permütasyonları özyinelemeli olarak oluştur
                swap(nums, start, i); // Diziyi eski haline döndürmek için geri değiştir (geri izleme)
            }
        }
    }

    // Dizideki iki elemanı değiştirmek için yardımcı fonksiyon
    private static void swap(int[] nums, int i, int j) {
        int temp = nums[i]; // i indeksindeki değeri geçici olarak sakla
        nums[i] = nums[j]; // i indeksindeki değeri j indeksine ata
        nums[j] = temp; // Geçici olarak saklanan değeri j indeksine ata
    }
}

```

---
## Big O Notasyonların Karşılaştırılması

| Big O Notasyonları | Açıklama                                                                                  | Performans   |
| ------------------ | ----------------------------------------------------------------------------------------- | ------------ |
| O(1)               | Sabit zaman karmaşıklığı; giriş boyutundan bağımsız.                                      | Hızlı        |
| O(log n)           | Logaritmik zaman karmaşıklığı; giriş boyutuyla yavaşça artar.                             | Hızlı        |
| O(n)               | Doğrusal zaman karmaşıklığı; giriş boyutuyla doğru orantılıdır.                           | Orta         |
| O(n log n)         | Doğrusal-logaritmik zaman karmaşıklığı; doğrusal ve logaritmik büyümenin kombinasyonudur. | Orta-Yavaş   |
| O(n^2)             | İkinci dereceden zaman karmaşıklığı; giriş boyutunun karesiyle orantılı olarak artar.     | Yavaş        |
| O(2^n)             | Üssel zaman karmaşıklığı; giriş boyutuyla üssel olarak artar.                             | Çok Yavaş    |
| O(n!)              | Faktöriyel zaman karmaşıklığı; giriş boyutuyla faktöriyel olarak artar.                   | Ekstra Yavaş |

![[BigONotasyonlarınKarsilastirmalari.jpg]]<br>

---
## Kısaca
> [!tldr]  Özet
Big O notasyonu algoritmaların nasıl ölçeklendiğine dair temel bir içgörü sağlar ve bu notasyonda ustalaşmak etkili bir yazılım mühendisi olmanın anahtarıdır. Bu bilgiler aynı zamanda verimli çözümler tasarlamanızı ve uygulamanızı sağlayarak daha hızlı ve daha sağlam uygulamalara giden yolu açar.

***Abdullah TANRIVERDİ***