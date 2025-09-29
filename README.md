Felç Riski Tahmini (Stroke Risk Prediction)
Bu proje, çeşitli sağlık ve demografik verilere dayanarak bir bireyin felç geçirme olasılığını tahmin etmeyi amaçlamaktadır. Bu sınıflandırma görevi için bir Lojistik Regresyon modeli oluşturulmuş, değerlendirilmiş ve optimize edilmiştir.

Projeye Genel Bakış
Proje, bir dizi adımdan oluşmaktadır:

Veri Yükleme ve Keşfi: Gerekli kütüphaneler içe aktarılır ve veri seti yüklenir.

Veri Ön İşleme: Modelin anlayabileceği formata getirmek için kategorik değişkenler sayısal değerlere dönüştürülür.

Model Eğitimi: Veri seti, eğitim ve test olmak üzere ikiye ayrılır ve Lojistik Regresyon modeli eğitilir.

Model Değerlendirme: Modelin performansı, test verileri üzerinde doğruluk (accuracy), sınıflandırma raporu (classification report) ve karmaşıklık matrisi (confusion matrix) gibi metriklerle ölçülür.

Hiperparametre Optimizasyonu: Modelin performansını artırmak için GridSearchCV tekniği ile en iyi hiperparametreler bulunur.

Kullanılan Veri Seti
Bu projede, felç riskini tahmin etmek için sentetik olarak oluşturulmuş bir veri seti kullanılmıştır. Veri seti aşağıdaki gibi özellikler içermektedir:

gender: Cinsiyet

age: Yaş

hypertension: Hipertansiyon durumu

heart_disease: Kalp hastalığı durumu

ever_married: Evlilik durumu

work_type: Çalışma türü

Residence_type: İkametgah türü

avg_glucose_level: Ortalama glukoz seviyesi

bmi: Vücut Kitle İndeksi (VKİ)

smoking_status: Sigara içme durumu

stroke: Felç durumu (Hedef Değişken: 1 = Felç, 0 = Felç Değil)

Metodoloji
Veri Ön İşleme:

gender, ever_married, work_type, Residence_type, ve smoking_status gibi kategorik sütunlar, pd.get_dummies fonksiyonu kullanılarak "One-Hot Encoding" yöntemiyle sayısal verilere dönüştürülmüştür.

Verinin Bölünmesi:

Veri seti, %70 eğitim ve %30 test verisi olacak şekilde ayrılmıştır.

Modelin Eğitimi ve Değerlendirilmesi:

Bir Lojistik Regresyon modeli oluşturulmuş ve eğitim verileriyle eğitilmiştir.

Modelin test verileri üzerindeki performansı değerlendirilmiştir.

Hiperparametre Optimizasyonu:

Model performansını iyileştirmek için GridSearchCV kullanılmıştır. penalty, C (Regülarizasyon parametresi) ve solver gibi parametreler için en uygun kombinasyon aranmıştır.

Çapraz doğrulama (cross-validation) için StratifiedKFold (5 katmanlı) tekniği tercih edilmiştir.

Sonuçlar
İlk Model Performansı: Hiperparametre optimizasyonu yapılmadan önce eğitilen Lojistik Regresyon modeli, test verileri üzerinde yaklaşık %79 doğruluk (accuracy) skoruna ulaşmıştır.

Hiperparametre Optimizasyonu Sonuçları: GridSearchCV ile bulunan en iyi parametreler şunlardır:

C: 0.01

penalty: 'l2'

solver: 'lbfgs'

En İyi Çapraz Doğrulama Skoru: Grid search sırasında elde edilen en iyi çapraz doğrulama (cross-validation) doğruluk skoru yaklaşık %76 olarak bulunmuştur.
