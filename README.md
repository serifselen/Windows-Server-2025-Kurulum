# Windows Server 2025 Kurulum Rehberi — Adım Adım (Markdown)

Kısa açıklama: Aşağıdaki Markdown formatı, yükleme ekran görüntülerini (senin çektiğin görüntüler) her adımın altına ekleyebileceğin, doğrudan GitHub README veya blog postuna yapıştırılmaya hazır bir rehberdir. Her adımda ne yapıldığı, neden seçildiği ve dikkat edilmesi gereken noktalar kısa ve net şekilde verilmiştir.

---

## Gereksinimler
- **ISO dosyası**: Windows Server 2025 ISO (ör. C:\Users\PC\Downloads\Windows Server 2025.iso)  
- **Sanal makine yazılımı**: VMware Workstation Pro 17+  
- **Önerilen kaynaklar (test için)**: 2 vCPU, 4 GB RAM (GUI için 4–8 GB önerilir), 100 GB disk  
- **Network**: NAT (test) veya Bridged (lab/erişim için)  
- **Not**: Bu rehber test ortamı ve blog/GitHub paylaşımı amaçlıdır; üretim ortamında kaynakları ve yedekleme/klasör konumlarını ihtiyaca göre ayarlayın.

---

## Kurulum Adımları

#### Adım 1: VMware Workstation Pro Başlangıç
- Ne yapılır: VMware Workstation Pro açılır ve "Create a New Virtual Machine" seçilir.  
- Neden: Yeni bir VM oluşturmak için başlangıç ekranı.  
- Dikkat: VMware sürümünüzün 17+ olmasına dikkat edin.  
- Ekran görüntüsü: ![Adım 1 — VMware Ana Ekran](./screenshots/1-vmware-main.png)

#### Adım 2: New Virtual Machine Wizard — Typical vs Custom
- Ne yapılır: Wizard'da "Typical (recommended)" veya "Custom (advanced)" seçilir.  
- Neden: Typical hızlı ve modern uyumluluk için uygundur; özel SCSI/disk/uyumluluk gerekiyorsa Custom seçilir.  
- Dikkat: Eski VMware sürümleriyle uyumluluk gerekiyorsa Custom kullanın.  
- Ekran görüntüsü: ![Adım 2 — New VM Wizard](./screenshots/2-new-vm-wizard.png)

#### Adım 3: Guest Operating System Installation (ISO veya Sonra Kurulum)
- Ne yapılır: "Installer disc", "Installer disc image (ISO)" veya "I will install the operating system later" seçeneklerinden uygun olanı seçilir.  
- Neden: Hazır ISO varsa doğrudan bağlayarak kurulum hızlandırılır; ISO yoksa işletim sistemi daha sonra kurulabilir.  
- Dikkat: ISO yolunu doğru gösterin; görüntüdeki ISO farklı (Windows 11) ise Server ISO’su ile değiştirin.  
- Ekran görüntüsü: ![Adım 3 — Installation Method](./screenshots/3-guest-installation.png)

#### Adım 4: Select a Guest Operating System
- Ne yapılır: Misafir OS tipi olarak **Microsoft Windows** seçilir ve Version menüsünden **Windows Server 2025** seçilir.  
- Neden: Doğru guest seçimi, VMware Tools uyumluluğu ve varsayılan ayarların uygunluğu için önemli.  
- Dikkat: Yanlış sürüm seçimi performans veya araç uyumsuzluğu yaratabilir.  
- Ekran görüntüsü: ![Adım 4 — Select OS](./screenshots/4-select-guest-os.png)

#### Adım 5: Name the Virtual Machine
- Ne yapılır: VM adı (ör. `SerifSelen`) ve VM dosya konumu seçilir.  
- Neden: Anlaşılır isimlendirme ileride yönetimi kolaylaştırır; konum yedekleme/taşıma açısından önemlidir.  
- Dikkat: Disk alanı yeterli olan bir klasör seçin.  
- Ekran görüntüsü: ![Adım 5 — Name VM](./screenshots/5-name-vm.png)

#### Adım 6: Specify Disk Capacity
- Ne yapılır: Maksimum disk boyutu (ör. 100 GB) girilir; "Split virtual disk into multiple files" veya "Store as a single file" seçilir.  
- Neden: Disk boyutu ve biçimi performans ve taşınabilirlik üzerinde etkili olur.  
- Dikkat: GUI (Desktop Experience) kullanacaksanız en az 60 GB planlayın; performans için tek dosya tercih edilebilir.  
- Ekran görüntüsü: ![Adım 6 — Disk Capacity](./screenshots/6-specify-disk.png)

#### Adım 7: Virtual Machine Settings — Donanım Özeti ve ISO Bağlama
- Ne yapılır: Bellek, CPU, disk tipi, network ve CD/DVD ayarlarını gözden geçirip ISO'yu CD/DVD sürücüsüne bağlayın (Use ISO image file).  
- Neden: Kurulumun başarılı olması için ISO bağlanmalı ve kaynaklar yeterli olmalı.  
- Dikkat: "Connect at power on" seçeneğini işaretleyin; bellek/CPU değerlerini ihtiyaçlara göre ayarlayın.  
- Ekran görüntüsü: ![Adım 7 — VM Settings](./screenshots/7-vm-settings.png)

#### Adım 8: Windows Server Setup — Dil ve Bölge Ayarları
- Ne yapılır: "Select language settings" ekranında **Language to install** ve **Time and currency format** seçilir (ör. English (United States)).  
- Neden: Kurulum ekranlarının dili ve bölgesel formatlar bu ayara bağlıdır.  
- Dikkat: Blogda hangi dili kullandığınızı not edin; ekran görüntüleri bu dile göre olacaktır.  
- Ekran görüntüsü: ![Adım 8 — Language Settings](./screenshots/8-language-settings.png)

#### Adım 9: Windows Server Setup — Klavye Ayarı
- Ne yapılır: "Keyboard or input method" seçilir (ör. Turkish Q).  
- Neden: Kurulum sırasındaki şifre ve lokal girişlerde doğru karakterler için önemlidir.  
- Dikkat: Remote yönetim/console erişimde klavye düzeni sorunlarına dikkat.  
- Ekran görüntüsü: ![Adım 9 — Keyboard Settings](./screenshots/9-keyboard-settings.png)

#### Adım 10: Install veya Repair Seçimi
- Ne yapılır: "Install Windows Server" seçilir.  
- Neden: Yeni kurulum için bu seçenek kullanılır; Repair yalnızca onarım içindir.  
- Dikkat: İleri adımda "everything will be deleted" benzeri uyarılar çıkabilir; doğru disk seçildiğinden emin olun.  
- Ekran görüntüsü: ![Adım 10 — Install or Repair](./screenshots/10-install-or-repair.png)

#### Adım 11: Select Image / Edition Seçimi
- Ne yapılır: Kurulacak edition seçilir (ör. **Windows Server 2025 Standard Evaluation (Desktop Experience)**).  
- Neden: Desktop Experience GUI ekler; test veya GUI ihtiyaçlarınız varsa seçin.  
- Dikkat: Evaluation sürümleri süre sınırlıdır; lisans planını unutmadan not alın.  
- Ekran görüntüsü: ![Adım 11 — Select Edition](./screenshots/11-select-edition.png)

#### Adım 12: Disk Seçimi ve Bölümlendirme
- Ne yapılır: Hedef disk seçilir, gerekiyorsa yeni bölüm oluşturulur veya formatlama yapılır.  
- Neden: Kurulacak OS'nin hangi partitiona yazılacağı burada belirlenir.  
- Dikkat: Doğru diski seçin; "Unallocated" alan üzerinde New -> Format yaparak ilerleyin.  
- Ekran görüntüsü: ![Adım 12 — Disk Selection](./screenshots/12-disk-selection.png)

#### Adım 13: Ready to install — Özet ve Başlat
- Ne yapılır: Seçimler özetlenir; "Install" butonuna basılarak kurulum başlatılır.  
- Neden: Son doğrulama adımıdır.  
- Dikkat: Özet ekranını kontrol edin; yanlış edition veya disk varsa geri dönün.  
- Ekran görüntüsü: ![Adım 13 — Ready to Install](./screenshots/13-ready-to-install.png)

#### Adım 14: Customize settings — Administrator parolası
- Ne yapılır: Kurulum tamamlandıktan sonra yerel **Administrator** hesabı için parola belirlenir.  
- Neden: İlk oturum ve yönetim için zorunludur.  
- Dikkat: Güçlü, benzersiz parola oluşturun; blogda örnek parolalar paylaşmayın.  
- Ekran görüntüsü: ![Adım 14 — Administrator Password](./screenshots/14-admin-password.png)

#### Adım 15: Telemetry / Diagnostic Data Tercihi
- Ne yapılır: "Send diagnostic data to Microsoft" tercihi seçilir (ör. Required only veya Optional).  
- Neden: Gizlilik ve telemetri tercihleri kurulumda belirlenir.  
- Dikkat: Hangi seçimi yaptığınızı blogda belirtin; okuyucular için şeffaf olur.  
- Ekran görüntüsü: ![Adım 15 — Diagnostic Data](./screenshots/15-diagnostic-data.png)

---

## Hızlı Checkliste (Kopyala-Yapıştır)
- ISO dosyası: C:\Users\PC\Downloads\Windows Server 2025.iso  
- VM adı: SerifSelen  
- VM lokasyonu: C:\Users\PC\Documents\Virtual Machines\SerifSelen  
- RAM: 2 GB (test) / 4–8 GB öneri GUI için  
- CPU: 1 vCPU (test)  
- Disk: 100 GB (sparse) / önerilen minimum 60 GB  
- Network: NAT (test) / Bridged (lab)  
- Edition: Windows Server 2025 Standard Evaluation (Desktop Experience)  
- Klavye: Turkish Q veya tercih edilen düzen  
- Administrator: güçlü parola oluştur

---

## Blog / GitHub Yayınlama Notları
- Görüntü isimlendirme: Adım numarası ile eşleştir (ör. 01-vmware-main.png).  
- Her adımda kısa başlık, açıklama (2–3 cümle), dikkat notu ve ekran görüntüsü kullanın.  
- README için: Başa "Gereksinimler" ve "Hızlı Checklist" bölümlerini ekleyin.  
- Güvenlik: Parola, lisans anahtarları veya hassas yolları halka açık paylaşmayın.  
- Ek öneri: Kurulum sonrası VMware Tools kurulumu ve Windows Update adımlarını ayrıca belgeleyin.

---

Eğer istersen, bu Markdown dosyasını doğrudan README şekline göre biraz daha detaylandırıp her adım için hazır image embed satırlarını (senin dosya adlarına göre) otomatik dolduracak şekilde güncelleyebilirim. Hangi dosya adlarını kullanacağını belirtirsen ben hazır Markdown'u o isimlerle düzenleyip göndereyim.