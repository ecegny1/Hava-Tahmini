# Hava Durumu Tahmini

## Genel Bakış

Bu proje, Facebook tarafından geliştirilen açık kaynaklı Prophet aracını kullanarak zaman serisi tahmini yapmayı gösterir. Amaç, Delhi'deki geçmiş veri setine dayanarak meantemp (ortalama sıcaklık) değerlerinin gelecekteki değerlerini tahmin etmektir. Notebook, veri ön işleme, model eğitimi ve Plotly kullanılarak yapılan etkileşimli görselleştirmeyi içerir.

## Proje Yapısı

Veri Hazırlığı: Verilerin model eğitimi için yüklenmesi ve hazırlanması.
Model Eğitimi: Bir Prophet modeli oluşturulup eğitilmesi.
Tahmin: Gelecekteki değerlerin tahmin edilmesi.
Görselleştirme: Etkileşimli Plotly grafikleri ile tahminlerin görüntülenmesi.

## Gereksinimler

Aşağıdaki Python kütüphanelerinin yüklü olması gerekmektedir:

pandas
matplotlib
seaborn
plotly
prophet

Bu kütüphaneleri yüklemek için aşağıdaki komutu çalıştırabilirsiniz:

```bash
pip install pandas matplotlib seaborn plotly prophet
```

## Kodun Açıklanması

### 1. Veri Hazırlığı

```bash
import pandas as pd
```

### Veri setini yükle

```bash
data = pd.read_csv("/path/to/your/weather_forecasting/DailyDelhiClimateTrain.csv")
```

### Tarih sütununu datetime formatına çevir

```bash
data["date"] = pd.to_datetime(data["date"], format='%Y-%m-%d')
```

### Yıl ve ay sütunlarını oluştur

```bash
data['year'] = data['date'].dt.year
data["month"] = data["date"].dt.month
```

### Verinin ilk birkaç satırını görüntüle

```bash
print(data.head())
```
### 2. Prophet için Veri Ön İşleme

### Sütun adlarını Prophet'in formatına uygun hale getir

```bash
forecast_data = data.rename(columns={"date": "ds", "meantemp": "y"})
```

```bash
print(forecast_data)
```

### 3. Model Eğitimi ve Tahmin

```bash
from prophet import Prophet
from prophet.plot import plot_plotly
```

### Prophet modelini başlat

```bash
model = Prophet()
```

### Modeli veriye uygula

```bash
model.fit(forecast_data)
```

### 365 gün için gelecek veri çerçevesini oluştur

```bash
forecasts = model.make_future_dataframe(periods=365)
```

### Tahminleri oluştur

```bash
predictions = model.predict(forecasts)
```

### Tahminleri görselleştir

```bash
plot_plotly(model, predictions)
```

## Görselleştirme

plot_plotly fonksiyonu, geçmiş ve tahmin edilen değerleri içeren etkileşimli bir grafiği gösterir.
Grafik üzerinde yakınlaştırma yapabilir ve veri noktaları üzerinde durarak detaylı bilgi alabilirsiniz.
