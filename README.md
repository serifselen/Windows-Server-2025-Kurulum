# 🚀 Windows Server 2025 Kurulum Rehberi

> **Not:** Bu rehber, **Windows Server 2025 Technical Preview** sürümü için hazırlanmıştır. Resmi sürüm henüz yayımlanmamıştır (2023 itibarıyla).

---

## 🔧 Adım 1: VMware Başlangıç Ekranı
![Adım 1: VMware Başlangıç Ekranı](Images/1.png)

**Açıklama:**  
Bu ekran, **VMware Workstation Pro 17** başlangıç arayüzünü gösterir. Sol tarafta "Library" paneli, ortada ise 3 temel seçenek bulunur:
- `Create a New Virtual Machine` (Yeni Sanal Makine Oluştur)
- `Open a Virtual Machine` (Mevcut Sanal Makineyi Aç)
- `Connect to a Remote Server` (Uzak Sunucuya Bağlan)

**Nasıl Devam Edilir?**  
- `Create a New Virtual Machine` butonuna tıklayın.
- Kurulum sihirbazı açılacaktır → Sonraki adımda ISO dosyası ekleyeceğiz.

> 💡 **Blog İpucu:**  
> Okuyuculara "Neden bu adımı yaptık?" sorusuna cevap verin. Örneğin:  
> "Sanal makine oluşturmadan önce, Windows Server 2025'in çalışacağı izole bir ortam gereklidir. VMware bu izolasyonu sağlar."

---

## 🔧 Adım 2: Kurulum Tipi Seçimi
![Adım 2: Kurulum Tipi Seçimi](Images/2.png)

**Açıklama:**  
"Create a New Virtual Machine" seçeneği tıklandıktan sonra **"New Virtual Machine Wizard"** açılır. Burada kurulum tipini seçeceğiz.

**Nasıl Devam Edilir?**  
- `Typical (Recommended)` seçeneğini işaretleyin.
- **Next** butonuna tıklayın.

> ⚠️ **Önemli Uyarı:**  
> İleri düzey kullanıcılar için `Custom (Advanced)` seçeneği, disk sürücü ayarlarını özelleştirmenize izin verir.

---

## 🔧 Adım 3: ISO Dosyası Seçimi
![Adım 3: ISO Dosyası Seçimi](Images/3.png)

**Açıklama:**  
Bu adımda, Windows Server 2025 kurulum dosyası olan **ISO** dosyasını ekleyeceğiz.

**Nasıl Devam Edilir?**  
- `Installer disc image file (iso)` seçeneğini işaretleyin.
- **Browse** butonuna tıklayıp indirdiğiniz ISO dosyasını seçin.
- **Next** butonuna tıklayın.

> 📌 **Önemli Not:**  
> ISO dosyasını henüz indirmediyseniz, Microsoft'un resmi [Insider Program](https://insider.windows.com/) sayfasından indirebilirsiniz.

---

## 🔧 Adım 4: İşletim Sistemi Seçimi
![Adım 4: İşletim Sistemi Seçimi](Images/4.png)

**Açıklama:**  
Windows Server 2025 için **"Microsoft Windows"** ve sürüm seçimi yapılır.

**Nasıl Devam Edilir?**  
- `Guest OS version` kısmından  
- **"Windows Server 2025"** seçeneğini işaretleyin.
- **Next** butonuna tıklayın.

> 💡 **Blog İpucu:**  
> Sürüm seçimi yanlış yapılacak olursa, sanal makine performansı etkilenebilir. Daima en uygun sürümü seçin!

---

## 🔧 Adım 5: Sanal Makine İsmi Verme
![Adım 5: Sanal Makine İsmi](Images/5.png)

**Açıklama:**  
Sanal makinenizin adını ve depolanacağı klasörü seçtiğiniz ekran.

**Nasıl Devam Edilir?**  
- **Virtual machine name** kısmına  
- `Windows-Server-2025` yazın.
- **Browse** ile kaydedilecek klasörü seçin.
- **Next** butonuna tıklayın.

> 📁 **Organizasyon Tavsiyesi:**  
> Tüm sanal makineler için ayrı bir klasör oluşturun (Örn: `C:\VMs\Windows-Server-2025`).

---

## 🔧 Adım 6: Disk Kapasitesi Ayarlama
![Adım 6: Disk Boyutu Ayarlama](Images/6.png)

**Açıklama:**  
Windows Server 2025'in çalışacağı sanal diskin boyutunu ayarladığınız ekran.

**Nasıl Devam Edilir?**  
- **Maximum disk size** kısmına  
- `120 GB` girin (en az).
- `Split virtual disk into multiple files` seçeneğini işaretleyin.
- **Next** butonuna tıklayın.

> ⚙️ **Teknik Detay:**  
> Disk boyutunu artırmanız, future-proof (geleceğe dönük) bir kurulum sağlar. 50 GB minimum, 120 GB idealdir.

---

## 🔧 Adım 7: Sanal Makine Donanım Ayarları
![Adım 7: Sanal Makine Donanım Ayarları](Images/7.png)

**Açıklama:**  
Sonraki adımlarda **RAM, işlemci çekirdeği** ve ağ ayarları özelleştirilecektir.

**Nasıl Devam Edilir?**  
- `Customize Hardware` butonuna tıklayın.
- Aşağıdaki ayarları yapın:  
  - **Memory:** 4096 MB (4 GB)  
  - **Processors:** 2 çekirdek  
  - **Network Adapter:** NAT  

> 🖥️ **Performans İpucu:**  
> 8 GB RAM ve 4 çekirdek, production ortamları için önerilir. Test ortamlarında 4 GB yeterlidir.

---

## 🔧 Adım 8: Windows Dil ve Zaman Ayarları
![Adım 8: Dil ve Zaman Ayarları](Images/8.png)

**Açıklama:**  
Kurulum başlatıldıktan sonra ilk açılış ekranı.

**Nasıl Devam Edilir?**  
- **Language** ve  
- **Time** ayarlarını seçin.
- **Next** butonuna tıklayın.

> 🌍 **Dil Seçimi Tavsiyesi:**  
> Türkçe seçerseniz, kurulum daha anlaşılır olacaktır. Ancak enterprise ortamlarda İngilizce tercih edilir.

---

## 🔧 Adım 9: Klavye Dil Seçimi
![Adım 9: Klavye Dil Seçimi](Images/9.png)

**Açıklama:**  
Klavye düzenini seçtiğiniz ekran.

**Nasıl Devam Edilir?**  
- Tercih ettiğiniz klavye düzenini seçin (Örn: "US" veya "Turkish").
- **Next** butonuna tıklayın.

> ⌨️ **Tavsiye:**  
> Genellikle "US" klavye düzeni tercih edilir, ancak Türkçe karakterler için "Turkish" seçeneğini tercih edebilirsiniz.

---

## 🔧 Adım 10: Lisans Anahtarı Girişi
![Adım 10: Lisans Anahtarı Girişi](Images/10.png)

**Açıklama:**  
Windows Server 2025 için lisans anahtarı isteyen ekran.

**Nasıl Devam Edilir?**  
- **"I don't have a product key"** seçeneğini işaretleyin (Technical Preview için gereklidir).
- **Next** butonuna tıklayın.

> ⚠️ **Önemli Uyarı:**  
> Technical Preview sürümlerinde lisans anahtarı gerekmez. Üretim ortamları için resmi lisans gereklidir.

---

## 🔧 Adım 11: Kurulum Türü Seçimi
![Adım 11: Kurulum Türü Seçimi](Images/11.png)

**Açıklama:**  
Kurulum türünü seçtiğiniz ekran.

**Nasıl Devam Edilir?**  
- **"Windows Server 2025 Standart Evalution (Desktop Experience)"** seçeneğini işaretleyin.
- **Next** butonuna tıklayın.

> 💡 **Neden Desktop Experience?**  
> "Desktop Experience" seçeneği, alışık olduğumuz windows masaüstü arayüzüne erişim sağlayıp kullanımı kolaylaştırdığı için tercih edilmelidir.

---

## 🔧 Adım 12: Disk Bölümleme
![Adım 12: Disk Bölümleme](Images/12.png)

**Açıklama:**  
Sanal diski bölümleyeceğiniz ekran.

**Nasıl Devam Edilir?**  
- **Disk 0** diske tıklayarak bölümleme işlemini tamamlayın.
- **Next** butonuna tıklayın.

> ⚠️ **Dikkat Edilmesi Gerekenler:**  
> - Disk boyutu 100 GB olarak ayarlanmış olmalı.  
> - "Format" işlemi otomatik olarak yapılır.

---

## 🔧 Adım 13: Kurulum Süreci
![Adım 13: Kurulum Süreci](Images/13.png)

**Açıklama:**  
Windows Server 2025 kurulumunun devam ettiği ekran.

**Nasıl Devam Edilir?**  
- Kurulum otomatik olarak ilerleyecektir.
- Sanal makine birkaç kez yeniden başlayacaktır.

> ⏱️ **Tahmini Süre:**  
> Kurulum 20-30 dakika sürecektir. Süre, sanal makine kaynaklarına göre değişebilir.

---

## 🔧 Adım 14: Yönetici Hesap Oluşturma
![Adım 14: Yönetici Hesap Oluşturma](Images/14.png)

**Açıklama:**  
Yönetici hesabını oluşturduğunuz ekran.

**Nasıl Devam Edilir?**  
- **Password** kısmına güçlü bir şifre girin.
- **Finish** butonuna tıklayın.

> 🔒 **Şifre Güvenliği:**  
> Şifrenizde büyük harf, rakam ve sembol kullanın (Örn: `P@ssw0rd!2025`).

---

## 🔧 Adım 15: Tanımlama verilerini Microsota Gönderin!
![Adım 15: Tanımlama verileri](Images/15.png)

**Açıklama:**  
Son olarak server içerisinde tanımlmala verilerini Microsota gönderme seçenekleri çıkmaktadır.

**Nasıl Devam Edilir?**  
- **Required only** seçilerek ilgili verilen gitmemesi seçilir.
- **Accept** seçilerek kurulum tamamlanır.

> 🎉 **Tebrikler!**  
> Windows Server 2025 kurulumu başarıyla tamamlandı. Artık Windows Server 2025 üzerinde testlerinizi gerçekleştirebilirsiniz.  

**#WindowsServer2025 #VMware #SanalMakine #BlogRehberi**