# Iris Veri Seti ile Sınıflandırma Analizi ve Model Karşılaştırma

Bu proje, makine öğrenmesi literatürünün en temel taşlarından biri olan **Iris Veri Seti** üzerinde farklı algoritmaların performansını ölçmek ve veri ön işleme tekniklerinin model üzerindeki etkisini analiz etmek amacıyla geliştirilmiştir.

## Veri Seti Hakkında: Iris (Süsen Çiçeği)

Çalışmada, 3 farklı Iris çiçeği türüne (Setosa, Versicolor, Virginica) ait morfolojik ölçümler içeren veri seti kullanılmıştır. 

* **Özellikler (Features):** Çanak yaprak (sepal) uzunluğu/genişliği ve taç yaprak (petal) uzunluğu/genişliği (toplam 4 özellik).
* **Sınıflandırma Hedefi:** Çiçeğin fiziksel ölçümlerine dayanarak 3 türden hangisine ait olduğunu tahmin etmek.
* **Analiz Notu:** Iris-Setosa türü diğerlerinden doğrusal olarak kolayca ayrılabilirken, Versicolor ve Virginica türleri arasındaki sınırı belirlemek model başarısı için asıl kriterdir.

## 🛠 Teknik Yaklaşım ve İş Akışı

### 1. Veri Ön İşleme ve Ölçeklendirme
Modellerin sayısal büyüklüklerden (magnitude) olumsuz etkilenmemesi ve daha hızlı yakınsaması için **StandardScaler** kullanılmıştır.
* **Data Leakage Önlemi:** Scaler nesnesi sadece `X_train` üzerinde eğitilmiş (`fit_transform`), test verisi ise bu parametrelerle dönüştürülmüştür (`transform`).

### 2. Kullanılan Modeller
* **Support Vector Machine (SVM):** Özellikle karmaşık sınırları çizebilmek için `RBF Kernel` tercih edilmiştir.
* **Naive Bayes:** Olasılıksal sınıflandırma başarısını ölçmek için uygulanmıştır.
* **Lineer Regresyon:** Sayısal tahminleme metriklerini (MAE, MSE, R²) test etmek için kullanılmıştır.

## 📈 Model Performansı ve Sonuçlar

Yapılan testler sonucunda SVM modeli, test setindeki 38 örneğin tamamını doğru tahmin ederek kusursuz bir performans sergilemiştir.

**Classification Report:**
```text
              precision    recall  f1-score   support

           0       1.00      1.00      1.00        12
           1       1.00      1.00      1.00        14
           2       1.00      1.00      1.00        12

    accuracy                           1.00        38





