# Plaka Tanıma Sistemi (OCR)

## Genel Bakış
Bu proje, araç plakalarındaki karakterleri algılamak ve tanımak için bir optik karakter tanıma (OCR) sistemi geliştirmeyi amaçlar. Proje, plakaların görüntülerini işlemek, karakterleri tespit etmek ve bu karakterleri metne dönüştürmek için Python tabanlı kütüphaneler kullanır. Google Colab üzerinde GPU desteği ile çalıştırılmıştır.

## Veri Seti
Veri seti, Google Drive'da aşağıdaki dizinlerde saklanmaktadır:
- **Görüntüler**: `/content/drive/MyDrive/Plate_System_trOCR/OCR_LP/LP-characters/images`
- **Anotasyonlar**: `/content/drive/MyDrive/Plate_System_trOCR/OCR_LP/LP-characters/annotations`

Her plaka görüntüsü için bir XML anotasyon dosyası bulunur ve bu dosyalar plaka üzerindeki karakterleri tanımlar.

## Özellikler
- **Veri Ön İşleme**: Görüntüler OpenCV ve PIL ile yüklenir, yeniden boyutlandırılır ve "letterbox" veya "crop" modlarıyla işlenir.
- **Karakter Algılama**: XML anotasyon dosyalarından plaka metinleri çıkarılır ve YOLO formatındaki koordinatlar mutlak piksel değerlerine dönüştürülür.
- **Sonuç Çıkarma**: İşlenen veriler bir CSV dosyasına (`lic_labels1.csv`) kaydedilir ve analiz edilir.
- **Performans Değerlendirmesi**: Test verileri üzerinde doğru karakter ve kelime tahmin oranları hesaplanır.

## Gereksinimler
Projeyi çalıştırmak için aşağıdaki kütüphanelerin yüklü olması gerekmektedir:
```bash
pip install numpy pandas matplotlib opencv-python pillow beautifulsoup4 datasets jiwer
```

## Proje Yapısı
* Kurulum: Gerekli kütüphaneler Colab ortamında yüklenir (datasets, jiwer).
* Dizin Oluşturma: Çıktılar /content/output dizinine kaydedilir.
* Veri İşleme: Görüntü ve anotasyon dosyaları eşleştirilerek bir veri çerçevesine dönüştürülür.
* Görüntü Ön İşleme: preprocess fonksiyonu ile görüntüler hedef boyuta (örn. width, height) uyarlanır.
* Karakter Tanıma: XML dosyalarından metin çıkarılır ve performans değerlendirilir.
* Sonuç Görselleştirme: Matplotlib ile örnek görüntüler ve tahminler gösterilir.

## Kullanım
1️⃣ Bu depoyu klonlayın:
```bash
git clone https://github.com/<kullanıcı-adınız>/<depo-adınız>.git
```

2️⃣ Google Colab'da projeyi açın ve Google Drive'ınızı bağlayın.

3️⃣ Veri seti yollarını kendi Drive dizininize göre güncelleyin.

4️⃣ Not defterindeki hücreleri sırayla çalıştırarak veriyi işleyin ve sonuçları değerlendirin.


