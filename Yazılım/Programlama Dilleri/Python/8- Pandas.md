#Yazılım #ProgramlamaDilleri #Python 

![[pandas.png]]

Pandas, Pythob için bir veri analizi kütüphanesidir. İki an veri yapısı kullanır:
- **Series** tek boyutlu veri yapısı (listeler gibi)
- **DataFrame** tablo benzeri iki boyutlu veri yapısı(excel veya sql tabloları gibi)

**Kurulum ve İçe Aktarma**
```python
# Pandas'ı kurmak için:
pip install pandas

# Pandas'ı projeye dahil etmek:
import pandas as pd

```

==**Pandas Veri Yapıları**==
- **Series** Tek bir veri sütununu ifade eder. Listeler, numpy dizileri veya dictionary'lerden oluşturulabilir.
```python
import pandas as pd

# Liste ile Series
s = pd.Series([10, 20, 30, 40])
print(s)

# Dictionary ile Series
data = {'a': 10, 'b': 20, 'c': 30}
s = pd.Series(data)
print(s)

```
Index, her veri elemanını benzersiz bir etiketi vardır.
Values, serinin elemanlarına erişebilirsiniz

```python
print(s.index)   # Index bilgisi
print(s.values)  # Değerler

```

- **DataFrame** İki boyutlu bir veri yapısıdır.Excel tablolarına benzer. Satır ve sütunlardan oluşur
```python
# DataFrame oluşturma
data = {'Name': ['Ali', 'Ayşe', 'Fatma'],
        'Age': [25, 30, 22],
        'Salary': [5000, 7000, 4500]}
df = pd.DataFrame(data)
print(df)

```

==**Veri Okuma ve Yazma**==
- **Veri Okuma**
1. CSV dosyasından okuma
```python
df = pd.read_csv('dosya.csv')

```
2. Excel dosyasından okuma
```python
df = pd.read_excel('dosya.xlsx')

```

3. CSV dosyasına yazma
```python
df.to_csv('yeni_dosya.csv', index=False)

```
4. Excel dosyasına yazma
```python
df.to_excel('yeni_dosya.xlsx', index=False)

```

==**Veri Manipülasyonu**==
- **Sütunlara Erişim**
```python
print(df['Name'])  # Sadece Name sütununu alır

```
- **Satırlara Erişim**
```python
print(df.iloc[0])  # İlk satır
print(df.loc[0])   # İlk satır (index 0 olan)
# iloc (index numarası ile erişim)
# loc (index ismi ile erişim)

```

- **Filtreleme**
```python
# Yaşı 25'ten büyük olanları getir
filtered = df[df['Age'] > 25]
print(filtered)

```

- **Yeni Sütun Ekleme**
```python
df['Tax'] = df['Salary'] * 0.2  # Vergi sütunu ekle
print(df)

```


==**Eksik Verilerle Çalışma**==
Pandas eksik verileri NaN(Not a Number) ile temsil eder

- **Eksik Verileri Görme**
```python
print(df.isnull())  # Hangi hücrelerin eksik olduğunu gösterir
print(df.isnull().sum())  # Hangi sütunda kaç eksik veri var

```

- **Eksik Verileri Temizleme**
```python
df = df.dropna()  #satır silme

df['Age'] = df['Age'].fillna(df['Age'].mean())  # Eksik yaşları ortalama ile doldur

```

==**Gruplama ve Toplama**==
- **Gruplama**
```python
grouped = df.groupby('Age')['Salary'].sum()
print(grouped)

```

- **Toplama İşlemleri**
```python
print(df['Salary'].mean())  # Maaşların ortalaması
print(df['Salary'].max())   # En yüksek maaş

```

==**Pandas Fonksiyonları**==
Bazı kulllanılan pandas fonksiyonları 

| Fonksiyon       | Açıklama                  |
| --------------- | ------------------------- |
| `head()`        | İlk n satırı getirir      |
| `tail()`        | Son n satırı getirir      |
| `describe()`    | İstatistik özetini verir  |
| `sort_values()` | Veriyi sıralar            |
| `drop()`        | Satır veya sütun siler    |
| `merge()`       | İki DataFrame birleştirir |
| `pivot_table()` | Pivot tablo oluşturur     |

---
***Abdullah TANRIVERDİ***
