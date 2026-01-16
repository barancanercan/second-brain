# İkinci Beyninize Hoş Geldiniz: AI Destekli Bilgi Yönetim Rehberi

Bu Obsidian kasası (vault), bir Yapay Zeka Mühendisi olarak tüm dijital bilgi birikiminizi, projelerinizi ve notlarınızı yönetmek için tasarlanmış canlı bir sistemdir. Sadece statik bir not defteri değil, aynı zamanda yapay zeka araçlarıyla entegre çalışan, ölçeklenebilir bir "ikinci beyin"dir.

## Temel Felsefe: P.A.R.A. Metodu

Bu kasa, bilgi yönetimi konusunda popüler bir sistem olan **P.A.R.A.** (Projects, Areas, Resources, Archive) metodunun uyarlanmış bir versiyonunu kullanır. Bu metodoloji, bilgiyi ne kadar "eyleme geçirilebilir" olduğuna göre sınıflandırır.

-   **Projects (Projeler):** Belirli bir hedefi ve bitiş tarihi olan, aktif olarak üzerinde çalıştığınız şeyler. (Örn: "Mistral-7B modelini fine-tune etme projesi")
-   **Areas (Alanlar):** Bitiş tarihi olmayan, hayatınızdaki uzun vadeli sorumluluk ve ilgi alanları. (Örn: "Büyük Dil Modelleri Mimarileri", "Kariyer Gelişimi")
-   **Resources (Kaynaklar):** Gelecekte ilginizi çekebilecek genel konular ve materyaller. (Örn: "İlginç makaleler", "Kod parçacıkları")
-   **Archive (Arşiv):** Tamamlanmış veya artık aktif olmayan öğeler.

---

## Klasör Yapısı Detaylı Açıklama

`AI_LLM_Engineering/` klasörü altındaki yapı şu şekildedir:

-   `00_Inbox` (Gelen Kutusu): Aklınıza gelen ani bir fikir, hızlı bir not veya daha sonra nereye koyacağınıza karar vereceğiniz herhangi bir bilgi için ilk durak. **Yeni oluşturulan tüm notlar varsayılan olarak buraya kaydedilir.** Gelen kutunuzu düzenli olarak gözden geçirip notları ilgili klasörlere taşımak, sistemin düzenli kalmasını sağlar.

-   `01_Projects` (Projeler): Aktif olarak üzerinde çalıştığınız, belirli hedefleri olan tüm projeleriniz burada yer alır. Her proje için kendi adıyla bir alt klasör oluşturun (örn: `Project_Finetune_Llama3`).

-   `02_Areas` (Alanlar): Sürekli devam eden sorumluluk ve ilgi alanlarınız. Burası, projelerle doğrudan ilişkili olmayan ama sizin için önemli olan bilgileri biriktirdiğiniz yerdir.
    -   `Papers`: Okuduğunuz ve özetlediğiniz akademik makaleler.
    -   `Experiments`: Yaptığınız model deneylerinin kayıtları, sonuçları ve analizleri.
    -   `Datasets`: İncelediğiniz veya kullandığınız veri setleriyle ilgili notlar.
    -   `Prompts`: Farklı modeller için geliştirdiğiniz ve başarılı bulduğunuz prompt "tarifleri".

-   `03_Resources` (Kaynaklar): Herhangi bir projeye veya alana ait olmayan, genel amaçlı kaynaklarınızın bulunduğu kütüphane.
    -   `Templates`: Yeni notlar (günlük not, proje toplantısı, makale özeti vb.) oluştururken zaman kazanmak için kullanacağınız şablonlar. `Daily_Note_Template.md` buna bir örnektir.
    -   `Code_Snippets`: Sık kullandığınız veya ileride kullanabileceğinizi düşündüğünüz kod parçacıkları.

-   `99_Logs` (Günlükler): Günlük çalışma kayıtlarınızın tutulduğu yer. Sistem, her gün için `Yıl/Yıl-Ay-Gün_Daily_Log.md` formatında otomatik bir not oluşturacak şekilde ayarlanmıştır.

-   `system` (Sistem Klasörü): Bu, kasanın işleyişiyle ilgili yapılandırma ve otomatik olarak yönetilen dosyaları içeren özel bir klasördür.
    -   `archive`: Tamamlanan veya iptal edilen projeler ve artık aktif olmayan alanlar buraya taşınır.
    -   `05_Attachments`: Kasanıza eklediğiniz tüm dosyalar (resimler, PDF'ler vb.) otomatik olarak bu klasörde saklanır.
    -   `Agents`: Gemini gibi yapay zeka ajanlarının yapılandırma dosyalarının ve "yeteneklerinin" (skills) bulunduğu yer.

---

## Temel İş Akışları ve Senaryolar

Bu sistemi en verimli şekilde nasıl kullanacağınıza dair bazı pratik senaryolar:

### Senaryo 1: Yeni Bir Fikri Hızlıca Yakalamak
1.  Aklınıza bir fikir geldiğinde veya hızlıca bir şeyi not almanız gerektiğinde, Obsidian'da yeni bir not oluşturun (`Cmd/Ctrl + N`).
2.  Notunuz, varsayılan olarak `00_Inbox` klasörüne kaydedilecektir.
3.  Fikrinizi veya notunuzu yazın.
4.  Daha sonra (örneğin gün sonunda) `00_Inbox` klasörünüzü gözden geçirin. Bu notun bir projeye mi, bir alana mı yoksa bir kaynağa mı ait olduğuna karar verip ilgili klasöre taşıyın.

### Senaryo 2: Günlük Çalışma ve Log Tutma
1.  Güne başlarken, soldaki Takvim eklentisinden bugünün tarihine tıklayarak veya komut paletinden "Daily notes: Open today's daily note" komutunu çalıştırarak günlük notunuzu açın.
2.  Gün içinde yaptığınız önemli işleri, karşılaştığınız sorunları veya öğrendiğiniz yeni şeyleri buraya zaman damgasıyla ekleyin.
3.  **AI Entegrasyonu:** Terminali açıp Gemini CLI'yi kullanarak "günlüğüme ekle: ..." gibi bir komutla doğrudan not ekleyebilirsiniz. Örneğin:
    > `gemini günlüğüme not düş: Veri ön işleme script'indeki bug'ı çözdüm.`
    Bu komut, `obsidian-daily-journal` yeteneğini kullanarak notu sizin için doğru dosyaya, doğru formatta ekleyecektir.

### Senaryo 3: Yeni Bir Projeye Başlamak
1.  `01_Projects` klasörü altında projenizin adıyla yeni bir klasör oluşturun (örn: `RAG_Uygulamasi_Gelistirme`).
2.  Bu klasörün içine bir `_index.md` veya `README.md` dosyası oluşturarak projenin amacını, hedeflerini ve ana notlara linkleri içeren bir başlangıç sayfası hazırlayın.
3.  Proje toplantı notlarınızı, yapılacaklar listelerinizi ve diğer proje belgelerinizi bu klasör altında oluşturun.
4.  Proje bittiğinde, tüm klasörü `system/archive` altına taşıyarak ana çalışma alanınızı temiz tutun.

### Senaryo 4: Bir Araştırma Makalesini Sisteme Eklemek
1.  İlgili makalenin PDF dosyasını Obsidian kasanıza sürükleyip bırakın. Dosya otomatik olarak `system/05_Attachments` klasörüne kopyalanacaktır.
2.  `02_Areas/Papers` altında, makale için yeni bir özet notu oluşturun.
3.  Bu notta, makalenin ana fikirlerini, önemli noktalarını ve kendi yorumlarınızı yazın.
4.  Notun içine, `[[makale_dosya_adi.pdf]]` şeklinde bir link vererek PDF dosyasını doğrudan notunuza bağlayın.

---

## Yapay Zeka (AI) Entegrasyonu

Bu kasanın en güçlü yanlarından biri, yapay zeka ile derin entegrasyonudur.

-   `system/Agents/Gemini/skills`: Gemini ajanının sahip olduğu "yetenekler" bu klasörde tanımlanır. Bu klasör, aslında bilgisayarınızdaki merkezi `/home/baran/.ai/skills` klasörüne işaret eden bir sembolik linktir. Bu sayede, gelecekte başka AI ajanları (Claude vb.) kullandığınızda, tüm ajanlar aynı merkezi yetenekleri paylaşabilir.
-   **Yeni Bir Yetenek (Skill) Nasıl Eklenir?**
    1.  `/home/baran/.ai/skills` klasörüne gidin.
    2.  `obsidian-daily-journal.md` dosyasını bir şablon olarak kopyalayıp yeni bir `.md` dosyası oluşturun.
    3.  Dosyanın içindeki talimatları ve örnekleri, yeni yeteneğinizin ne yapması gerektiğine göre düzenleyin.
    4.  Kaydettiğiniz anda, Gemini CLI yeni yeteneğinizi otomatik olarak tanıyacak ve kullanıma sunacaktır.

Bu rehber, ikinci beyninizi kullanmaya başlamanız için bir temel oluşturur. Sistemi kendi iş akışlarınıza göre özelleştirmekten ve geliştirmekten çekinmeyin. İyi çalışmalar!