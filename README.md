# Colab
Başlık
Titanic Yolcu Kurtme — İkili Sınıflandırma Projesi

Açıklama
Bu proje, Titanic veri seti kullanılarak yolcuların hayatta kalma olasılıklarını tahmin etmeyi amaçlar. Proje, veri keşfi (EDA), özellik mühendisliği, önişleme pipeline’ı, temel modeller (Lojistik Regresyon, Random Forest), opsiyonel bir Keras sinir ağı, model değerlendirme ve model kaydetmeyi içerir. Colab üzerinde adım adım çalışmak üzere hazırlandı.

Özellikler

Veri temizleme ve eksik değer impute etme
Yeni özellikler: Title, HasCabin, FamilySize
Sayısal/kategorik pipeline: imputasyon, ölçekleme, One-Hot Encoding
Modeller: Logistic Regression, Random Forest, opsiyonel Keras NN
Model değerlendirme: Accuracy, ROC AUC, Confusion Matrix, Classification Report
Basit GridSearch ile hiperparametre ayarı
Model serileştirme (joblib)
Dosya Yapısı (Colab için hücre sırası)

1_setup.ipynb (veya ilk hücre): kütüphaneler ve veri yükleme
2_eda.ipynb: keşifsel veri analizi, görselleştirmeler
3_feature_engineering.ipynb: feature oluşturma ve sütun seçimi
4_preprocessing_and_pipelines.ipynb: ColumnTransformer ve pipeline tanımı
5_model_training.ipynb: LR ve RF eğitimi, değerlendirme
6_hyperparameter_tuning.ipynb: GridSearch örneği
7_keras_model.ipynb (opsiyonel): basit sinir ağı
artifacts/: kaydedilmiş model dosyaları (titanic_rf_pipeline.joblib vb.)
README.md (bu dosya)
Kurulum & Çalıştırma (Colab)

Colab’da yeni notebook oluştur veya hazır .ipynb hücrelerini sırayla kopyala.
Runtime > Change runtime type > Python 3 (GPU gerekli değil).
Hücreleri sırasıyla çalıştır:
Kütüphaneler ve veri yükleme
EDA
Feature engineering
Train/test split + pipeline
Modelleri eğit ve değerlendir
(Opsiyonel) Hyperparameter tuning ve Keras NN
Modeli kaydetmek için joblib.dump(...) kullan.
Veri Kaynağı

Titanic veri seti (kamu): https://raw.githubusercontent.com/datasciencedojo/datasets/master/titanic.csv
Ana Komutlar (kısa örnek)

Veri yükleme: df = pd.read_csv(train_url)
Train/test split: train_test_split(...)
Pipeline tanımı: Pipeline([...]) ve ColumnTransformer([...])
Model eğitme: pipe.fit(X_train, y_train)
Model kaydetme: joblib.dump(pipe_rf, 'titanic_rf_pipeline.joblib')
Değerlendirme Metirikleri

Accuracy, Precision, Recall, F1-score (classification_report)
ROC AUC (roc_auc_score)
Confusion Matrix (sns.heatmap)
Sonuçlar (örnek)

Logistic Regression accuracy ≈ 0.79
Random Forest accuracy ≈ 0.81
Keras NN accuracy ≈ 0.80 (Not: Bu değerler kullandığın parametrelere ve rastlantısal tohumlara göre değişebilir.)
İyi Uygulamalar ve İleri Adımlar

Daha sofistike Age imputasyonu (model tabanlı)
Feature engineering: fare dönüşümleri, kabin harfi kullanımı
Stratified K-Fold CV, daha geniş hyperparameter aramaları (RandomizedSearch/Bayesian)
XGBoost/LightGBM ile karşılaştırma
Model açıklanabilirliği için SHAP kullanımı
Sonuçları ve model dosyalarını GitHub üzerinde yayınlama
Lisans
MIT License — İstediğiniz şekilde kullanabilirsiniz, atıf memnuniyetle karşılanır.
