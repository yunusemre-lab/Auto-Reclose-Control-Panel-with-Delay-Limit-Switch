# Zaman Gecikmeli ve Sınır Anahtarlı İleri-Geri Otomatik Kumanda Panosu

Bu depo, endüstriyel otomasyon sistemlerinde sıkça kullanılan **Zaman Gecikmeli İleri-Geri Asenkron Motor / Dahlander Sürücü Kumanda Devresi**'nin QElectroTech şemasını, simülasyon aşamalarını ve profesyonel pafta çıktısını barındırır.

---

## 🚀 Proje Hakkında
Bu proje; motorun ileri ve geri yönlerde güvenli çalışmasını, ters yön geçişlerinde zaman rölesi ile gecikme sağlanmasını, mekanik/elektriksel kilitlemeleri ve limit switch (`LS1`, `LS2`) otomasyonunu endüstriyel standartlara uygun olarak simüle etmek ve belgelendirmek amacıyla geliştirilmiştir.

---

## 🛠️ Kullanılan Bileşenler ve Donanım
* **Güç Devresi Elemanları:**
  * 3 Fazlı Ana Devre Kesici (3P Miniature Circuit Breaker / C10)
  * İleri ve Geri Güç Kontaktörleri
  * Kontaktör altı montajlı Termik Aşırı Akım Röleleri (`FR1`, `FR2`)
  * 3 Fazlı Asenkron / Dahlander Motor Bloğu
* **Kumanda Devresi Elemanları:**
  * Tek Kutuplu / Çift Kutuplu Kumanda Koruma Sigortası (1P MCB / C6)
  * Acil Durum Stop Butonu (NC - 95/96)
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

## 📊 Görsel Simülasyon ve Devre Şeması

<p align="center">
  <img width="800" alt="Simulasyon Görseli" src="https://github.com/user-attachments/assets/803f4370-9dff-41ac-980e-ad0e03e8210a" />
</p>

<img width="1676" height="885" alt="Screenshot_1" src="https://github.com/user-attachments/assets/b9ebb258-1bf4-45b3-927a-2a439545d771" />
<img width="1677" height="616" alt="Screenshot_2" src="https://github.com/user-attachments/assets/a25f0589-d752-4c95-8f82-8632a90fc04a" />
<img width="1676" height="417" alt="Screenshot_3" src="https://github.com/user-attachments/assets/3dafd151-c4a6-4a79-999d-7523839f5eff" />
<img width="984" height="701" alt="image" src="https://github.com/user-attachments/assets/ee0432c1-e447-42a4-8ba8-38bca0658863" />
