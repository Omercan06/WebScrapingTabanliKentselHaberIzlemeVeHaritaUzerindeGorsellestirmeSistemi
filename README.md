# 📍 Kentsel Haber İzleme ve Harita Üzerinde Görselleştirme Sistemi

![Kocaeli University](https://img.shields.io/badge/Kocaeli_University-Computer_Engineering-blue) ![Project Status](https://img.shields.io/badge/Status-Completed-success) ![Python](https://img.shields.io/badge/Python-3.12+-yellow) ![FastAPI](https://img.shields.io/badge/FastAPI-Latest-009688) ![MongoDB](https://img.shields.io/badge/MongoDB-Atlas-47A248)

Bu proje, Kocaeli yerel haber sitelerinden (Çağdaş Kocaeli, Özgür Kocaeli, Ses Kocaeli, Yeni Kocaeli ve Bizim Yaka) son 3 güne ait verileri **Web Scraping** yöntemleriyle toplayan, **Doğal Dil İşleme (NLP)** kullanarak sınıflandıran ve elde edilen olayları **Google Maps API** üzerinden interaktif bir harita üzerinde sunan uçtan uca bir sistemdir.

## 🚀 Öne Çıkan Özellikler

* **Akıllı Scraping:** 5 farklı yerel kaynaktan otomatik veri çekme ve asenkron HTML temizliği.
* **NLP ile Sınıflandırma:** `intfloat/multilingual-e5-base` modeli kullanılarak haberlerin; *Trafik Kazası, Yangın, Hırsızlık, Elektrik Kesintisi ve Kültürel Etkinlikler* kategorilerine AI desteğiyle atanması.
* **Semantik Tekrar Engelleme:** Farklı kaynaklarda yer alan ancak içerik olarak aynı olan haberlerin %90 ve üzeri benzerlik oranıyla tespit edilip tek bir marker altında birleştirilmesi.
* **Otomatik Konum Çıkarımı:** Haber metninden mahalle ve sokak bilgilerinin Regex ve NLP ile ayıklanıp koordinata dönüştürülmesi.
* **Dinamik Dashboard:** Harita yeniden yüklenmeden anlık filtreleme (tarih, ilçe, tür) ve haber detaylarına hızlı erişim.

## 🛠 Teknik Mimari

### Backend (Python - FastAPI)
* **Veritabanı:** MongoDB (Zorunlu ister kapsamında Schema Validasyonu ve Unique Index desteğiyle).
* **NLP & AI:** `Sentence-Transformers` ve `PyTorch` tabanlı semantik analiz motoru.
* **Geocoding:** Google Maps Geocoding API entegrasyonu ve maliyet tasarrufu için MongoDB tabanlı konum önbellekleme (Caching).
* **Scraping:** `httpx` ve `BeautifulSoup4` ile asenkron veri toplama.

### Frontend (Modern Web)
* **Harita:** Google Maps JavaScript API (Advanced Markers ve Custom Dark Style).
* **Arayüz:** CSS Glassmorphism ve modern dashboard tasarımı (Inter & Outfit fontları ile premium görünüm).

## 📂 Dosya Yapısı

```bash
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

👨‍💻 Hazırlayan
Ömercan - [Kocaeli Üniversitesi Bilgisayar Mühendisliği]
