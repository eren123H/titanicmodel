# 🚢 Titanic Veri Madenciliği Projesi

Bu projede, 1912 yılında batan Titanic gemisindeki yolcuların hayatta kalıp kalmadığını çeşitli makine öğrenmesi modelleri kullanarak tahmin etmeye çalıştık. Model çıktıları; kurtarma senaryoları, güvenlik protokollerinin değerlendirilmesi ve sınıflandırma örnekleri için yol gösterici olabilecek niteliktedir.

## 📁 Veri Seti

- **Kaynak:** `Titanic-Dataset.csv`
- **Toplam Kayıt:** 891 yolcu bilgisi
- **Hedef Değişken:** `Survived` (1 = Hayatta, 0 = Öldü)
- **Bağımsız Değişkenler:**
  - Kategorik: `Sex`, `Embarked`, `Pclass`, `SibSp`, `Parch`
  - Sayısal: `Age`, `Fare`

## 🛠️ Veri Ön İşleme

- `Age` sütunundaki eksik veriler, medyan değer (≈ 28 yaş) ile dolduruldu.
- `Embarked` sütunundaki boş veriler, en sık liman olan `'S'` değeri ile tamamlandı.
- `Sex` ve `Embarked` değişkenleri One-Hot Encoding ile sayısal forma dönüştürüldü.
- `Survived` hedef değişken olarak ayrıldı, diğer sütunlar `X` veri matrisini oluşturdu.

## 🤖 Kullanılan Modeller ve Performans

| Model              | Doğruluk (%) | ROC AUC |
|-------------------|--------------|---------|
| Lojistik Regresyon | 81           | 0.88    |
| Karar Ağacı        | 79           | 0.88    |
| Random Forest      | 82           | 0.89    |

- **Random Forest**, en yüksek doğruluk ve ROC AUC skoruna ulaşarak en başarılı model oldu.
- **Lojistik Regresyon**, yorumlanabilirlik açısından öne çıktı.
- **Karar Ağaçları**, basit ve açıklayıcı kurallar üretme açısından faydalı
