# Bölüm II: Donanımsal Evrim

Bir cihazı onarmak onu standartlarına döndürür. Onu evrimleştirmek ise potansiyelinin ötesine taşımaktır. Bu bölümde, tabletin zayıf noktalarını güçlendiren ve onu daha kullanışlı hale getiren modifikasyonlar yer almaktadır.

## Tersine Mühendislik: Docking Portunu Deşifre Etmek

*   **Amaç:** Tabletin altındaki, orijinal klavyesi için tasarlanmış 5-pinli manyetik **Pogo-Pin konnektörünü** işlevsel bir porta dönüştürmek.
*   **Yöntem:** Üreticiden alınan şema (1. Fotoğraf) ve multimetre ölçümleriyle pin yapısı çözüldü ve kendi şemamı (2. Fotoğraf) oluşturdum. Portun tam işlevli bir USB 2.0 arayüzü barındırdığı doğrulandı.
*   **Sonuç:** Bu bilgiyle, cihaza ergonomik ve gizli bir harici USB-A portu kazandıran özel bir adaptör yapıldı. Adaptör, tabletin iç girintisine tamamen gömülerek dışarıda kaba bir çıkıntı bırakmadı.

<p float="left">
  <img src="../assets/images/thumbnail_pin_belegung_F1T.jpg" width="400" />
  <img src="../assets/images/pin%20diyagram%20tablet.png" width="400" /> 
</p>
<p align="center">
  <i>1. Fotoğraf: Üreticinin sağladığı orijinal şema.      2. Fotoğraf: Kendi ölçümlerimle doğruladığım pin yapısı.</i>
</p>

### Pin Numaralandırması ve İşlevleri

Analizler, portun aslında tam işlevli bir USB 2.0 portu barındırdığını kesinleştirdi. Pinler aşağıdaki gibidir:

| Pin Numarası | İşlevi                | Şema Karşılığı | Açıklama                                                                |
| :----------: | ------------------- | :------------: | ----------------------------------------------------------------------- |
| **1**        | **+5V Güç**         |  `+V_5P0_KB`   | Harici aksesuarlara güç sağlar. USB standartlarına uygun.                 |
| **2**        | **USB Data - (DN)** | `USB2_MODEM_DN`| Standart USB 2.0 negatif veri hattı.                                    |
| **3**        | **USB Data + (DP)** | `USB2_MODEM_DP`| Standart USB 2.0 pozitif veri hattı.                                    |
| **4**        | **Klavye Algılama** |    `KB_DET`    | Klavye takılı olup olmadığını algılar. Harici klavye tarafından, **1k Ohm'luk bir direnç üzerinden** GND'ye (Pin 5) çekildiğinde aktif olur. |
| **5**        | **Toprak (GND)**    |     `GND`      | Devre için ortak referans topraklaması.                                   |

## Modifikasyon 1: Ses Sistemi Yükseltmesi

*   **Problem:** Cihazın orijinal hoparlörleri, özellikle konuşma içeren içeriklerde rahatsız edici derecede tiz ve cılız bir ses kalitesi sunuyordu.
*   **Çözüm:** Eski bir dizüstü bilgisayardan söktüğüm, kendi akustik ses odacıklarına sahip, çok daha kaliteli bir çift hoparlörü, tabletin orijinal hoparlör çıkışlarına lehimledim.
*   **Mühendislik Detayı:** Hoparlörlerin kablolarını, tabletin orijinal hoparlör ızgaralarından geçirdim. Bu sayede dışarıda hiçbir kablo izi kalmadı. Hoparlörleri kasa geometrisine **sıfıra sıfır** oturacak şekilde konumlandırdım. Bu sayede ne ekrana bir baskı oluştu ne de tableti elde tutarken varlıkları hissedildi. Ses kalitesi, gece ile gündüz kadar farklılaştı.

<p align="center">
  <img src="../assets/images/hoparlor_lehimlerken.jpg" width="450">
</p>
<p align="center">
  <i>Teneke seslere veda anı. Her milimetrenin hesabı yapıldı.</i>
</p>

## Modifikasyon 2: "Hayalet Klavye" Sorununun Çözümü

*   **Problem:** Yaptığım özel USB soketinin metal pinleri, tabletin alüminyum şasesine temas ederek `KB_DET` (Klavye Algılama) pinini istem dışı olarak tetikliyor, bu da otomatik ekran döndürmeyi kilitliyordu.
*   **Arıza Tespiti:** Birkaç gözlemden sonra sorunun kaynağını buldum: Yaptığım özel soketin lehimlenmiş metal pinleri, tabletin alüminyum şasesine temas ediyordu.
*   **Çözüm:** Temas eden bölgeyi sıcak silikon ile tamamen yalıtarak bu sorunu kalıcı olarak çözümledim. Bu, özellikle metal kasalı cihazlarda yapılan modifikasyonlarda yalıtımın ne kadar kritik olduğunu gösteren bir tecrübe oldu.

## Diğer Mekanik İyileştirmeler

*   **Kamera Lensi Değişimi:** Çizik olan orijinal kamera lensi, eski bir laptoptan dikkatlice sökülen sağlam bir lens ile değiştirildi. Lens, yapışkanına zarar vermemek için etrafındaki plastikten kırılarak dikkatlice ayrıldı.
*   **Şase Gıcırdamasının Giderilmesi:** Kasanın esneyen ve gıcırdama yapan noktalarına, iç kısımdan küçük destek parçaları eklenerek cihazın mekanik bütünlüğü artırıldı ve ses sorunu giderildi.

<p align="center">
  <img src="../assets/images/tablet%20modifiye%20edilmiş%20hal%20içi.png">
</p>
<p align="center">
  <i>Tüm modifikasyonlar tamamlandıktan sonra tabletin iç düzeni.</i>
</p>

---
**[Sıradaki Bölüm: Yazılım ve Optimizasyon →](./3_Software_and_Optimization.md)**
