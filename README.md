📍 Kentsel Haber İzleme ve Harita Üzerinde Görselleştirme Sistemi
Bu proje, Kocaeli yerel haber sitelerinden (Çağdaş Kocaeli, Özgür Kocaeli, Ses Kocaeli vb.) son 3 güne ait verileri Web Scraping yöntemleriyle toplayan, Doğal Dil İşleme (NLP) kullanarak sınıflandıran ve elde edilen olayları Google Maps API üzerinden interaktif bir harita üzerinde sunan uçtan uca bir sistemdir..

🚀 Öne Çıkan Özellikler
Akıllı Scraping: 5 farklı yerel kaynaktan otomatik veri çekme ve HTML temizliği.

NLP ile Sınıflandırma: intfloat/multilingual-e5-base modeli kullanılarak haberlerin Trafik Kazası, Yangın, Hırsızlık, Elektrik Kesintisi ve Kültürel Etkinlikler kategorilerine yüksek doğrulukla atanması.

Semantik Tekrar Engelleme: İçerik olarak %90 ve üzeri benzerlik gösteren farklı kaynaklardaki haberlerin tespit edilip tek bir marker altında birleştirilmesi.

Otomatik Konum Çıkarımı: Haber metninden mahalle/sokak bilgilerinin Regex ve NLP ile ayıklanıp koordinata dönüştürülmesi.

Dinamik Dashboard: Harita üzerinden anlık filtreleme (tarih, ilçe, tür) ve haber detaylarına hızlı erişim.

🛠 Teknik Mimari
Backend (Python - FastAPI)
Veritabanı: MongoDB (Zorunlu ister kapsamında Schema Validasyonu ile birlikte).

NLP & AI: Sentence-Transformers ve PyTorch tabanlı semantik analiz.

Geocoding: Google Maps Geocoding API ile adres-koordinat dönüşümü ve maliyet tasarrufu için MongoDB tabanlı konum önbellekleme (Caching).

Scraping: httpx ve BeautifulSoup4 ile asenkron veri toplama.

Frontend (Modern Web)
Harita: Google Maps JavaScript API (Advanced Markers).

Arayüz: CSS Glassmorphism ve Modern Dashboard tasarımı (Inter & Outfit fontları).

📂 Dosya Yapısı
Bash
.
├── backend/
│   ├── main.py            # FastAPI API uç noktaları
│   ├── scraper.py         # Web scraping ve veri toplama boru hattı
│   ├── nlp_processor.py   # AI Sınıflandırma ve semantik benzerlik motoru
│   ├── geocoder.py        # Konum-Koordinat dönüşümü ve Cache sistemi
│   ├── database.py        # MongoDB bağlantısı ve Schema validasyonu
│   └── requirements.txt   # Gerekli kütüphaneler
├── frontend/
│   ├── index.html         # Ana dashboard arayüzü
│   ├── style.css          # Modern görsel tasarım
│   ├── app.js             # Harita mantığı ve API entegrasyonu
│   └── config.js          # API Anahtarları ve yapılandırma
└── README.md
🔧 Kurulum ve Çalıştırma
1. Gereksinimler
Python 3.12+

MongoDB (Local veya Atlas)

Google Maps API Key

2. Backend Kurulumu
Bash
cd backend
pip install -r requirements.txt
.env dosyasını oluşturun ve bilgilerinizi girin:

Kod snippet'i
MONGO_URI=mongodb://localhost:27017
GOOGLE_MAPS_API_KEY=KENDI_ANAHTARINIZ
3. Sistemi Başlatma
Backend'i çalıştırın:

Bash
uvicorn main:app --reload
Ardından frontend/index.html dosyasını tarayıcınızda açın.

📊 Veri Akış Şeması
Tetikleme: Kullanıcı arayüzden "Haberleri Güncelle"ye tıklar.

Scraping: Belirlenen 5 yerel siteden son 3 günün haberleri çekilir.

İşleme: Metinler temizlenir, AI modeli ile kategorize edilir.

Konum: Haber metninden konum ayıklanır ve koordinata dönüştürülür.

Kayıt: Veriler MongoDB'ye kaydedilir (Duplicate kontrolü ile).

Görselleştirme: Harita üzerinde türe göre farklı ikonlarla gösterilir.

👨‍💻 Hazırlayan
Ömercan - [Kocaeli Üniversitesi Bilgisayar Mühendisliği]
