# Bölüm I: UEFI/BIOS Onarımı

Proje, başarısız bir alternatif işletim sistemi (Brunch OS) kurulumu sonrası başladı. Cihaz, Windows kurulumunu tamamlayamıyor ve sürekli "Otomatik Onarım" ekranına ya da doğrudan UEFI Shell'e düşüyordu. Cihaz "brick" olmuştu.

## Arıza Tespiti: Kanıta Dayalı Analiz

Sorunun kaynağını bulmak için basit bir mantık izledim: Sorun donanımda mı, yazılımda mı?

| Linux Çekirdeğinin Gördüğü | UEFI Firmware'inin Göremediği |
| :---: | :---: |
| Bir Linux Mint Live USB'si ile sistemi başlattığımda, `GParted` uygulaması tabletin 64GB'lık eMMC depolamasını sorunsuz bir şekilde tanıdı. Bu, çipin fiziksel olarak sağlam olduğunun kesin bir kanıtıydı. | UEFI Shell ekranında ise, `map -r` komutu hiçbir depolama aygıtı (`blkX`) listelemiyordu. Bu durum, tabletin kendi beyni olan UEFI'nin, fiziksel olarak sağlam olan belleği tanıyamadığını gösteriyordu. |
| <img src="../assets/images/thumbnail_17477595295231327780041398629873.jpg.jpg" width="350"> | <img src="../assets/images/Outlook-qgcwu443.png" width="350"> |
| **Teşhis:** Sorun, eMMC çipinde değil; UEFI firmware'inde veya NVRAM'deki bir bozulmadaydı. |

## Çözüm: Tek Port Kısıtlamasını Aşmak

Bu net kanıtlarla durumu Wortmann AG teknik desteğine ilettiğimde, sorunun bilinen bir durum olduğunu ve çözümün BIOS'un yeniden flash'lanması olduğunu teyit ettiler. Gerekli BIOS dosyasını ve talimatları paylaştılar.

Ancak ortada ciddi bir donanımsal kısıtlama vardı: Cihazdaki **tek bir USB portu**. Flash'lama işlemi için hem komutları yazacak bir USB klavyeye hem de dosyaları tutan bir USB belleğe aynı anda ihtiyaç vardı.

Bu sorunu aşmak için aşağıdaki adımları izleyen bir yöntem geliştirdim:

1.  **Komutu Hafızaya Almak:** Önce USB klavyeyi taktım. EFI Shell'e `Flash.nsh` komutunu yazıp (hata vermesini önemsemeden) Enter'a bastım. Bu, komutu Shell'in geçici geçmiş hafızasına kaydetti.
2.  **Cihazları Değiştirmek:** Klavyeyi çıkarıp, içinde BIOS dosyaları olan USB belleği taktım.
3.  **Komutu Geri Çağırmak:** Klavye olmadan, tabletin fiziksel **Ses Açma/Kısma tuşlarını** kullanarak komut geçmişinde gezindim. `Flash.nsh` komutu ekranda yeniden belirdiğinde, **Güç Tuşuna** bir kez basarak (Enter işlevi görür) komutu çalıştırdım.

Bu alışılmadık yöntem sayesinde flash'lama işlemi başarıyla tamamlandı ve tabletin beyni, unuttuğu belleğini yeniden tanıdı.

### Gerekli Dosyalar

*   **Terra Pad 1062 BIOS Dosyası:** Üreticinin sağladığı BIOS flash dosyasına aşağıdaki linkten ulaşabilirsiniz.
    *   [FLASH.zip İndirme Linki](http://drive.wortmann.de/files/1749018331/FLASH.zip)
    *   **Uyarı:** BIOS güncellemesi riskli bir işlemdir. Bu dosyayı kullanmanın tüm sorumluluğu size aittir. İşlem sırasında cihazın gücünün kesilmediğinden emin olun.
