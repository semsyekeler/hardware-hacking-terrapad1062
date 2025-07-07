# Bölüm II: Sırları Çözmek - Kayıp Docking Portu

Tableti hayata döndürdükten sonra gözüm, altındaki gizemli 5 pinli manyetik konnektöre takıldı. Bu port ne işe yarıyordu ve potansiyeli neydi? Bu sorular, projenin ikinci aşamasını başlattı.

## Görev: Pinlerin Haritasını Çıkarmak

Üretici (Wortmann AG) ile yaptığım yazışmalar sonucunda, portun bir şemasını elde etmeyi başardım. Bu şemayı kendi ölçümlerimle birleştirerek pinlerin işlevlerini kesin olarak doğruladım.

![Docking Portu Şeması](../assets/images/thumbnail_pin_belegung_F1T.jpg)
*^Üreticinin sağladığı orijinal şema.*

![Kendi Pin Çizimim](../assets/images/pin%20diyagram%20tablet.png)
*^Şema ve multimetre ölçümleriyle doğruladığım pin yapısı.*

### Doğrulanmış Pin Yapısı (Soldan Sağa)

| Pin No | İşlevi                | Şema Karşılığı | Açıklama                                                                |
| :----: | ------------------- | :------------: | ----------------------------------------------------------------------- |
| **1**  | **+5V Güç**         |  `+V_5P0_KB`   | Harici aksesuarlara güç sağlar.                                         |
| **2**  | **USB Data - (DN)** | `USB2_MODEM_DN`| Standart USB 2.0 negatif veri hattı.                                    |
| **3**  | **USB Data + (DP)** | `USB2_MODEM_DP`| Standart USB 2.0 pozitif veri hattı.                                    |
| **4**  | **Klavye Algılama** |    `KB_DET`    | Klavye takılı olup olmadığını algılar. Toprağa (GND) çekilince aktif olur. |
| **5**  | **Toprak (GND)**    |     `GND`      | Devre için ortak referans topraklaması.                                   |

## İcat: Özel USB Adaptörü

Bu pin bilgilerini kullanarak, tablete harici bir USB-A portu kazandıran özel bir adaptör tasarladım. Bu adaptör sayesinde, tablete tek bir kabloyla hem klavye/fare gibi cihazları hem de USB bellekleri bağlamak mümkün hale geldi.

![Özel USB Adaptörüm](../assets/images/tablete%20bağlanan%20usb%20dişi%20kısım.jpg)
*^Pogo pinler ve bir USB dişi portu kullanılarak yapılmış özel adaptör.*
