Kod incelemesi, yorumlar ve notlar.

def __init__() - Başlatmak için
def _init_driver(self): - argumentler için. 

'```python
            # User agent
options.add_argument(
    "user-agent=Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/120.0.0.0 Safari/537.36"
            )
''' 

burası header. 

def _manual_login_wait(self):

Maneul girmek için kullanılıyor. Sisteme buradan manuel giriyoruz. 

120 sn bekliyor. Burayı kısaltabiliriz. 

def _parse_tweet_date()

"Tweetlerin tarihlerini ayırmak için kullanıyor."

def _is_within_days()

Belritilen tarih aralığında mı?

def _parse_metric()

engagement metrics' 1.2k 5.5m gibi gösteriliyor.

Bunları önce küçğk harge öeviriyor. Sonra bölüyor. 
K ise 1000 ile M ise 1000000 ile B ise 1000000000 ile çarpıyor. 

def scrape_tweets():

url'e git. 

> [!NOTE]
>  * tweet_elements = self.driver.find_elements(
>                         By.XPATH,
>                         "//article[@data-testid='tweet']"
> * time_elem = element.find_element(By.XPATH, ".//time")
> * author_elem = element.find_element(
                                    By.XPATH,
                                    ".//div[@data-testid='User-Name']//a[contains(@href, '/')]"
> like_btn = element.find_element(By.XPATH, ".//button[@data-testid='like']")
> views_link = element.find_element(
                                    By.XPATH,
                                    ".//a[contains(@aria-label, 'görüntülenme') or contains(@aria-label, 'views')]"
> Bu bir selector mu? Arama mı yapıyor? 


`@retry_on_scraping_error` şunu der: _"Eğer bu fonksiyonun içindeki işlemler (tweet çekme) bir hata nedeniyle durursa, hemen pes etme! Fonksiyonu baştan (veya kaldığı yerden) tekrar çalıştırmayı dene."_
