# Bölüm II: Donanımsal Evrim

Bu bölümde, cihazın standart yeteneklerinin ötesine taşınmasını sağlayan donanımsal modifikasyonlar ve iyileştirmeler detaylandırılmaktadır.

## Tersine Mühendislik: Docking Portunun Analizi

*   **Amaç:** Tabletin alt kısmında bulunan, orijinal klavyesi için tasarlanmış 5-pinli manyetik **Pogo-Pin konnektörünü** analiz ederek işlevsel bir porta dönüştürmek.
*   **Yöntem:** Üreticiden temin edilen teknik şema (1. Fotoğraf) ve multimetre kullanılarak yapılan ölçümlerle pin yapısı doğrulandı. Bu doğrulamaya dayanarak kendi bağlantı şemam (2. Fotoğraf) oluşturuldu. Analizler, portun tam işlevli bir USB 2.0 arayüzü barındırdığını ortaya koydu.
*   **Sonuç:** Elde edilen bilgilerle, cihaza harici bir USB-A portu kazandıran özel bir adaptör imal edildi. Adaptör, tabletin iç girintisine tam oturacak şekilde tasarlanarak ergonomik bütünlük korundu.

<p float="left">
  <img src="../../assets/images/thumbnail_pin_belegung_F1T.jpg" width="400" />
  <img src="../../assets/images/pin%20diyagram%20tablet.png" width="400" />
</p>
<p align="center">
  <i>1. Fotoğraf: Üreticinin sağladığı orijinal şema. &nbsp;&nbsp;&nbsp;&nbsp; 2. Fotoğraf: Kendi ölçümlerimle doğruladığım pin yapısı. (Ön taraf ekran, arka taraf kapak)</i>
</p>

### Pin Numaralandırması ve İşlevleri

Analizler sonucunda elde edilen pin konfigürasyonu aşağıdaki gibidir:

| Pin Numarası | İşlevi                | Şema Karşılığı | Açıklama                                                                |
| :----------: | ------------------- | :------------: | ----------------------------------------------------------------------- |
| **1**        | **+5V Güç**         |  `+V_5P0_KB`   | Harici aksesuarlara güç sağlar. USB standartlarına uygundur.             |
| **2**        | **USB Data - (DN)** | `USB2_MODEM_DN`| Standart USB 2.0 negatif veri hattı.                                    |
| **3**        | **USB Data + (DP)** | `USB2_MODEM_DP`| Standart USB 2.0 pozitif veri hattı.                                    |
| **4**        | **Klavye Algılama** |    `KB_DET`    | Klavye takılı olup olmadığını algılar. Harici klavye tarafından, **1k Ohm'luk bir direnç üzerinden** GND'ye (Pin 5) çekilerek aktif olur. |
| **5**        | **Toprak (GND)**    |     `GND`      | Devre için ortak referans topraklaması.                                   |

<p align="center">
  <img src="../../assets/images/tablete%20bağlanan%20usb%20dişi%20kısım.jpg" width="450">
</p>
<p align="center">
  <i>Tersine mühendislik ile elde edilen bilgilere göre tasarlanan özel USB soketi.</i>
</p>

## Modifikasyonlara Başlamadan Önce: Kasanın Açılması

**UYARI:** Bu işlemler tecrübe gerektirir. Cihazınıza kalıcı hasar verebilir ve garantiyi geçersiz kılabilirsiniz. Tüm sorumluluk size aittir.

*   **Gerekli Aletler:**
    *   Torx T4 tornavida ucu
    *   Plastik pena veya eski bir banka kartı gibi ince ve esnek bir kanırtma aleti

*   **Sökme Talimatları:**
    1.  **Doğru Vidaları Sökün:** Arka kapaktaki **tüm vidaları** sökün. Bunlar kickstand üzerindeki siyah vidalar ve alt kısımdaki beyaz/gümüş renkli vidalardır.
    2.  **KRİTİK UYARI:** Kickstand'ın doğrudan tabletin metal kasasına bağlandığı menteşe vidalarına **kesinlikle dokunmayın!** Bu vidaların sökülmesi, cihazın montajını zorlaştırır ve gereksiz bir işlemdir.
    3.  **Kapağı Ayırın:** Tüm vidalar söküldükten sonra, kasa ile arka kapak arasına plastik penayı dikkatlice sokun ve tırnakları yavaşça attırarak kapağı ayırın.

<p align="center">
  <img src="../../assets/images/tablet%20kasa.jpg" width="700">
</p>
<p align="center">
  <i>Sökme işlemi: Kickstand'ın menteşeye bağlı vidaları (3x2 adet siyah olan) ve altında kalan (gümüş renk 4 vida)  sökülecek,</i>
</p>

*   **Montaj İpuçları:**
    *   Mıknatıslı kısımlara yakın olan alt vidaları takarken, manyetik çekim nedeniyle vida yuvadan kayabilir. Vidayı parmağınızla hizalayarak kılavuzluk yapmanız gerekebilir.
    *   Ribbon (şerit) kablolara son derece hassas davranın; kolayca kopabilirler.
    *   İşlem yaparken vidaların veya metal aletlerin anakart üzerindeki SMD bileşenlere temas ederek kısa devre yapmamasına özen gösterin.

## Modifikasyon 1: Ses Sistemi Yükseltmesi

*   **Problem:** Cihazın orijinal hoparlörleri, özellikle konuşma içeren içeriklerde yetersiz ve tiz bir ses karakteristiği sergiliyordu.
*   **Çözüm:** Eski bir dizüstü bilgisayardan alınan, kendi akustik odacıklarına sahip daha yüksek kaliteli bir çift hoparlör, tabletin orijinal hoparlör çıkışlarına lehimlendi.
*   **Mühendislik Detayı:** Hoparlör kabloları, tabletin orijinal hoparlör ızgaralarından geçirildi. Hoparlörler, kasa geometrisine tam oturacak şekilde konumlandırılarak cihazın ergonomisi ve fiziksel bütünlüğü korundu. Sonuç olarak ses kalitesinde belirgin bir artış sağlandı.

<p align="center">
  <img src="../../assets/images/hoparlor_lehimlerken.jpg" width="450">
</p>
<p align="center">
  <i>Eski laptop hoparlörünün montajı.</i>
</p>

## Modifikasyon 2: "Hayalet Klavye" Sorununun Çözümü

*   **Problem:** Yapılan özel USB soketinin metal pinlerinin, tabletin alüminyum şasesine temas etmesi sonucu `KB_DET` (Klavye Algılama) pini istem dışı olarak tetikleniyor, bu da otomatik ekran döndürme gibi işlevleri kilitliyordu. Bataryayı söküp takmak sorunu geçici olarak çözse de temas devam ettiği için hata tekrarlıyordu.
*   **Çözüm:** Temas eden bölge, yalıtkan olan sıcak silikon kullanılarak elektriksel olarak izole edildi ve sorun kalıcı olarak giderildi.

## Diğer Mekanik İyileştirmeler

*   **Kamera Lensi Değişimi:** Çizik olan orijinal kamera lensi, eski bir laptoptan şasesi kırılarak dikkatlice ayrılan sağlam bir lens ile değiştirildi. Lensin orijinal yapışkanı korunarak montaj yapıldı.
*   **Şase Gıcırdamasının Giderilmesi:** Kasanın esneyen noktalarına iç kısımdan, içe göçmeyi engelleyecek destek parçaları eklenerek mekanik stabilite artırıldı ve gıcırdama sesi tamamen engellendi.

<p align="center">
  <img src="../../assets/images/tablet%20modifiye%20edilmiş%20hal%20içi.png">
</p>
<p align="center">
  <i>Tüm modifikasyonlar tamamlandıktan sonra tabletin iç düzeni.</i>
</p>

---
**[← Önceki Bölüm: Onarım ve Diriliş](./1_Onarim_ve_Dirilis.md) | [Sıradaki Bölüm: Yazılım ve Optimizasyon →](./3_Yazilim_ve_Optimizasyon.md)**