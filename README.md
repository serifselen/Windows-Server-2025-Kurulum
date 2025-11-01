# VMware Workstation Pro 17 ile Windows Server 2025 Kurulum Rehberi

## Giriş

VMware Workstation Pro 17, gelişmiş sanallaştırma çözümleri sunan güçlü bir yazılımdır. Bu adım adım rehberde, VMware Workstation Pro 17 kullanarak Windows Server 2025 işletim sistemini nasıl kuracağınızı anlatacağız.

---

## Bölüm 1: Sanal Makine Oluşturma

### 1. Adım: VMware Workstation Pro 17'yi Başlatma
- VMware Workstation Pro 17'yi açın
- "Create a New Virtual Machine" seçeneğini tıklayın

### 2. Adım: Yapılandırma Türünü Seçme
- "Typical (recommended)" seçeneğini seçin
- "Next" butonuna tıklayın

### 3. Adım: Kurulum Yöntemini Belirleme
- "Installer disc image file (iso)" seçeneğini işaretleyin
- "Browse" butonu ile Windows Server 2025 ISO dosyasını seçin

### 4. Adım: İşletim Sistemi Seçimi
- Guest operating system: "Microsoft Windows"
- Version: "Windows Server 2025"

### 5. Adım: Sanal Makine Bilgileri
- Virtual machine name: `SerifSelen`
- Location: `C:\Users\PC\Documents\Virtual Machines\SerifSelen`

---

## Bölüm 2: Donanım Yapılandırması

### 6. Adım: Disk Ayarları
- Maximum disk size: 100 GB
- "Split virtual disk into multiple files" seçeneğini seçin

### 7. Adım: Donanım Özeti
- Memory: 2 GB
- Processors: 1
- Hard Disk: 100 GB
- Network Adapter: NAT
- CD/DVD: ISO dosyası bağlı ve "Connect at power on" işaretli

### 8. Adım: Dil ve Bölge Ayarları
- Language: English (United States)
- Time format: English (United States)

### 9. Adım: Klavye Ayarları
- Keyboard: Turkish Q

---

## Bölüm 3: Windows Server 2025 Kurulumu

### 10. Adım: İşletim Sistemi Sürümü
- "Windows Server 2025 Standard Evaluation (Desktop Experience)" seçin

### 11. Adım: Kurulum Onayı
- Seçimleri gözden geçirin
- "Install" butonuna tıklayın

### 12. Adım: Yönetici Şifresi
- Administrator hesabı için güçlü bir şifre belirleyin
- "Finish" butonuna tıklayın

### 13. Adım: Tanılama Verisi
- "Required only" seçeneğini seçin
- "Accept" butonuna tıklayın

---

## Kurulum Sonrası

- Değerlendirme sürümü 180 gün geçerlidir
- `slmgr.vbs /rearm` komutu ile süre uzatılabilir
- Sunucu Manager otomatik olarak başlayacaktır

---

*Bu rehber VMware Workstation Pro 17.5 veya üzeri sürümler için hazırlanmıştır.*