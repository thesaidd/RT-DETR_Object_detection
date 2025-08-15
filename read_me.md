**Gerçek** **Zamanlı** **Nesne** **Algılama** **ve** **Yeniden**
**Tanımlama** **(RT-DETR** **&** **Re-ID)**

Bu depo, RT-DETR modelini kullanarak gerçek zamanlı nesne algılama ve
takibi (tracking) yapan, aynı zamanda nesnelerin yeniden tanımlanmasını
(Re-ID) sağlayan Python betikleri içermektedir. Proje, video akışında
veya bir görüntüde belirli nesneleri (araba ve insan) tespit edip takip
ederken, aynı zamanda bu nesnelerin kimliklerini korumayı amaçlar.

**Özellikler**

> ● **Gerçek** **Zamanlı** **Tespit:** transformers kütüphanesi
> üzerinden RT-DETR modeli ile nesneleri hızla algılama.
>
> ● **Nesne** **Takibi:** supervision kütüphanesi ile algılanan
> nesneleri takip etme.
>
> ● **Yeniden** **Tanımlama** **(Re-ID):** Farklı Re-ID modelleri
> kullanarak (örneğin torchreid veya basit histogram tabanlı yöntemler)
> aynı nesnelerin farklı karelerde bile tek bir kimliğe sahip olmasını
> sağlama.
>
> ● **Çeşitli** **Kullanım** **Senaryoları:**
>
> ○ rtdetr_inference.py: Tek bir görüntü dosyası üzerinde nesne
> algılama.
>
> ○ rtdetr_interface_video.py: Gerçek zamanlı ekran akışı üzerinde nesne
> algılama ve takip.
>
> ○ de_id_rt-detr_video_v\*.py: Gelişmiş yeniden tanımlama ve takip
> algoritmaları ile nesne kimliğini koruma.

**Kurulum**

Proje, PyTorch ve diğer çeşitli Python kütüphanelerini kullanmaktadır.
Sanal bir ortamda kurulum yapmanız tavsiye edilir.

**Bağımlılıklar**

Gerekli tüm kütüphaneleri yüklemek için aşağıdaki komutları kullanın:

pip install torch transformers supervision opencv-python mss
scikit-learn numpy pillow torchreid

**Not:** torchreid kurulumu için ek gereksinimler olabilir, lütfen resmi
belgeleri kontrol edin.

**Kullanım**

Aşağıda, her bir betiğin nasıl kullanılacağına dair kısa bir rehber
bulunmaktadır.

**1.** **Tek** **Bir** **Görüntü** **Üzerinde** **Nesne** **Algılama**

rtdetr_inference.py betiği, kullanıcıdan bir görüntü dosyası seçmesini
ister ve o görüntüdeki nesneleri tespit edip etiketler.

python rtdetr_inference.py

**2.** **Gerçek** **Zamanlı** **Ekran** **Kaydı** **ile** **Nesne**
**Takibi**

rtdetr_interface_video.py betiği, ekranınızın belirli bir alanını
yakalar ve gerçek zamanlı olarak nesneleri algılayıp takip eder.

python rtdetr_interface_video.py

**3.** **Gerçek** **Zamanlı** **Ekran** **Kaydı** **ile** **Yeniden**
**Tanımlama** **(Re-ID)**

de_id_rt-detr_video_v\*.py dosyaları, daha gelişmiş Re-ID algoritmaları
içerir. En son versiyon olan de_id_rt-detr_video_v4.py dosyasını
kullanmanız önerilir. Bu betik, algılanan nesnelere kalıcı kimlikler
atar.

python de_id_rt-detr_video_v4.py

> ● Çıkmak için **'q'** tuşuna basın.

**Katkıda** **Bulunma**

Geliştirmelere katkıda bulunmaktan çekinmeyin. Bir hata bulursanız veya
bir özellik eklemek isterseniz, lütfen bir issue oluşturun veya bir pull
request gönderin.

**Lisans**

Bu proje MIT Lisansı altında yayımlanmıştır.
