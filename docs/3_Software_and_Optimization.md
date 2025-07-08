# Bölüm III: Yazılım ve Optimizasyon

[← Önceki Bölüm: Donanımsal Evrim](./2_Hardware_Evolution.md)

Donanım modifikasyonları tamamlandıktan sonraki aşama, bu donanıma en uygun yazılım ekosistemini kurmak ve onu verimli bir iş istasyonuna dönüştürmekti.

## A. İşletim Sistemi Arayışı: Zorlu Bir Macera

*   **Problem:** Intel Atom Z8500 gibi düşük güçlü bir işlemci, modern işletim sistemleri altında kolayca zorlanabilir. Amacım, hem medya tüketimi hem de üretkenlik için en akıcı deneyimi sunan sistemi bulmaktı.
*   **Deneyler ve Sonuçlar:**
    *   **Ubuntu Macerası:** Kurulum sırasında ekranın sürekli olarak rastgele zamanlarda kapanması, hem kurulum sürecini sekteye uğrattı hem de kararlı bir kullanımın mümkün olmayacağını gösterdi.
    *   **Debian (Net Install) Denemesi:** Çift işletim sistemi amacıyla, mümkün olan en minimal Debian kurulumunu yaptım. Hedefim, medya tüketimi için ultra hafif bir Linux ortamı yaratmaktı. Ancak sonuç, Windows 10'a kıyasla son derece yavaş, hantal ve tabletin donanım özelliklerinden uzak, adeta bir işkenceye dönüşen bir deneyim oldu.
*   **Nihai Karar:** Yapılan testler, bu özel donanım kombinasyonu için en stabil, uyumlu ve performanslı platformun **Windows 10** olduğunu kesinleştirdi. Özellikle dokunmatik ekran, kalem ve sensör sürücüleri konusundaki sorunsuz entegrasyon belirleyici oldu.

<p align="center">
  <img src="../assets/images/debian%20net%20install%20kde%20plasma%20denerken%20kod%20ekrani%20açık.jpg" width="550">
</p>
<p align="center">
  <i>Linux dünyasındaki sayısız denemeden sadece biri. Her dağıtım, donanım uyumluluğu konusunda farklı bir sınav verdi.</i>
</p>

## B. Kritik Yazılım Seçimleri: Hız ve Stabilite

Bu donanımda en iyi çalışan ve tableti gerçek bir taşınabilir iş istasyonuna dönüştüren, **hızlı açılan ve stabil kullanım sağlayan** yazılımlar şunlar oldu:

| Kategori | Seçilen Yazılım | Açıklama ve İndirme Linki |
| :--- | :--- | :--- |
| **Kodlama** | **Sublime Text** | İnanılmaz derecede hafif yapısı sayesinde anında açılıyor ve en büyük kod dosyalarında bile takılmadan, akıcı bir kullanım sunuyor. <br> *[Resmi Web Sitesi](https://www.sublimetext.com/)* |
| **PDF** | **PDF-XChange Editor** | Adobe Reader gibi ağır alternatiflerin aksine, çok hızlı açılıyor ve büyük PDF'lerde gezinirken bile kasmadan stabil bir performans sergiliyor. <br> *[Resmi Web Sitesi](https://www.tracker-software.com/product/pdf-xchange-editor)* |
| **Ofis** | **SoftMaker FreeOffice** | Microsoft Office'e en hızlı ve en hafif alternatif. Word, Excel ve PowerPoint dosyalarını şaşırtıcı bir hızla açıyor ve düzenliyor. <br> *[Resmi Web Sitesi](https://www.freeoffice.com/en/)* |
| **E-Posta**| **Wino Mail** | Modern ve temiz arayüzünü, sistem kaynaklarını tüketmeyen hafif bir yapıyla birleştiriyor. <br> *[Microsoft Store](https://apps.microsoft.com/detail/9ncrcvjc50wl?hl=en-us&gl=us)* |
| **Uzak Masaüstü**| **Parsec** | Düşük gecikmeli teknolojisi sayesinde ana bilgisayara uzaktan bağlanarak ağır işleri bile bu tablet üzerinden akıcı bir şekilde yapma imkanı tanır. <br> *[Resmi Web Sitesi](https://parsec.app/)* |

<p align="center">
  <img src="../assets/images/programs.jpg" width="700">
</p>
<p align="center">
  <i>Cihazın potansiyelini ortaya çıkaran hafif ve güçlü yazılımlar.</i>
</p>

## C. Günlük Kullanım Optimizasyonları ve İpuçları

| YouTube Sorunu ve Çözümü | OneNote ve Kalem Çözümü |
| :---: | :---: |
| <img src="../assets/images/freetube.jpg" width="350"> | <img src="../assets/images/one%20note%20for%20windows%2010%20tablet%20dış%20çekim.jpg" width="350"> |
| **Problem:** Tarayıcıdan YouTube izlemek, sürekli takılmalar ve ses/görüntü senkronizasyon sorunları yaratıyordu.<br><br> **Çözüm:** Tarayıcıyı aradan çıkaran **[FreeTube](https://freetubeapp.io/)** istemcisi kuruldu. Bu tek uygulama, **akıcı ve reklamsız bir deneyim** sunarak tabletin medya tüketim kabiliyetini tamamen değiştirdi. | **Problem:** Akıcı bir not alma uygulaması ve kalem eksikliği.<br><br> **Çözüm:** En hızlı versiyon olan `OneNote for Windows 10` (Microsoft Store) ile **[VirtualTablet](https://www.sunnysidesoft.com/virtualtablet/)** uygulaması birleştirildi. VirtualTablet, bir akıllı telefonu PC'ye bir grafik tablet gibi bağlayarak, telefonun kalemini OneNote'da kullanma imkanı sağladı. |

### Tarayıcı Optimizasyonu ve Dokunmatik Ekran İpuçları
*   **En Hızlı Tarayıcı:** Bu donanım için en iyi tarayıcıyı bulma arayışında, popüler tüm alternatifler test edildi. Testler sonucunda, en az sistem kaynağı tüketen ve en akıcı performansı sunan tarayıcının **Microsoft Edge** olduğu netleşti.
*   **Chromium Tabanlı Tarayıcılarda Kritik Dokunmatik Sorunu ve Çözümü:**
    *   **Problem:** Chrome, Brave gibi tarayıcılarda, "yeni sekme aç" (+) butonuna dokunmatik olarak tıklandığında, sistem dokunuşun hassas konumunu yanlış yorumlayıp hemen yanındaki "sekmeyi kapat" (X) butonuna basılmış gibi algılıyordu.
    *   **Çözüm:** Bu sorunu aşmak için, butona sadece dokunmak yerine, **her tıklamada kısa bir süre basılı tutmak** gerekiyor. Bu küçük gecikme, sistemin doğru konumu tanıması için yeterli zamanı tanıyor.

Bu yazılımlar ve optimizasyonlar sayesinde tablet, donanımının getirdiği tüm dezavantajların aşıldığı, tam teşekküllü bir taşınabilir Windows sistemine dönüştü.

---
**[Sıradaki Bölüm: Sınırların Ötesi - Yeni Yetenekler →](./4_Beyond_The_Limits.md)**
