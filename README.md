# Windows Server 2025 Kurulum Rehberi

Bu dokümanda Windows Server 2025'in VMware Workstation Pro 17 üzerinde kurulum adımları detaylı olarak açıklanmaktadır.

## İçindekiler

- [Adım 1: VMware Workstation Ana Ekran](#adım-1-vmware-workstation-ana-ekran)
- [Adım 2: Sanal Makine Sihirbazı - Konfigürasyon Tipi Seçimi](#adım-2-sanal-makine-sihirbazı---konfigürasyon-tipi-seçimi)
- [Adım 3: İşletim Sistemi Kurulum Kaynağı Seçimi](#adım-3-i̇şletim-sistemi-kurulum-kaynağı-seçimi)
- [Adım 4: İşletim Sistemi Seçimi](#adım-4-i̇şletim-sistemi-seçimi)
- [Adım 5: Sanal Makine Adlandırma ve Konum Belirleme](#adım-5-sanal-makine-adlandırma-ve-konum-belirleme)
- [Adım 6: Disk Kapasitesi Belirleme](#adım-6-disk-kapasitesi-belirleme)
- [Adım 7: Sanal Makine Ayarlarının Özeti](#adım-7-sanal-makine-ayarlarının-özeti)
- [Adım 8: Windows Server Kurulum - Dil Ayarları](#adım-8-windows-server-kurulum---dil-ayarları)
- [Adım 9: Klavye Ayarları](#adım-9-klavye-ayarları)
- [Adım 10: Kurulum Seçenekleri](#adım-10-kurulum-seçenekleri)
- [Adım 11: Kurulum İmajı Seçimi](#adım-11-kurulum-i̇majı-seçimi)
- [Adım 12: Kurulum Konumu Seçimi](#adım-12-kurulum-konumu-seçimi)
- [Adım 13: Kurulum Onayı](#adım-13-kurulum-onayı)
- [Adım 14: Administrator Şifresi Belirleme](#adım-14-administrator-şifresi-belirleme)
- [Adım 15: Tanılama Verileri Paylaşımı](#adım-15-tanılama-verileri-paylaşımı)

---

## Adım 1: VMware Workstation Ana Ekran

![Adım 1](Images/1.png)

VMware Workstation Pro 17 açıldığında karşımıza gelen ana ekrandır. Bu ekranda üç temel seçenek bulunmaktadır:

- **Create a New Virtual Machine**: Yeni bir sanal makine oluşturmak için kullanılır
- **Open a Virtual Machine**: Mevcut bir sanal makineyi açmak için kullanılır
- **Connect to a Remote Server**: Uzak bir sunucuya bağlanmak için kullanılır

> 💡 Yeni bir Windows Server 2025 kurulumu için **"Create a New Virtual Machine"** seçeneğine tıklayınız.

---

## Adım 2: Sanal Makine Sihirbazı - Konfigürasyon Tipi Seçimi

![Adım 2](Images/2.png)

New Virtual Machine Wizard açılır. Bu ekranda iki konfigürasyon seçeneği sunulmaktadır:

### Typical (recommended) - Önerilen
- Önerilen ayarlarla hızlı kurulum yapar
- Workstation 17.5 veya üzeri bir sanal makine oluşturur
- Birkaç kolay adımda kurulum tamamlanır

### Custom (advanced) - Gelişmiş
- Gelişmiş seçenekler sunar
- SCSI denetleyici tipi, sanal disk tipi gibi detaylı ayarları yapılandırmanıza olanak tanır
- Eski VMware ürünleriyle uyumluluk için kullanılabilir

> ✅ Bu rehberde **"Typical (recommended)"** seçeneği ile devam edilmektedir. **"Next"** butonuna tıklayınız.

---

## Adım 3: İşletim Sistemi Kurulum Kaynağı Seçimi

![Adım 3](Images/3.png)

Guest Operating System Installation ekranında işletim sisteminin nasıl yükleneceği belirlenir. Üç seçenek mevcuttur:

### Kurulum Seçenekleri

1. **Installer disc**: Fiziksel sürücüden kurulum yapar
   - "No drives available" görünüyorsa fiziksel medya takılı değildir

2. **Installer disc image file (iso)**: ISO dosyası kullanarak kurulum yapar
   - Örnekte: `C:\Users\PC\Downloads\Windows Server 2025.iso` dosya yolu belirtilmiştir

3. **I will install the operating system later**: Sanal makine boş sabit diskle oluşturulur
   - İşletim sistemi daha sonra manuel olarak kurulur

> ✅ **"I will install the operating system later"** seçeneğini işaretleyiniz. Bu seçenek, sanal makinenin boş bir sabit diskle oluşturulmasını ve işletim sisteminin manuel olarak kurulmasını sağlar. **"Next"** butonuna tıklayınız.

---

## Adım 4: İşletim Sistemi Seçimi

![Adım 4](Images/4.png)

Select a Guest Operating System ekranında kurulacak işletim sisteminin türü seçilir.

### Guest operating system seçenekleri:
- Microsoft Windows
- Linux
- VMware ESX
- Other

### Yapılacaklar:
1. **Microsoft Windows** seçeneğini işaretleyiniz
2. **Version** açılır menüsünden **"Windows Server 2025"** seçimini yapınız

> ⚠️ Listede çok sayıda Windows sürümü bulunmaktadır (Windows 10, 8.x, 7, Vista, XP ve çeşitli Windows Server sürümleri). Doğru sürümü seçtiğinizden emin olunuz.

**"Next"** butonuna tıklayınız.

---

## Adım 5: Sanal Makine Adlandırma ve Konum Belirleme

![Adım 5](Images/5.png)

Name the Virtual Machine ekranında sanal makinenin adı ve dosyalarının saklanacağı konum belirlenir.

### Yapılandırma:

**Virtual machine name**: `SerifSelen`
- Bu ismi kendi tercihlerinize göre değiştirebilirsiniz

**Location**: `C:\Users\PC\Documents\Virtual Machines\SerifSelen`
- Varsayılan konum olarak belirlenmiştir
- "Browse..." butonuna tıklayarak farklı bir konum seçebilirsiniz

> 💡 Varsayılan konumun Edit > Preferences menüsünden değiştirilebileceği not olarak belirtilmiştir.

**"Next"** butonuna tıklayınız.

---

## Adım 6: Disk Kapasitesi Belirleme

![Adım 6](Images/6.png)

Specify Disk Capacity ekranında sanal makinenin sabit disk boyutu yapılandırılır.

### Disk Ayarları:

**Maximum disk size (GB)**: `100 GB`
- Windows Server 2025 için önerilen boyut: **60 GB**

### Depolama Türü:

Sanal makinenin sabit diski, host bilgisayarın fiziksel diskinde bir veya daha fazla dosya olarak saklanır. Bu dosyalar küçük başlar ve sanal makineye uygulama, dosya ve veri ekledikçe büyür.

#### Seçenekler:

1. **Store virtual disk as a single file** ✅ (Önerilen)
   - Disk tek bir dosya olarak saklanır

2. **Split virtual disk into multiple files**
   - Disk birden fazla dosyaya bölünür
   - Sanal makineyi başka bir bilgisayara taşımayı kolaylaştırır
   - Çok büyük disklerle performansı düşürebilir

> ✅ **"Store virtual disk as a single file"** seçeneği işaretli bırakılmalıdır. **"Next"** butonuna tıklayınız.

---

## Adım 7: Sanal Makine Ayarlarının Özeti

![Adım 7](Images/7.png)

Virtual Machine Settings ekranında oluşturulan sanal makinenin donanım özellikleri görüntülenir.

### Donanım Listesi:

| Donanım | Değer |
|---------|-------|
| Memory | 2 GB |
| Processors | 1 |
| Hard Disk (NVMe) | 100 GB |
| CD/DVD (SATA) | Auto detect |
| Network Adapter | NAT |
| USB Controller | Present |
| Sound Card | Auto detect |
| Display | Auto detect |

### CD/DVD Ayarları:

**Device status:**
- ☐ Connected
- ☑ Connect at power on

**Connection:**
- ☐ Use physical drive: Auto detect
- ☑ **Use ISO image file**: `C:\Users\PC\Downloads\Windows Server 2025.iso`

> ⚠️ ISO dosyasının doğru yolda olduğundan emin olunuz. "Browse..." butonu ile farklı bir ISO dosyası seçilebilir.

**"OK"** butonuna tıklayarak sanal makine oluşturma işlemini tamamlayınız.

---

## Adım 8: Windows Server Kurulum - Dil Ayarları

![Adım 8](Images/8.png)

Sanal makine başlatıldığında Windows Server Setup ekranı açılır.

### Select language settings

Üç seçenek bulunur:

1. **Language to install**: `English (United States)`
   - Kurulacak işletim sisteminin dili

2. **Time and currency format**: `English (United States)`
   - Saat ve para birimi formatı

> 💡 Her iki açılır menüden de tercih ettiğiniz dil ve bölge ayarlarını seçebilirsiniz.

Ekranın alt kısmında Microsoft logosu ile birlikte **Support** ve **Legal** linkleri bulunmaktadır.

Ayarlarınızı yaptıktan sonra **"Next"** butonuna tıklayınız.

---

## Adım 9: Klavye Ayarları

![Adım 9](Images/9.png)

Select keyboard settings ekranında klavye düzeni seçilir.

### Klavye Düzeni:

**Keyboard or input method**: `Turkish Q`

> 💡 Kullanacağınız klavye düzenine göre bu ayarı yapılandırabilirsiniz. Türkçe Q klavye, Türkiye'de standart olarak kullanılan klavye düzenidir.

**"Next"** butonuna tıklayarak devam ediniz.

---

## Adım 10: Kurulum Seçenekleri

![Adım 10](Images/10.png)

Select setup option ekranında iki temel seçenek sunulmaktadır:

### I would like to:

1. ☑ **Install Windows Server**
   - Windows Server'ın en son sürümünü kurmak veya PC'nizi onarmak için kullanılır
   - ⚠️ Kurulum yapılırsa tüm dosyalar, uygulamalar ve ayarlar silineceği konusunda uyarı verilmektedir

2. ☐ **Repair my PC**
   - PC'nizi onarmak için kullanılır

### Önemli Onay:

☑ **"I agree everything will be deleted including files, apps, and settings"**

> ⚠️ Bu önemli bir onay kutusudur ve devam etmeden önce mutlaka işaretlenmelidir.

Ekranın alt kısmında "Previous Version of Setup" linki bulunmaktadır.

Yeni bir kurulum için **"Install Windows Server"** seçili kalmalı ve onay kutusu işaretlenmelidir. **"Next"** butonuna tıklayınız.

---

## Adım 11: Kurulum İmajı Seçimi

![Adım 11](Images/11.png)

Select Image ekranında kurulacak Windows Server 2025 sürümü seçilir.

### Operating System Seçenekleri:

1. ☐ Windows Server 2025 Standard Evaluation
2. ☑ **Windows Server 2025 Standard Evaluation (Desktop Experience)**
3. ☐ Windows Server 2025 Datacenter Evaluation
4. ☐ Windows Server 2025 Datacenter Evaluation (Desktop Experience)

### Desktop Experience Hakkında:

**Desktop Experience** sürümleri, tam grafik arayüzlü Windows masaüstü ortamı sunar.

**Özellikler:**
- ✅ Tam Windows grafik arayüzü
- ⚠️ Ekstra disk alanı kullanır
- ✅ Windows masaüstünü kullanmak için idealdir
- ✅ Masaüstü gerektiren uygulamalar için gereklidir

> 💡 "This option installs the full Windows graphical environment, consuming extra drive space. It can be useful if you want to use the Windows desktop or have an app that requires it."

Grafik arayüze ihtiyacınız varsa **"Windows Server 2025 Standard Evaluation (Desktop Experience)"** seçimini yapınız. **"Next"** butonuna tıklayınız.

---

## Adım 12: Kurulum Konumu Seçimi

![Adım 12](Images/12.png)

Select location to install Windows Server ekranında işletim sisteminin kurulacağı disk belirlenir.

### Araç Çubuğu:

Ekranın üst kısmında altı araç butonu bulunmaktadır:

| İkon | İşlev | Açıklama |
|------|-------|----------|
| 🔄 | Refresh | Disk listesini yeniler |
| 💿 | Load Driver | Sürücü yükler |
| 🌐 | Bring Disk Online | Diski çevrimiçi yapar |
| ❌ | Delete Partition | Bölümü siler |
| 📝 | Format Partition | Bölümü formatlar |
| ➕ | Create Partition | Yeni bölüm oluşturur |
| ↔️ | Extend Partition | Bölümü genişletir |

### Disk Listesi:

| Name | Total Size | Free Space | Type |
|------|------------|------------|------|
| Disk 0 Unallocated Space | 100.0 GB | 100.0 GB | Unallocated Space |

> 💡 Disk henüz bölümlenmemiş durumda (Unallocated Space). Kuruluma devam etmek için bu disk seçili olmalıdır.

**"Next"** butonuna tıklayınız. Kurulum otomatik olarak gerekli bölümleri oluşturacaktır.

---

## Adım 13: Kurulum Onayı

![Adım 13](Images/13.png)

Ready to install ekranında kurulum öncesi son onay verilir.

### To recap, you've chosen to:

Seçilen kurulum özeti:

- ✅ **Install Windows Server 2025 Standard Evaluation (Desktop Experience)**
- ✅ **Keep nothing**

### ⚠️ Önemli Uyarı:

> "PC'nizi kurulum sırasında kullanamayacaksınız. Başlamadan önce dosyalarınızı kaydetmeniz ve kapatmanız önerilmektedir."

### Butonlar:

- **Back**: Geri dön
- **Install**: Kurulumu başlat

> 🚀 Tüm ayarları kontrol ettikten sonra **"Install"** butonuna tıklayarak kurulumu başlatınız. Bu noktadan sonra kurulum işlemi başlayacak ve geri dönüş mümkün olmayacaktır.

---

## Adım 14: Administrator Şifresi Belirleme

![Adım 14](Images/14.png)

Customize settings ekranında yerleşik yönetici hesabı için şifre belirlenir.

### Açıklama:

"Type a password for the built-in administrator account that you can use to sign in to this computer."

### Form Alanları:

| Alan | Değer |
|------|-------|
| **User name** | Administrator (otomatik, değiştirilemez) |
| **Password** | Şifrenizi giriniz (gizli) |
| **Reenter password** | Şifrenizi tekrar giriniz |

### 🔒 Önemli Güvenlik Notları:

- ✅ Güçlü bir şifre seçiniz (büyük/küçük harf, rakam ve özel karakter içermeli)
- ✅ Şifreyi güvenli bir yerde saklayınız
- ⚠️ Bu hesap tam yönetici yetkilerine sahiptir

> 💡 Sol alt köşede dönen yükleme ikonu görünmektedir, bu kurulumun devam ettiğini gösterir.

Şifrenizi girdikten sonra **"Finish"** butonuna tıklayınız.

---

## Adım 15: Tanılama Verileri Paylaşımı

![Adım 15](Images/15.png)

Send diagnostic data to Microsoft ekranında gizlilik ve tanılama ayarları yapılandırılır.

### Açıklama:

Ayarlarınızı seçin, ardından kaydetmek için **Accept**'i seçin. Bu ayarlar hakkında bilgi, nasıl değiştirileceği, Windows'un güvenli olmayan uygulamalar ve web içeriğinden nasıl korunduğu ve ilgili veri aktarımları hakkında **Learn more** linkinden bilgi edinilebilir.

### Seçenekler:

#### 1. ☑ Required only (Yalnızca Gerekli) - Seçili

**Ne gönderilir:**
- Yalnızca cihazınız, ayarları ve yetenekleri hakkında bilgi
- Doğru çalışıp çalışmadığı kontrol edilir

**Amaç:**
- Windows'u güvenli ve güncel tutmak
- Sorunları gidermek
- Ürün iyileştirmeleri yapmak

> ✅ Seçiminiz ne olursa olsun, cihazınız eşit derecede güvenli olacak ve normal şekilde çalışacaktır.

#### 2. ☐ Required and optional

- Gerekli tanılama verilerine ek olarak isteğe bağlı veriler de gönderilir

### Butonlar:

- **Learn more**: Daha fazla bilgi
- **Accept**: Kabul et ve devam et

Tercihinize göre seçim yapıp **"Accept"** butonuna tıklayınız. Kurulum tamamlanacak ve Windows Server 2025 kullanıma hazır hale gelecektir.

---

## 🎉 Kurulum Tamamlandı

Bu adımları tamamladıktan sonra Windows Server 2025 sisteminiz kullanıma hazır olacaktır. İlk oturum açmanızda belirlediğiniz Administrator şifresi ile giriş yapabilirsiniz.

### 📋 Kurulum Sonrası Öneriler:

1. **Windows Update**: Windows Update'i çalıştırarak sistem güncellemelerini yükleyiniz
2. **VMware Tools**: VMware Tools'u yükleyerek sanal makine performansını iyileştiriniz
3. **Güvenlik**: Güvenlik duvarı ve ağ ayarlarını yapılandırınız
4. **Roller ve Özellikler**: Gerekli sunucu rollerini ve özelliklerini yükleyiniz

---

## 📝 Doküman Bilgileri

| Bilgi | Değer |
|-------|-------|
| **Hazırlayan** | Serif SELEN |
| **Tarih** | 2 Kasım 2025 |
| **Platform** | VMware Workstation Pro 17 |
| **İşletim Sistemi** | Windows Server 2025 Standard Evaluation (Desktop Experience) |
| **Toplam Adım** | 15 |
| **Disk Boyutu** | 100 GB |
| **RAM** | 2 GB |

---

## 🔗 Faydalı Linkler

- [Microsoft Windows Server Dökümantasyonu](https://docs.microsoft.com/windows-server/)
- [VMware Workstation Pro Dökümantasyonu](https://docs.vmware.com/en/VMware-Workstation-Pro/)
- [Windows Server 2025 Yenilikler](https://docs.microsoft.com/windows-server/get-started/)

---

## 📄 Lisans

Bu doküman eğitim amaçlı hazırlanmıştır. Windows Server 2025 Evaluation sürümü 180 gün süreyle kullanılabilir.

---

**Son Güncelleme:** 2 Kasım 2025