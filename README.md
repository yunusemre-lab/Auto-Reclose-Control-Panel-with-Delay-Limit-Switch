# Zaman Gecikmeli ve Sınır Anahtarlı İleri-Geri Otomatik Kumanda Panosu

Bu depo, endüstriyel otomasyon sistemlerinde sıkça kullanılan **Zaman Gecikmeli İleri-Geri Asenkron Motor / Dahlander Sürücü Kumanda Devresi**'nin QElectroTech şemasını, simülasyon aşamalarını ve profesyonel pafta çıktısını barındırır.

---

## 🚀 Proje Hakkında
Bu proje; motorun ileri ve geri yönlerde güvenli çalışmasını, ters yön geçişlerinde zaman rölesi ile gecikme sağlanmasını, mekanik/elektriksel kilitlemeleri ve limit switch (`LS1`, `LS2`) otomasyonunu endüstriyel standartlara uygun olarak simüle etmek ve belgelendirmek amacıyla geliştirilmiştir.

---

## ⚙️ Çalışma Mantığı ve Adım Adım Çalışma Senaryosu

1. **Başlatma (İleri Yön Çalışma):**
   * Operatör `START` butonuna bastığında **`İLERİ`** kontaktörü enerjilenir ve mühürlenir. Motor ileri yönde dönmeye başlar.
   * `İLERİ` kontaktörünün kapalı kontağı, `GERİ` hattını keserek iki yönün aynı anda devreye girmesini önler (**Elektriksel Kilitleme**).

2. **Birinci Sınır Konumu ve Zaman Gecikmesi (`LS1` Tetiklenmesi):**
   * Hareket eden sistem birinci sınır anahtarına (`LS1`) ulaştığında `LS1` açılır, `İLERİ` kontaktörünün enerjisi kesilir ve motor durur.
   * Aynı anda yardım kontakları üzerinden **`ZR1` / `V` Zaman Rölesi** devreye girer ve ayarlanan bekleme süresini (örn. 5 saniye) saymaya başlar.
   * Bu bekleme süresi, motorun mekanik ve elektriksel ataletinin sıfırlanmasını (durmasını) sağlayarak ani ters akım darbelerini önler.

3. **Geri Yön Otomatik Başlatma:**
   * Zaman rölesi ayarlanan süreyi tamamladığında kapanan kontağı üzerinden **`GERİ`** kontaktörünü otomatik olarak tetikler.
   * Motor geri yönde dönmeye başlar.

4. **İkinci Sınır Konumu ve Sistemi Durdurma (`LS2` Tetiklenmesi):**
   * Sistem geri yönde ilerleyip ikinci sınır anahtarına (`LS2`) ulaştığında `LS2` açılır.
   * `GERİ` kontaktörünün enerjisi kesilir ve sistem bir sonraki kumanda emrine kadar tamamen güvenli şekilde durur.

5. **Güvenlik ve Koruma Elemanları:**
   * Herhangi bir aşırı yük veya sıkışma durumunda termik aşırı akım röleleri (`FR1`, `FR2`) kumanda devresini keser (95/96 kontakları).
   * Acil bir durumda `ACİL STOP` veya `STOP` butonlarına basılarak tüm sistem anında durdurulabilir.

---

## 🛠️ Kullanılan Bileşenler ve Donanım
* **Güç Devresi Elemanları:**
  * 3 Fazlı Ana Devre Kesici (3P Miniature Circuit Breaker / C10)
  * İleri ve Geri Güç Kontaktörleri
  * Kontaktör altı montajlı Termik Aşırı Akım Röleleri (`FR1`, `FR2`)
  * 3 Fazlı Asenkron / Dahlander Motor Bloğu
* **Kumanda Devresi Elemanları:**
  * Tek Kutuplu / Çift Kutuplu Kumanda Koruma Sigortası (1P MCB / C6)
  * Acil Durum Stop Butonu (NC)
  * Standart Stop Butonu ve Start Butonu
  * Sınır Anahtarları (`LS1`, `LS2`)
  * Zaman Rölesi (`V` / `ZR1`)
  * İleri ve Geri Yardımcı Kumanda Kontaktörleri

---

## 📐 Teknik Özellikler ve Tasarım Kriterleri
* **Güvenlik Interlock Mimarisi:** İleri ve geri kontaktörleri arasında elektriksel kilitleme (interlock) sağlanarak aynı anda devreye girmeleri engellenmiştir.
* **Zaman Gecikmesi:** Geçiş süreçlerinde sistem kararlılığını korumak için entegre zaman rölesi mantığı eklenmiştir.
* **Pafta Standardı:** QElectroTech ile endüstriyel IEC standartlarına uygun koordinatlı çizim, antet (title block) ve PDF export entegrasyonu sağlanmıştır.

---

## 📂 Dosya Yapısı
* `Ileri_Geri_Kumanda.qet` — QElectroTech kaynak proje dosyası (Düzenlenebilir).
* `Ileri_Geri_Kumanda_Semasi.pdf` — Profesyonel PDF pafta çıktısı.

---

## 📊 Görsel Simülasyon ve Devre Şemaları

### 🎥 Otomasyon Panel Simülasyonu
<p align="center">
  <img width="100%" alt="Paneli Simülasyonu" src="https://github.com/user-attachments/assets/803f4370-9dff-41ac-980e-ad0e03e8210a" />
</p>

---

### ⚡ QElectroTech Devre Şemaları & Pafta Çıktısı

<img width="1676" height="885" alt="Screenshot_1" src="https://github.com/user-attachments/assets/b9ebb258-1bf4-45b3-927a-2a439545d771" />
<img width="1677" height="616" alt="Screenshot_2" src="https://github.com/user-attachments/assets/a25f0589-d752-4c95-8f82-8632a90fc04a" />
<img width="1676" height="417" alt="Screenshot_3" src="https://github.com/user-attachments/assets/3dafd151-c4a6-4a79-999d-7523839f5eff" />
<img width="984" height="701" alt="image" src="https://github.com/user-attachments/assets/ee0432c1-e447-42a4-8ba8-38bca0658863" />
