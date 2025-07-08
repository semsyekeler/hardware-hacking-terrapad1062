# Bölüm II: Docking Portu Tersine Mühendisliği

Tablet hayata döndükten sonra, potansiyelini artırmak için yeni yollar aramaya başladım. Tabletin altındaki, orijinal klavyesi için tasarlanmış 5-pinli manyetik pogo konnektör, bir genişleme portu potansiyeli taşıyordu.

## Görev: Pinlerin Haritasını Çıkarmak

Bu portun sırrını çözmek için iki yönlü bir strateji izledim: Dijital ve Fiziksel.

1.  **Dijital Keşif:** Üretici Wortmann AG ile kurduğum teması devam ettirerek, portun teknik bir şemasını rica ettim. Projeye olan ilgimden dolayı, portun bağlantılarını gösteren bir şema parçası gönderdiler.
2.  **Fiziksel Doğrulama:** Bir multimetre ile, şemadaki her bir pinin işlevini fiziksel olarak test ettim. Voltaj ölçümleriyle +5V ve GND pinlerini, süreklilik testiyle de USB data hatlarını doğruladım.

<p float="left">
  <img src="../assets/images/thumbnail_pin_belegung_F1T.jpg" width="400" />
  <img src="../assets/images/pin%20diyagram%20tablet.png" width="400" /> 
</p>

*^Solda üreticinin sağladığı şema, sağda ise kendi ölçümlerimle doğruladığım pin yapısı.*

### Deşifre Edilmiş Pin Yapısı (Soldan Sağa)

Bu analizler sonucunda, portun aslında tam işlevli bir USB 2.0 portu barındırdığı kesinleşti:

| Pin No | İşlevi                | Şema Karşılığı | Açıklama                                                                |
| :----: | ------------------- | :------------: | ----------------------------------------------------------------------- |
| **1**  | **+5V Güç**         |  `+V_5P0_KB`   | Harici aksesuarlara güç sağlar. USB standartlarına uygun.                 |
| **2**  | **USB Data - (DN)** | `USB2_MODEM_DN`| Standart USB 2.0 negatif veri hattı.                                    |
| **3**  | **USB Data + (DP)** | `USB2_MODEM_DP`| Standart USB 2.0 pozitif veri hattı.                                    |
| **4**  | **Klavye Algılama** |    `KB_DET`    | Klavye takılı olup olmadığını algılar. Toprağa (GND) çekilince aktif olur. |
| **5**  | **Toprak (GND)**    |     `GND`      | Devre için ortak referans topraklaması.                                   |

## İcat: Özel USB Adaptörü

Bu bilgiyle, tablete harici bir USB-A portu kazandıran özel bir adaptör tasarladım. Bu adaptör sayesinde, cihaza tek bir kabloyla hem klavye/fare gibi cihazları hem de USB bellekleri bağlamak mümkün hale geldi.

![Özel USB Adaptörüm](../assets/images/tablete%20bağlanan%20usb%20dişi%20kısım.jpg)
*^Pogo pinler ve bir USB dişi portu kullanılarak yapılmış, tablete yeni yetenekler kazandıran özel adaptör.*
