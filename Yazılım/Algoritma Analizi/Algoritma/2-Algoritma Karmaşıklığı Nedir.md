#Yazılım #Algoritma 

Bir algoritma tükettiği Uzay ve Zaman miktarına göre karmaşık olarak tanımlanır. Bu nedenle bir algoritmanın Karmaşıklığı, yürütülmesi ve beklenen çıktıyı elde etmesi için ihtiyaç duyacağı zamanın ölçüsünü ve tüm verileri (girdi, geçici veri ve çıktı) depolamak için ihtiyaç duyacağı Uzayı ifade eder. Bu nedenle bu iki faktör bir algoritmanın verimliliğini tanımlar.

- **Zaman Faktörü**: Algoritmanın çalışması için geçen süreyi ölçer ve genellikle giriş boyutuna bağlı olarak ifade edilir.

- **Alan (Uzay) Faktörü**: Algoritmanın çalışması için gereken bellek miktarını ölçer ve genellikle giriş boyutuna bağlı olarak ifade edilir.


**Zaman Karmaşıklığı Nasıl Hesaplanır?**
Bir algoritmanın zaman karmaşıklığı, algoritmanın yürütülmesi ve sonucu alması için gereken zaman miktarını ifade eder. Bu, normal işlemler, koşullu if-else ifadeleri, döngü ifadeleri vb. için olabilir.

- **Sabit Zaman** Sadece bir kez yürütülen herhangi bir talimat bu parçaya gelir. Örneğin, giriş, çıkış, if-else, switch, aritmetik işlemler, vb.
- **Değişken Zaman** Birden fazla kez, diyelim ki n kez yürütülen herhangi bir talimat bu parçaya gelir. Örneğin, döngüler, yineleme, vb.  Bu nedenle zaman karmaşıklığı C(P) herhangi bir algoritmanın P'si T(P)=C+TP(I)'dır, burada C sabit zaman kısmıdır ve TP(I) algoritmanın değişken kısmıdır ve bu da örnek karakteristiği I'e bağlıdır.

**Uzay Karmaşıklığı Nasıl Hesaplanır?**
Bir algoritmanın uzay karmaşıklığı, algoritmanın değişkenleri depolamak ve sonucu almak için ihtiyaç duyduğu bellek miktarını ifade eder. Bu, girdiler, geçici işlemler veya çıktılar için olabilir.

- **Sabit Uzay** Bu, algoritmanın ihtiyaç duyduğu alanı ifade eder. Örneğin, giriş değişkenleri, çıkış değişkenleri, program boyutu, vb.
-  **Değişken Uzay** Bu, algoritmanın uygulanmasına bağlı olarak farklı olabilen alanı ifade eder. Örneğin, geçici değişkenler, dinamik bellek tahsisi, yineleme yığın alanı, vb. Bu nedenle herhangi bir algoritmanın uzay karmaşıklığı S(P) herhangi bir algoritmanın S(P)=C+SP(I)'dır, burada C sabit parçadır ve S(I) algoritmanın değişken parçasıdır ve bu da örnke özelliği I'e bağlıdır.


