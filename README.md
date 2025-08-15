# Gerçek Zamanlı Nesne Algılama ve Yeniden Tanımlama (RT-DETR & Re-ID)

Bu depo, RT-DETR modelini kullanarak gerçek zamanlı nesne algılama ve takibi (tracking) yapan, aynı zamanda nesnelerin yeniden tanımlanmasını (Re-ID) sağlayan Python betikleri içermektedir. Proje, video akışında veya bir görüntüde belirli nesneleri (araba ve insan) tespit edip takip ederken, aynı zamanda bu nesnelerin kimliklerini korumayı amaçlar.

## 🚀 Özellikler
- **Gerçek Zamanlı Tespit:** `transformers` kütüphanesi üzerinden RT-DETR modeli ile nesneleri hızla algılama.
- **Nesne Takibi:** `supervision` kütüphanesi ile algılanan nesneleri takip etme.
- **Yeniden Tanımlama (Re-ID):** Farklı Re-ID modelleri kullanarak (örneğin `torchreid` veya histogram tabanlı yöntemler) aynı nesnelerin farklı karelerde bile tek bir kimliğe sahip olmasını sağlama.
- **Çeşitli Kullanım Senaryoları:**
  - `rtdetr_inference.py`: Tek bir görüntü dosyası üzerinde nesne algılama.
  - `rtdetr_interface_video.py`: Gerçek zamanlı ekran akışı üzerinde nesne algılama ve takip.
  - `de_id_rt-detr_video_v*.py`: Gelişmiş yeniden tanımlama ve takip algoritmaları ile nesne kimliğini koruma.

## ⚙️ Kurulum
Proje, PyTorch ve çeşitli Python kütüphanelerini kullanmaktadır. Sanal bir ortamda kurulum yapmanız tavsiye edilir.

### 🔧 Bağımlılıklar
Aşağıdaki komut ile gerekli kütüphaneleri yükleyebilirsiniz:

pip install torch transformers supervision opencv-python mss scikit-learn numpy pillow torchreid

1. Tek Bir Görüntü Üzerinde Nesne Algılama
python rtdetr_inference.py
Bu betik, kullanıcıdan bir görüntü dosyası seçmesini ister ve o görüntüdeki nesneleri tespit edip etiketler.

2. Gerçek Zamanlı Ekran Kaydı ile Nesne Takibi

python rtdetr_interface_video.py
Bu betik, ekranınızın belirli bir alanını yakalar ve gerçek zamanlı olarak nesneleri algılayıp takip eder.

3. Gerçek Zamanlı Yeniden Tanımlama (Re-ID)

python de_id_rt-detr_video_v4.py
Bu betik, algılanan nesnelere kalıcı kimlikler atar. Çıkmak için 'q' tuşuna basın.
