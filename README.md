# Credit Card Fraud Detection

Kredi kartı işlemlerinde dolandırıcılık (fraud) tespiti için makine öğrenmesi projesi.
[ULB (Université Libre de Bruxelles) Credit Card Fraud veri seti](https://www.kaggle.com/mlg-ulb/creditcardfraud) kullanılmıştır.

## Veri Seti
- 284,807 işlem, sadece 492 tanesi fraud (**%0.17**) — ciddi sınıf dengesizliği
- Özellikler: V1-V28 (PCA ile anonimleştirilmiş, gizlilik nedeniyle yorumlanamıyor), Time, Amount
- Eksik veri yok

## Yapılan Analizler (EDA)
- Sınıf dağılımı incelendi, dengesizlik doğrulandı
- Amount ve Time değişkenlerinin sınıflara göre dağılımı karşılaştırıldı
- Amount değişkeni sağa çarpık (right-skewed) bulundu → log-transform uygulandı
- V1-V28 değişkenlerinin Class ile korelasyonu incelendi, korelasyon heatmap oluşturuldu

## Modelleme
**Baseline Model:** Logistic Regression (`class_weight='balanced'`)

| Metrik | Skor |
|--------|------|
| Recall (fraud sınıfı) | 0.92 |
| Precision (fraud sınıfı) | 0.06 |
| PR-AUC | 0.71 |
| ROC-AUC | 0.97 |

**Not:** Dengesiz veri seti nedeniyle accuracy yerine Precision, Recall ve PR-AUC metrikleri esas alınmıştır.


## Kullanılan Kütüphaneler
`pandas`, `numpy`, `scikit-learn`, `matplotlib`, `seaborn`
