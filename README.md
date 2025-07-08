# Terra Pad 1062: Bir Donanım Geri Dönüşüm ve Modifikasyon Projesi

<img src="./assets/images/guitar_and_tablet_close_photo.jpg" width="600">

*^Onarılıp modifiye edilen tablet, özel yapım bir AUX splitter ve FlexASIO sürücüleri ile gecikmesiz bir elektro gitar amfi prosesörüne dönüştürüldü.*

Bu depo, yazılımsal bir hata sonucu kullanılamaz hale gelen bir Terra Pad 1062 tabletin, sistematik arıza tespiti, onarımı ve bir dizi donanımsal/yazılımsal modifikasyonla modern, çok yönlü bir cihaza dönüştürülmesi sürecini adım adım belgelemektedir.

Bu rehber, benzer cihazlara sahip olan veya donanım modifikasyon projelerine ilgi duyanlar için teknik bir başvuru kaynağı olarak tasarlanmıştır.

**UYARI:** Bu rehberdeki işlemler bilgi ve tecrübe gerektirir. Cihazınıza kalıcı hasar verebilirsiniz ve garantiyi geçersiz kılabilirsiniz. Tüm sorumluluk size aittir.

---

## Projenin Ana Hatları

Bu proje, bir cihazın yeniden doğuşunu anlatan 4 ana bölümden oluşmaktadır:

### **[Bölüm I: Onarım ve Diriliş](./docs/1_Repair_and_Resurrection.md)**
Cihazı kullanılamaz hale getiren UEFI/BIOS hatasının kanıta dayalı tespiti ve tek bir USB portu kısıtlamasıyla BIOS'un yeniden flash'lanması.

### **[Bölüm II: Donanımsal Evrim](./docs/2_Hardware_Evolution.md)**
Cihazın orijinal 5-pinli Pogo-Pin portunun tersine mühendislikle USB portuna dönüştürülmesi, ses sisteminin yükseltilmesi ve diğer mekanik iyileştirmeler.

### **[Bölüm III: Yazılım ve Optimizasyon](./docs/3_Software_and_Optimization.md)**
Linux maceralarından sonra Windows 10'da karar kılınması ve düşük güçlü donanımda akıcı bir deneyim sağlayan kritik yazılım seçimleri.

### **[Bölüm IV: Sınırların Ötesi - Yeni Yetenekler](./docs/4_Beyond_The_Limits.md)**
Onarılan tabletin dönüştüğü araçlar:
*   **Taşınabilir İkinci Ekran:** Space Desk ile kablosuz bir kodlama monitörü.
*   **Gitar Amfi Prosesörü:** Özel donanım ve FlexASIO ile gecikmesiz bir müzik stüdyosu.
*   **Mobil İş İstasyonu:** Proteus gibi ağır yazılımları bile çalıştırabilen bir sistem.

---

## Teşekkür

Bu projenin başlangıç noktasındaki değerli yardımlarından dolayı Wortmann AG'den **Dennis Sudermann**'a teşekkürler.
