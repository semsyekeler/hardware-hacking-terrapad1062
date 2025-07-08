# Bölüm IV: Yazılım Optimizasyonu

Donanım artık potansiyeline ulaşmıştı. Sıra, bu donanımdan en iyi performansı alacak yazılımı bulmaya ve optimize etmeye gelmişti.

## Arayış: Doğru İşletim Sistemi

*   **Problem:** Intel Atom Z8350 gibi düşük güçlü bir işlemci, modern işletim sistemleri altında kolayca zorlanabilir. Amacım, en akıcı ve en uyumlu deneyimi sunan sistemi bulmaktı.
*   **Deneyler:** Bu amaçla birçok popüler Linux dağıtımını test ettim: MX Linux (XFCE), Zorin OS Lite ve çeşitli Debian versiyonları.
*   **Sonuç:** Testler, Linux dağıtımlarının bu özel donanım kombinasyonunda sürücü uyumluluğu, dokunmatik ekran hassasiyeti ve genel sistem kararlılığı konularında Windows 10'un gerisinde kaldığını gösterdi. Özellikle ses ve sensör sürücüleri sorunluydu.

![Debian Kurulum Denemesi](../assets/images/debian%20net%20install%20kde%20plasma%20denerken%20kod%20ekrani%20açık.jpg)
*^Linux dünyasındaki sayısız denemeden sadece biri. Her dağıtım, donanım uyumluluğu konusunda farklı bir sınav verdi.*

## Optimizasyon: Windows 10'u Uçurmak

Nihai karar, donanım için özel olarak tasarlanmış olan ruha, yani Windows 10'a geri dönmekti. Ancak standart bir kurulumla yetinmedim.

| Yazılım Optimizasyonu | Uygulama Arayüzü |
| :--- | :--- |
| **Problem:** Tarayıcı üzerinden YouTube izlemek, işlemciyi anında %100 kullanıma kilitleyerek cihazı aşırı yavaşlatıyor ve ısındırıyordu. Bu, benzer donanıma sahip tüm cihazların ortak kaderidir. <br><br> **Çözüm:** Tarayıcının getirdiği tüm gereksiz yükü ortadan kaldıran, YouTube videolarını doğrudan kendi arayüzünde API üzerinden çeken **FreeTube** adında bir masaüstü uygulaması kurdum. <br><br> **Sonuç:** Bu tek değişiklik devrim niteliğindeydi. İşlemci kullanımı %20-30 seviyelerine düştü, 1080p videolar bile takılmadan, akıcı ve **reklamsız** bir şekilde izlenebilir hale geldi. Bu, tabletin medya tüketim kabiliyetini tek başına baştan yarattı. | <img src="../assets/images/freetube.jpg" width="350"> |

*   **Üretkenlikte Zirve:** Microsoft OneNote uygulaması, tabletin Wacom tabanlı kalem teknolojisiyle kusursuz bir uyum sergiledi. Not almak, çizim yapmak ve PDF'ler üzerine işaretlemeler yapmak inanılmaz derecede akıcı ve keyifliydi.

Bu optimizasyonlar sayesinde, Terra Pad 1062, zayıf donanımına rağmen hem üretkenlik hem de eğlence için son derece verimli ve modern bir cihaza dönüştü.

![Windows 10 ve OneNote ile Mükemmel Uyum](../assets/images/one%20note%20for%20windows%2010%20tablet%20dış%20çekim.jpg)
*^Doğru yazılım ve donanımın birleşimi, cihazın potansiyelini tamamen ortaya çıkardı.*
