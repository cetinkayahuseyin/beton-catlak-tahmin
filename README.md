# Beton Çatlak Tahmin

Bu proje, **Concrete Crack Images for Classification** veri setini kullanarak beton yüzeylerdeki çatlakların otomatik olarak tespit edilmesini amaçlamaktadır. Görüntü işleme ve derin öğrenme yöntemleri kullanılarak beton yüzeylerde çatlak olup olmadığı sınıflandırılmıştır.  

Repo, projenin teknik detaylarını, kullanılan yöntemleri, elde edilen sonuçları ve gelecekte yapılabilecek geliştirmeleri içermektedir.  

---

# Giriş

Günümüzde altyapı projelerinde beton, en sık kullanılan yapı malzemelerinden biridir. Zaman içinde beton yüzeylerde oluşan çatlakların tespiti, yapının güvenliği açısından kritik öneme sahiptir. Geleneksel yöntemlerle yapılan manuel incelemeler hem zaman alıcı hem de maliyetlidir.  

Bu proje, görüntü işleme ve derin öğrenme tekniklerini kullanarak beton yüzeylerde **çatlak tespitini otomatikleştirmeyi** hedeflemektedir.  
- Kullanılan veri seti: **Concrete Crack Images for Classification (Kaggle)**  
- Kullanılan yöntem: **CNN (Convolutional Neural Networks)** tabanlı sınıflandırıcı  
- Hedef: Beton yüzeyin çatlak veya sağlam olduğunu yüksek doğrulukla tahmin etmek  

Projenin teknik anlatımları, `notebooks/` klasöründe yer alan Jupyter notebook dosyalarında markdown hücreleriyle detaylandırılmıştır.  

---

# Veri Seti

- **Kaynak:** [Kaggle - Concrete Crack Images for Classification](https://www.kaggle.com/datasets/balraj98/concrete-crack-images-for-classification)  
- **Boyut:** Toplam 40.000 görüntü  
  - Çatlaklı (Positive): 20.000  
  - Çatlak olmayan (Negative): 20.000  
- **Özellikler:**  
  - Görseller gri tonlamalı, 227x227 piksel  
  - Dengeli sınıf dağılımı  
- **Kullanım:**  
  - Eğitim (train) ve test setlerine ayrıldı  
  - Görseller normalize edilerek CNN modeline verildi  

---

# Kullanılan Yöntemler

1. **Ön İşleme**  
   - Görseller yeniden boyutlandırıldı  
   - Normalizasyon uygulandı  
   - Eğitim / test ayrımı yapıldı  

2. **Modelleme**  
   - **Convolutional Neural Network (CNN)** mimarisi kullanıldı  
   - Katmanlar: Conv2D, MaxPooling2D, Flatten, Dense, Dropout  
   - Aktivasyon fonksiyonu: ReLU ve çıktı katmanında Softmax  

3. **Eğitim Parametreleri**  
   - Optimizasyon: Adam  
   - Kayıp fonksiyonu: Binary Cross-Entropy  
   - Epoch sayısı: 20  
   - Batch size: 32  

4. **Değerlendirme**  
   - Accuracy  
   - Loss  
   - Confusion Matrix  
   - Precision, Recall, F1-score  

---

# Metrikler

Eğitim sonucunda elde edilen performans:  

- **Training Accuracy:** %98  
- **Validation Accuracy:** %96  
- **Test Accuracy:** %95+  
- **Confusion Matrix:** Çatlak ve sağlam yüzeylerde yüksek ayırt edebilme başarısı  

Model, gerçek dünya senaryolarında beton yüzeylerde çatlakların hızlı ve güvenilir şekilde tespit edilebileceğini göstermektedir.  

---

# Sonuç ve Gelecek Çalışmalar

Bu proje, görüntü işleme ve derin öğrenme tekniklerinin inşaat mühendisliğinde **yapı sağlığı izleme (Structural Health Monitoring)** alanında kullanılabileceğini göstermektedir. Beton yüzeylerde çatlakların otomatik olarak tespit edilebilmesi, bakım-onarım süreçlerini hızlandırarak daha güvenli yapılar inşa edilmesine katkı sağlayabilir.  

**Çatlak türü sınıflandırma:** Mevcut model yalnızca çatlak/çatlak değil ayrımı yapmaktadır. Gelecekte model, **basınç çatlağı, çekme çatlağı, deprem çatlağı** gibi farklı çatlak türlerini ayırt edebilecek şekilde geliştirilebilir. Böylece kullanıcılar evlerinde oluşan çatlakların fotoğrafını çekerek sistemden **çatlağın türünü ve önem derecesini** öğrenebilir. Bu, hem mühendislik uygulamaları hem de günlük hayat için büyük kolaylık sağlayacaktır.  Özellikle hasarlı yapılarda hasar tespitinde büyük önem taşıyacaktır.

Gelecek çalışmalar için öne çıkan fikirler:  
- Daha gelişmiş CNN mimarileri (ResNet, EfficientNet) ile karşılaştırma yapılması  
- **Data Augmentation** yöntemleriyle modelin genelleştirme kabiliyetinin artırılması  
- Gerçek zamanlı kamera sistemleriyle entegrasyon  
- Mobil uygulama veya web arayüzü üzerinden modelin deploy edilmesi  

---

# Linkler

- [Kaggle Dataset](https://www.kaggle.com/datasets/arnavr10880/concrete-crack-images-for-classification)  
- [Kaggle Notebook](https://www.kaggle.com/code/huseyincetinkaya/beton-catlak-tahmin)

