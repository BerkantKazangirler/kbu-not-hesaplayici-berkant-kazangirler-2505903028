# KBÜ Not Hesaplama Sistemi

## Proje Açıklaması

Bu proje, Karabük Üniversitesi'nin (KBÜ) akademik not hesaplama kurallarına göre öğrenci başarı notunu hesaplayan interaktif bir web uygulamasıdır. HTML, CSS ve JavaScript kullanılarak geliştirilmiş olup, öğrencilerin vize, yıl içi çalışma puanı, final veya bütünleme notlarını girerek dönem sonu başarı durumlarını öğrenmelerini sağlar.

Uygulama, kullanıcı dostu bir arayüze sahiptir ve gerçek zamanlı form validasyonu, dinamik görünüm değişiklikleri ve kapsamlı hata kontrolleri içerir.

---

## KBÜ Kurallarına Göre Hesap Mantığı

### Yıl İçi Notu Hesaplama

Yıl içi notu, öğrencinin vize sınavı ve diğer yıl içi çalışmalarının değerlendirmesidir. Eğer yıl içi çalışma puanı ayrıca girilmemişse, vize notu doğrudan yıl içi notu olarak kabul edilir. Bu esneklik, farklı ders yapılandırmalarına uyum sağlar.

### Başarı Notu Hesaplama

Başarı notu, öğrencinin yıl içi performansı ve dönem sonu sınavının ağırlıklı ortalaması ile hesaplanır:

**Başarı Notu = (Yıl İçi Notu × 0.4) + (Dönem Sonu Sınavı × 0.6)**

- **Yıl İçi Notu:** Yıl içi çalışma puanı girilmişse o değer, girilmemişse vize notu kullanılır.
- **Dönem Sonu Sınavı:** Final notu veya bütünleme notu (hangisi girilmişse).
- **Bütünleme Önceliği:** Öğrenci hem final hem bütünleme notunu girmişse, bütünleme notu dönem sonu sınavı olarak kullanılır.

### Başarı ve Harf Notu Kriterleri

Hesaplanan başarı notuna göre harf notu ve geçme durumu belirlenir:

| Başarı Notu Aralığı | Harf Notu | Katsayı | Durum |
| ------------------- | --------- | ------- | ----- |
| 90 - 100            | A1        | 4.00    | Geçti |
| 80 - 89             | A2        | 3.50    | Geçti |
| 70 - 79             | B1        | 3.00    | Geçti |
| 65 - 69             | B2        | 2.75    | Geçti |
| 60 - 64             | C2        | 2.50    | Geçti |
| < 60                | F3        | 0.00    | Kaldı |

### Özel Durumlar

1. **F1 - Devamsızlık:** Öğrenci devam şartını sağlayamamışsa (minimum %70 devam zorunluluğu), otomatik olarak F1 notu alır ve dersten kalır.

2. **F2 - Sınava Girmeme:** Öğrenci genel veya bütünleme sınavına girmemişse F2 notu alır ve dersten kalır.

3. **F3 - Başarısızlık:** Aşağıdaki durumlardan biri gerçekleşirse öğrenci F3 notu alır:
   - Final/Bütünleme sınavı notu 50'nin altındaysa
   - Başarı notu 60'ın altındaysa

---

## Kullanım Talimatı

### Projeyi Çalıştırma

1. **Dosyaları İndirin/Klonlayın:**

   ```bash
   git clone https://github.com/BerkantKazangirler/kbu-projects.git
   cd kbu-not-hesaplayici-berkant-kazangirler-2505903028
   ```

2. **Tarayıcıda Açın:**

   - `index.html` dosyasını çift tıklayarak herhangi bir web tarayıcısında açın.
   - Veya Live Server gibi bir geliştirme sunucusu kullanın:
     ```bash
     # VS Code'da Live Server extension ile
     # Sağ tık -> Open with Live Server
     ```

3. **Alternatif Yöntem:**
   - Dosya yolunu doğrudan tarayıcının adres çubuğuna kopyalayıp yapıştırın.

### Not Hesaplama Adımları

1. **Vize Notu:** Vize sınav notunuzu girin (0-100 arası, **zorunlu**).

2. **Yıl İçi Çalışma Puanı (Opsiyonel):**

   - Tüm yıl içi çalışmalarınızın (ödevler, projeler, lab çalışmaları vb.) ortalamasını girin.
   - **Boş bırakılırsa:** Vize notu otomatik olarak yıl içi notu olarak kullanılır.

3. **Final Notu:** Final sınav notunuzu girin (bütünleme sınavına girmeyecekseniz **zorunlu**).

4. **Bütünleme Notu (Opsiyonel):**

   - Bütünleme sınavına girdiyseniz bu alana notunuzu girin.
   - Bütünleme notu girildiğinde, final notu alanı otomatik olarak gizlenir.
   - Bütünleme notunu sildiğinizde, final notu alanı tekrar görünür.

5. **Devam Durumu:** Dersin devam şartını sağladıysanız işaretleyin (%70 ve üzeri).

6. **Sınava Girme Durumu:** Genel veya bütünleme sınavına girdiyseniz işaretleyin.

7. **Hesapla:** "Notu Hesapla" butonuna tıklayın veya Enter tuşuna basın.

8. **Sonuçları Görüntüleyin:**

   - Başarı notunuz
   - Harf notunuz ve katsayınız
   - Geçme durumunuz (Geçti/Kaldı)
   - Açıklama mesajı

9. **Sıfırla:** Tüm alanları temizlemek için "Sıfırla / Temizle" butonuna tıklayın.

---

## Dosya Yapısı

```
kbu-not-hesaplayici-berkant-kazangirler-2505903028/
│
├── index.html       # Ana HTML sayfası (form ve yapı)
├── script.js        # JavaScript mantığı (hesaplama fonksiyonları)
├── style.css        # CSS stilleri (görünüm ve tasarım)
└── README.md        # Proje dokümantasyonu (GitHub Copilot tarafından oluşturuldu)
```

---

## Teknik Detaylar

### Kullanılan Teknolojiler

- **HTML5:** Semantic yapı ve form elemanları
- **CSS3:** Modern styling, flexbox layout, responsive design
- **JavaScript (ES6):** DOM manipülasyonu, event handling, hesaplamalar

### Önemli Fonksiyonlar

1. **`hesapla()`**

   - Ana hesaplama fonksiyonu
   - Not girişlerini alır ve başarı notunu hesaplar
   - Harf notunu ve durum bilgisini belirler
   - Sonuçları ekrana yazdırır

2. **`butunlemeKontrol()`**

   - Bütünleme alanı doldurulduğunda final alanını gizler
   - Bütünleme alanı boşaltıldığında final alanını gösterir
   - `oninput` event'i ile gerçek zamanlı çalışır

3. **`resetForm()`**

   - Tüm form alanlarını temizler
   - Değişkenleri sıfırlar
   - Sonuç ekranını gizler

4. **`sonucGizle()`**
   - Sonuç paragraflarını gizler
   - Hata durumlarında kullanılır

---
