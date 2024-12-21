#Yazılım #ProgramlamaDilleri #Python 

![[numpy.png]]


Numpy (Numerical Python), Python'da sayısal hesaplamalar yapmak için kullanılan bir kütüphanedir. Temel olarak büyük, çok boyutlu diziler(arrays) ve matrislerle çalışmayı kolaylaştıran yöntemler sunar.

**Kullanım Alanları:**
- Veri analizi.
- Makine öğrenmesi.
- Görüntü işleme.
- İstatistiksel analiz.
- Finansal modelleme.

**Özellikleri**
- Hızlı ve verimli hesaplama için optimize edilmiştir
- Veri analizi ve veri manipülasyonu kolaylaştırır.
- İstatistik, lineer cebir ve Fourier dönüşümleri için özelleşmiş fonksiyonlar sunar

**NumPy Kurulumu**
```bash
pip install numpy
```


**İmport Etme**
```python
import numpy as np
```

**Numpy Dizileri(Arrays)** 
- **Array Oluşturma**
```python
import numpy as np

# Tek boyutlu dizi
a = np.array([1, 2, 3])

# İki boyutlu dizi
b = np.array([[1, 2], [3, 4]])

# Boş dizi
c = np.zeros((3, 3))

# Rastgele değerli dizi
d = np.random.rand(2, 3)

```
- **Array Özellikleri**
```python
print(a.shape)  # Dizi boyutu
print(a.dtype)  # Veri tipi
print(a.ndim)   # Boyut sayısı

```

-  **Aralık Oluşturma**
```python
# Sıfırlarla dolu matris
zeros = np.zeros((3, 4))

# Birlerle dolu matris
ones = np.ones((2, 3))

# Rastgele değerli matris
rand = np.random.rand(3, 3)

# Belirli bir aralıkta sayılar
arange = np.arange(0, 10, 2)

# Eşit aralıklı sayılar
linspace = np.linspace(0, 10, 5)


```

- **Matematiksel İşlemler**
```python
x = np.array([1, 2, 3])
y = np.array([4, 5, 6])

# Toplama
z = x + y

# Çarpma
z = x * y

# Ortalama
mean = np.mean(x)


arr = np.array([1, 2, 3, 4, 5])

# Toplam ve Ortalama
print(np.sum(arr))       # 15
print(np.mean(arr))      # 3.0

# Minimum ve Maksimum
print(np.min(arr))       # 1
print(np.max(arr))       # 5

# Standart Sapma ve Varyans
print(np.std(arr))       # 1.414
print(np.var(arr))       # 2.0

# Logaritma ve Kare Alma
print(np.log(arr))       # [0.   0.69 1.09 1.38 1.61]
print(np.sqrt(arr))      # [1.   1.41 1.73 2.   2.24]


```

- **Matris Çarpımı**
```python
A = np.array([[1, 2], [3, 4]])
B = np.array([[5, 6], [7, 8]])
C = np.dot(A, B)  # Matris çarpımı

```

- **İstatiksel Fonksiyonlar** 
```python
data = np.array([1, 2, 3, 4, 5])

print(np.max(data))   # Maksimum
print(np.min(data))   # Minimum
print(np.std(data))   # Standart sapma

```
- **CSV Okuma**
```python
data = np.genfromtxt('data.csv', delimiter=',', skip_header=1)

```

- **CSV Yazma**
```python
# CSV Yazma 
np.savetxt('output.csv', data, delimiter=',')
```
- **Filtreleme**
```python
# 3'ten büyük değerler
filtered = data[data > 3]

```
- **Eksik Veri İşleme**
```python
data = np.array([1, np.nan, 3, 4])
mean = np.nanmean(data)  # NaN'leri yoksayarak ortalama al

```
NumPy, veri analizi ve veri bilimi projelerinde temel taş niteliğindedir.
***

***Abdullah TANRIVERDİ***
