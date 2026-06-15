
## 📌 Proje Hakkında (About the Project)
Bu proje, Büyük Veri Analizi dersi kapsamında geliştirilmiş uçtan uca bir veri madenciliği ve Karar Destek Sistemi (KDS) çalışmasıdır. `Heart_Dataset_Cleaned.csv` veri seti kullanılarak; hastaların demografik, klinik ve yaşam tarzı alışkanlıkları incelenmiş ve henüz tanı konmamış bireylerin **Kardiyovasküler Hastalık (Kalp Hastalığı)** riskini önceden tespit edebilen makine öğrenmesi modelleri geliştirilmiştir.

Proje, geleneksel "reaktif" tıp anlayışını veriye dayalı "proaktif" (önleyici) bir sağlık yönetimi modeline dönüştürmeyi hedefleyen bir İş Zekası (Business Intelligence) prototipidir.

---

## 📊 Veri Seti Özeti (Dataset Overview)
* **Gözlem Sayısı:** 328 Hasta (Satır)
* **Değişken Sayısı:** 21 Özellik (Sütun)
* **Hedef Değişken (Target):** `Heart patient` (Sınıf Dengesizliği: %67 Sağlıklı, %33 Hasta)
* **Veri Kalitesi:** Temizlenmiş veri seti (Eksik değer veya mükerrer kayıt bulunmamaktadır).

Kullanılan temel değişkenler arasında; *Yaş, Cinsiyet, Vücut Kitle İndeksi (BMI), Kan Basıncı (Hipertansiyon), Diyabet, Fiziksel Aktivite Sıklığı, Stres Düzeyi, Sigara/Alkol Kullanımı ve Aile Öyküsü* yer almaktadır.

---

## 🛠️ Kullanılan Metodolojiler (Methodologies)
Proje, standart bir veri bilimi yaşam döngüsüne (Data Science Lifecycle) sadık kalınarak geliştirilmiştir:
1. **Keşifsel Veri Analizi (EDA):** Veri dağılımlarının, aykırı değerlerin (outliers) ve hedef değişkenle olan non-lineer korelasyonların tespiti.
2. **Veri Ön İşleme (Data Preprocessing):** Kategorik verilerin sayısallaştırılması (Label Encoding), veri ölçeklendirme (StandardScaler) ve tabakalı ayırma (Stratified Train/Test Split - 80/20).
3. **Makine Öğrenmesi (Machine Learning):** Üç farklı sınıflandırma algoritmasının eğitimi:
   * Lojistik Regresyon (Logistic Regression)
   * Karar Ağacı (Decision Tree)
   * Rastgele Orman (Random Forest)

---

## 📈 Ana Bulgular ve Model Performansı (Key Findings)

### Keşifsel Analiz Bulguları:
* **Fiziksel Riskler:** BMI değeri 30+ (Obezite) olan ve Hipertansiyon kategorisinde yer alan bireylerde hastalık riski logaritmik olarak artmaktadır.
* **Yaşam Tarzı Etkisi:** Haftada 5 gün ve üzeri kardiyo egzersizi yapan grupta hastalık riski istatistiksel olarak sıfıra yaklaşırken; düzenli sigara kullanımı ve kronik stres, hastalık tetikleyicisi olarak saptanmıştır.

### Makine Öğrenmesi Sonuçları:
Sınıfları birbirinden ayırma gücü (ROC-AUC) metriklerine göre modeller kıyaslandığında;
* 🏆 **En Başarılı Model:** `Random Forest` (AUC: **0.822**)
* **Karar Ağacı (Decision Tree):** AUC: 0.715
* **Lojistik Regresyon:** AUC: 0.782

**Değişken Önemi (Feature Importance):** Random Forest modeline göre hastalık riskini belirleyen en kritik 4 değişken sırasıyla; **BMI, Boy, Kilo ve Kan Basıncı** olarak tespit edilmiştir. Model
