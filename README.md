# 🛒 E-Ticaret Veri Seti Detaylı İnceleme ve Veri Analizi

![Python](https://img.shields.io/badge/Python-3.9+-3776AB?style=for-the-badge&logo=python&logoColor=white)
![Pandas](https://img.shields.io/badge/Pandas-Data%20Analysis-150458?style=for-the-badge&logo=pandas&logoColor=white)
![Seaborn](https://img.shields.io/badge/Seaborn-Data%20Visualization-3776AB?style=for-the-badge)
![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-F37626?style=for-the-badge&logo=jupyter&logoColor=white)
![Status](https://img.shields.io/badge/Status-Completed-success?style=for-the-badge)

Bu proje, bir e-ticaret platformuna ait ham sipariş verilerinin **uçtan uca Veri Bilimi (Data Science) ve Keşifsel Veri Analizi (EDA - Exploratory Data Analysis)** süreçlerinden geçirilerek temizlenmesi, işlenmesi, görselleştirilmesi ve stratejik iş kararlarına dönüştürülmesini kapsamaktadır.

---

## 📌 Proje Özeti ve Amaçlar

E-ticaret sektöründe veriye dayalı karar alma süreçleri; müşteri segmentasyonu, gelir optimizasyonu, iade oranlarının düşürülmesi ve stok yönetimi açısından hayati önem taşır. Bu çalışmada **1.428 sipariş kaydı** ve **18 farklı öznitelik** içeren e-ticaret veri seti detaylı bir şekilde analiz edilmiştir.

### Main Objectives:
1. **Veri Kalitesini Artırma:** Eksik veri, aykırı değer (outlier) ve tekrarlayan kayıtların tespiti ve temizlenmesi.
2. **Kullanıcı & Satış Analizi:** Şehir, bölge, ürün kategorisi, müşteri tipi ve ödeme yöntemlerine göre satış performansının incelenmesi.
3. **Zaman Serisi & Dönemsellik:** Siparişlerin aylık, haftalık ve haftanın günlerine göre yoğunluk analizi.
4. **İş Hikayeleştirme (Business Storytelling):** Yüksek gelir üreten ve müşteri memnuniyeti sağlayan stratejik ürün-şehir kombinasyonlarının belirlenmesi.

---

## 📊 Veri Seti Mimarisi

Veri seti `e_ticaret_veri_seti.csv` dosyası içerisinde yer almakta olup aşağıdaki öznitelikleri barındırmaktadır:

| Sütun Adı | Veri Tipi | Açıklama |
| :--- | :--- | :--- |
| `siparis_id` | Object / String | Benzersiz sipariş kimlik numarası |
| `musteri_id` | Object / String | Benzersiz müşteri kimlik numarası |
| `siparis_tarihi` | Datetime | Siparişin gerçekleştiği tarih ve saat |
| `sehir` | Categorical | Siparişin teslim edildiği şehir (İstanbul, Ankara vb.) |
| `bolge` | Categorical | Şehrin bulunduğu coğrafi bölge |
| `kategori` | Categorical | Ürün kategorisi (Kozmetik, Spor, Kitap, Elektronik vb.) |
| `urun_adi` | Object / String | Satın alınan ürün adı |
| `adet` | Integer | Sipariş edilen ürün adedi |
| `birim_fiyat` | Float | Ürünün birim fiyatı (TL) |
| `indirim_orani` | Float | Siparişe uygulanan indirim oranı (%0 - %100) |
| `kargo_ucreti` | Float | Sipariş kargo ücreti |
| `odeme_turu` | Categorical | Ödeme yöntemi (Kredi Kartı, Banka Kartı, Kapıda Ödeme, EFT) |
| `musteri_tipi` | Categorical | Müşteri segmenti (Yeni, Mevcut, VIP) |
| `teslimat_gunu` | Float / Int | Sipariş teslimat süresi (gün) |
| `musteri_puani` | Float | Sipariş sonrası müşteri değerlendirme puanı (1 - 5) |
| `iade_durumu` | Categorical | Siparişin iade edilip edilmediği (Evet / Hayır) |
| `kar_marji_orani` | Float | Ürün veya siparişteki kâr marjı oranı |
| `toplam_tutar` | Float | Siparişin net toplam tutarı (TL) |

---

## 🛠️ Analiz ve Uygulama Adımları

Çalışma `Eticaret.ipynb` notebook'u içerisinde **14 ana başlık** altında adım adım yürütülmüştür:

```
├── 1. Veri Setini Tanıma (EDA & Genel Profil)
├── 2. Kayıp Veri (Missing Value) Tespiti ve İmpütasyon
├── 3. Veri Tipi Dönüşümleri (Datetime & Categorical Optimization)
├── 4. Tekrarlayan ve Tutarsız Kayıtlar (Deduplication)
├── 5. Aykırı Değer Analizi (IQR Yöntemi & Outlier Handling)
├── 6. Kategorik Veri Analizi
├── 7. Sayısal Veri Analizi
├── 8. Grup Bazlı Analiz (GroupBy Aggregations)
├── 9. Pivot Tablo Analizi (Cross-tabulation)
├── 10. Veri Görselleştirme (Seaborn & Matplotlib)
├── 11. Zaman Serisi Analizi (Time Series Dynamics)
├── 12. Değişkenler Arası İlişkiler (Correlation & Heatmap)
└── 13. Veri Hikayeleştirme ve İş Yorumu (Business Insights)
```

---

## 📈 Öne Çıkan Bulgular ve İş Çıkarımları

1. **Yüksek Gelir ve Müşteri Memnuniyeti:**
   - Gelir üretimi yüksek olan kategorilerde müşteri memnuniyet puanlarının (Müşteri Puanı) tutarlılığı incelenmiştir.
2. **Ödeme Türü Performansı:**
   - Kredi Kartı ve Banka Kartı ile yapılan alışverişlerin ortalama sipariş tutarının, Kapıda Ödeme yöntemine göre önemli ölçüde yüksek olduğu gözlemlenmiştir.
3. **Şehir & Kategori Fırsatları:**
   - Büyükşehirlerde (İstanbul, Ankara, İzmir) belirli kategorilere yönelim yüksekken, gelişmekte olan şehirlerde farklı ürün gruplarında potansiyel fırsatlar tespit edilmiştir.
4. **Zaman Serisi Trendleri:**
   - Ayın ilk yarısı ile ikinci yarısı arasındaki harcama alışkanlıkları ve hafta sonı sipariş yoğunlukları analiz edilmiştir.

---

## 💻 Kullanılan Teknolojiler ve Kütüphaneler

- **Programlama Dili:** Python 3.9+
- **Veri Manipülasyonu:** `pandas`, `numpy`
- **Veri Görselleştirme:** `matplotlib`, `seaborn`
- **Geliştirme Ortamı:** Jupyter Notebook (`.ipynb`)

---

## 🚀 Kurulum ve Çalıştırma

Projeyi yerel bilgisayarınızda çalıştırmak için aşağıdaki adımları takip edebilirsiniz:

1. **Depoyu Klonlayın:**
   ```bash
   git clone https://github.com/52BaranHaydar/E-Ticaret-Veri-Seti-Analizi.git
   cd E-Ticaret-Veri-Seti-Analizi
   ```

2. **Gerekli Kütüphaneleri Yükleyin:**
   ```bash
   pip install pandas numpy matplotlib seaborn jupyter
   ```

3. **Jupyter Notebook'u Başlatın:**
   ```bash
   jupyter notebook Eticaret.ipynb
   ```

---

## 👤 Yazar

- **Baran Haydar**
- **GitHub:** [@52BaranHaydar](https://github.com/52BaranHaydar)
