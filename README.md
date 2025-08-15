# RT-DETR + Re-ID Ekran Takip Sistemi

Bu proje, **RT-DETR** nesne tespit modeli ve **ByteTrack** takip algoritmasını kullanarak ekran görüntüsü üzerinde **araç ve insan tespiti** yapar.  
Ayrıca geliştirilmiş bir **Re-ID (Tekrar Tanıma)** mekanizması ile aynı nesneleri farklı pozisyonlarda yeniden tanır.

## 🚀 Özellikler
- **RT-DETR** ile gerçek zamanlı nesne tespiti
- **ByteTrack** ile nesne takibi
- **Re-ID** ile tekrar tanıma (konum + görsel özellik)
- FPS, aktif ID sayısı ve galeri yönetimi
- Canlı ekran görüntüsü üzerinden çalışma

---

## 📋 Gereksinimler

### Donanım
- NVIDIA GPU (CUDA destekli) — RTX 2060+ önerilir
- Minimum 8 GB RAM (16 GB önerilir)
- Minimum 4 GB GPU Belleği

### Yazılım
- Python 3.9 – 3.11 (3.12 önerilmez)
- Windows / Linux (MacOS’ta sınırlı destek)
- CUDA Toolkit + cuDNN (GPU kullanımında gerekli)

---

## 🔧 Kurulum

### 1. Depoyu Klonla veya Dosyaları İndir
```bash
git clone https://github.com/kullanici_adi/rtdetr-reid.git
cd rtdetr-reid


2. Gerekli Kütüphaneleri Yükle

pip install torch torchvision torchaudio --index-url https://download.pytorch.org/whl/cu121
pip install opencv-python supervision mss numpy scikit-learn transformers

Çalıştırma

python rtdetr_reid.py


Çalıştırıldığında:

Canlı tespit ve takip ekranda gösterilir

Sol üstte FPS, ID sayısı ve aktif takip bilgisi bulunur

Konsolda tespit ve tekrar tanıma mesajları yazdırılır

⌨️ Klavye Kısayolları
Tuş	İşlev
q	Programı sonlandırır
g	Konsola mevcut kimlik galerisini yazar

⚠️ Olası Hatalar ve Çözümler
CUDA error veya Torch not compiled with CUDA

GPU sürücüsü veya CUDA Toolkit doğru kurulmamış olabilir

GPU yoksa kod CPU modunda çalışır ancak FPS düşer

ModuleNotFoundError

Eksik kütüphane varsa yüklemek için:

pip install paket_adi

Siyah ekran / boş pencere

mss yakalama alanı ekran çözünürlüğüyle uyuşmayabilir
→ Kod içinde:

"width": 1280,
"height": 720


değerlerini kendi çözünürlüğünüze göre ayarlayın.

📈 Performans İpuçları

Yakalama alanını küçültün (FPS artar)

GPU kullanın, CPU’da FPS çok düşük olur

istenen_etiketler listesini daraltın (ör. sadece "car")

📌 Konsol Çıktı Örneği
🆕 YENİ NESNE! Tracker:2 -> ID:1 car
🔄 TEKRAR TANIMLAMA! Tracker:4 -> ID:1 car (benzerlik: 0.82)
📊 MEVCUT KİMLİKLER (Toplam: 3):
🚗 Arabalar (2 tane):
   ID:1 - Son pozisyon: (0.45, 0.62)
🚶 İnsanlar (1 tane):
   ID:2 - Son pozisyon: (0.32, 0.48)
