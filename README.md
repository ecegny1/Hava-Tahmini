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

  '''bash 
pip install pandas matplotlib seaborn plotly prophet
  '''
