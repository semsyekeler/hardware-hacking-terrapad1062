# Bölüm II: Donanımsal Evrim

Bu bölümde, cihazın standart yeteneklerinin ötesine taşınmasını sağlayan donanımsal modifikasyonlar ve iyileştirmeler detaylandırılmaktadır.

## Gerekli Aletler ve İlk Adımlar

*   **Tornavida:** Bu cihazda **Torx T4** uçlu tornavida gereklidir.
*   **Açma Aparatı:** Kasayı çizmeden açmak için plastik bir pena veya eski bir banka kartı idealdir.
*   **Önemli Uyarı (Sökme):** Arka kapağı açarken, **sadece tabletin kendi standını (kickstand) tutan vidaları sökün.** Doğrudan menteşenin ana şaseye bağlı olduğu vidalara dokunmayın. Aksi takdirde geri montajda menteşe hizalaması büyük bir sorun olabilir.
*   **Önemli Uyarı (Kablolar):** Cihazın içindeki ribbon (şerit) kablolar çok hassastır ve kolayca kopabilir. Sökme/takma işlemlerinde aşırı güç uygulamaktan kaçının.

## Tersine Mühendislik: Docking Portunun Analizi

*   **Amaç:** Tabletin alt kısmında bulunan, orijinal klavyesi için tasarlanmış 5-pinli manyetik **Pogo-Pin konnektörünü** analiz ederek işlevsel bir porta dönüştürmek.
*   **Yöntem:** Üreticiden temin edilen teknik şema (1. Fotoğraf) ve multimetre kullanılarak yapılan ölçümlerle pin yapısı doğrulandı. Bu doğrulamaya dayanarak kendi bağlantı şemam (2. Fotoğraf) oluşturuldu.
*   **Sonuç:** Elde edilen bilgilerle, cihaza harici bir USB-A portu kazandıran özel bir adaptör imal edildi.

<p float="left">
  <img src="../assets/images/thumbnail_pin_belegung_F1T.jpg" width="400" />
  <img src="../assets/images/pin%20diyagram%20tablet.png" width="400" /> 
</p>
<p align="center">
  <i>1. Fotoğraf: Üreticinin sağladığı orijinal şema.      2. Fotoğraf: Kendi ölçümlerimle doğruladığım pin yapısı.</i>
</p>

### Pin Numaralandırması ve İşlevleri

| Pin Numarası | İşlevi                | Şema Karşılığı | Açıklama                                                                |
| :----------: | ------------------- | :------------: | ----------------------------------------------------------------------- |
| **1**        | **+5V Güç**         |  `+V_5P0_KB`   | Harici aksesuarlara güç sağlar. USB standartlarına uygundur.             |
| **2**        | **USB Data - (DN)** | `USB2_MODEM_DN`| Standart USB 2.0 negatif veri hattı.                                    |
| **3**        | **USB Data + (DP)** | `USB2_MODEM_DP`| Standart USB 2.0 pozitif veri hattı.                                    |
| **4**        | **Klavye Algılama** |    `KB_DET`    | Klavye takılı olup olmadığını algılar. Harici klavye tarafından, **1k Ohm'luk bir direnç üzerinden** GND'ye (Pin 5) çekilerek aktif olur. |
| **5**        | **Toprak (GND)**    |     `GND`      | Devre için ortak referans topraklaması.                                   |

## Modifikasyon 1: Ses Sistemi Yükseltmesi

*   **Problem:** Cihazın orijinal hoparlörleri, özellikle konuşma içeren içeriklerde yetersiz ve tiz bir ses karakteristiği sergiliyordu.
*   **Çözüm:** Eski bir dizüstü bilgisayardan alınan, kendi akustik odacıklarına sahip daha yüksek kaliteli bir çift hoparlör, tabletin orijinal hoparlör çıkışlarına lehimlendi.
*   **Mühendislik Detayı:** Hoparlörler, kasa geometrisine tam oturacak şekilde konumlandırılarak cihazın ergonomisi ve fiziksel bütünlüğü korundu.

## Modifikasyon 2: "Hayalet Klavye" Sorununun Çözümü

*   **Problem:** Yapılan özel USB soketinin metal pinlerinin, tabletin alüminyum şasesine temas etmesi sonucu `KB_DET` pini istem dışı olarak tetikleniyor, bu da otomatik ekran döndürme gibi işlevleri kilitliyordu.
*   **Arıza Tespiti (Hipotez ve Gerçek):** İlk başta sorunun, batarya sökülse bile şarjlı kalan bir kapasitörden kaynaklandığını düşündüm. Ancak asıl nedenin, soket ile şase arasındaki fiziksel temas (kısa devre) olduğu anlaşıldı.
*   **Çözüm:** Temas eden bölge, sıcak silikon kullanılarak elektriksel olarak yalıtıldı ve sorun kalıcı olarak giderildi.

## Diğer Mekanik İyileştirmeler

*   **Kamera Lensi Değişimi:** Çizik olan orijinal kamera lensi, eski bir laptoptan alınan sağlam bir lens ile değiştirildi. Lens, yapışkanına zarar vermemek için etrafındaki plastikten kırılarak dikkatlice ayrıldı.
*   **Şase Gıcırdamasının Giderilmesi:** Kasanın esneyen noktalarına iç kısımdan destek parçaları eklenerek mekanik stabilite artırıldı ve gıcırdama sesi engellendi.

---
<p align="center">
  <strong><a href="./1_Repair_and_Resurrection.md">← Önceki Bölüm: Onarım ve Diriliş</a></strong>
  <span style="padding: 0 20px;">|</span>
  <strong><a href="./3_Software_and_Optimization.md">Sıradaki Bölüm: Yazılım ve Optimizasyon →</a></strong>
</p>
