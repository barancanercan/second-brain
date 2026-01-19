---
tags:
  - kod-inceleme
  - scraper
  - python
  - selenium
  - xpath
  - twitter
  - web-scraping
  - automation
date: 2026-01-19
---

# 📜 Kod İncelemesi: X/Twitter Scraper

## Metadata

- **Script Adı:** X/Twitter Scraper
- **Versiyon:** 3.1
- **İnceleme Tarihi:** 2026-01-19
- **İlgili Dosya:** `AI_LLM_Engineering/00_Inbox/x_scraper.py.md`

---

## 🎯 Özet

Bu script, `selenium` ve `undetected-chromedriver` kullanarak belirtilen bir X/Twitter kullanıcısının profilindeki tweet'leri geriye dönük olarak belirli bir zaman aralığı (varsayılan 90 gün) boyunca toplar. Manuel olarak login olmayı gerektirir ve bot tespit mekanizmalarını atlatmayı hedefler.

---

## 📝 Fonksiyon Bazlı Notlar

*Kod incelemesi sırasında alınan fonksiyon bazlı yorumlar ve notlar.*

### `__init__()`
Sınıfı başlatmak için kullanılıyor.

### `_init_driver(self)`
Driver argümanlarını ayarlamak için kullanılıyor.

```python
# User agent örneği
options.add_argument(
    "user-agent=Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/120.0.0.0 Safari/537.36"
)
```
Bu kısım HTTP header'ını ayarlıyor.

### `_manual_login_wait(self)`
Sisteme manuel giriş yapmak için kullanılıyor. 120 saniye bekliyor.

> [!TIP]
> Bu süre ihtiyaca göre kısaltılabilir.

### `_parse_tweet_date()`
Tweetlerin tarihlerini ayrıştırmak için kullanılıyor.

### `_is_within_days()`
Bir tweet'in belirtilen tarih aralığında olup olmadığını kontrol ediyor.

### `_parse_metric()`
Engagement metrikleri (1.2K, 5.5M gibi) işliyor:
1. Önce küçük harfe çeviriyor
2. Sonra değeri ve birimi bölüyor
3. Birime göre çarpım yapıyor:
   - `k` → 1.000
   - `m` → 1.000.000
   - `b` → 1.000.000.000

### `scrape_tweets()`
Ana scraping fonksiyonu. URL'e gidip tweet'leri topluyor.

**Kullanılan XPATH Selector'ler:**

> [!NOTE]
> Bu selector'ler Twitter'ın DOM yapısına göre elementleri buluyor.

```python
# Tweet elementlerini bul
tweet_elements = self.driver.find_elements(
    By.XPATH,
    "//article[@data-testid='tweet']"
)

# Zaman elementini bul
time_elem = element.find_element(By.XPATH, ".//time")

# Yazar elementini bul
author_elem = element.find_element(
    By.XPATH,
    ".//div[@data-testid='User-Name']//a[contains(@href, '/')]"
)

# Beğeni butonunu bul
like_btn = element.find_element(By.XPATH, ".//button[@data-testid='like']")

# Görüntülenme linkini bul
views_link = element.find_element(
    By.XPATH,
    ".//a[contains(@aria-label, 'görüntülenme') or contains(@aria-label, 'views')]"
)
```

### `@retry_on_scraping_error` Dekoratörü
Bu dekoratör şunu der: *"Eğer bu fonksiyonun içindeki işlemler (tweet çekme) bir hata nedeniyle durursa, hemen pes etme! Fonksiyonu baştan (veya kaldığı yerden) tekrar çalıştırmayı dene."*
