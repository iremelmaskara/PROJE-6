# PROJE-6
Bu proje, Tiva C serisi mikrodenetleyicisi (TM4C123GH6PM) kullanarak mikrodenetleyicinin saat ayarlarını yapılandırmayı sağlar. Kod, PLL (Phase-Locked Loop) yapılandırması ile sistemi 50 MHz hızına ayarlar.

Özellikler
Saat Yapılandırması: Mikrodenetleyicinin ana saat kaynağını 16 MHz kristal osilatöre ayarlayarak, sistem saatini 50 MHz'e çıkartır.
PLL Kullanımı: PLL modunu etkinleştirir ve sistem saati ayarlamaları yapar.

Yapılandırma ve Başlatma
Saat Ayarı:
Mikrodenetleyicinin saati 16 MHz kristal osilatör ile başlatılır.
PLL kullanılarak sistem saati 50 MHz'e çıkartılır.
PLL Modu:
PLL yapılandırması yapılarak, sistemin saati hızlandırılır.
Yapılandırma Adımları:
SYSCTL_RCC2_R ve SYSCTL_RCC_R register'ları üzerinden PLL ve saat kaynağı yapılandırması yapılır.
SYSCTL_RCC_R |= SYSCTL_RCC_BYPASS; komutu ile geçici olarak sistem saati devre dışı bırakılır ve PLL yapılandırılır.
SYSCTL_RCC_R |= SYSCTL_RCC_USESYSDIV; komutu ile PLL'den alınan sinyalin bölünmesi yapılır.
Çalışma Prensibi
PLL Yapılandırması: Sistemin saat kaynağı PLL kullanılarak değiştirilir. Başlangıçta 16 MHz kristal osilatör kullanılır.
Saat Hızı Ayarı: SYSCTL_RCC_R ve SYSCTL_RCC2_R register'ları ile 50 MHz sistem saati elde edilir.
BYPASS Modu Kapatılır: PLL ayarları tamamlandıktan sonra, SYSCTL_RCC_R &= ~SYSCTL_RCC_BYPASS; komutu ile BYPASS modu kapatılır ve PLL etkinleştirilir.
