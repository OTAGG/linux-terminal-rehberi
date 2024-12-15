# Linux Paket Yönetimi

## Paket Yönetimi Nedir?

Paket yönetimi, Linux sistemlerde yazılımların kurulması, güncellenmesi ve kaldırılması işlemlerini yöneten sistemdir. Paket yöneticisi, yazılım bağımlılıklarını otomatik olarak çözer ve sistem bütünlüğünü korur.

## APT ve APT-GET

### APT (Advanced Package Tool) Nedir?
- Debian tabanlı sistemlerde kullanılan modern paket yönetim aracı
- Ubuntu, Linux Mint gibi dağıtımlarda varsayılan
- Güçlü bağımlılık çözümleme
- Otomatik güncelleme desteği
- APT-GET'in daha yeni ve kullanıcı dostu versiyonu

### APT-GET Nedir?
- APT'nin eski versiyonu
- Komut satırı tabanlı paket yönetim aracı
- Script yazımında hala yaygın kullanım
- APT ile aynı paket veritabanını kullanır

### APT vs APT-GET Karşılaştırması

#### APT Avantajları
- Daha modern ve kullanıcı dostu arayüz
- İlerleme çubuğu gösterimi
- Renkli çıktı desteği
- Daha az yazım gerektiren komutlar

#### APT-GET Kullanım Alanları
- Shell script yazımında
- Eski sistemlerde
- Geriye dönük uyumluluk gereken durumlarda

### Temel APT Komutları

#### Sistem Güncelleme
```bash
# Paket listesini güncelle
sudo apt update

# Sistemdeki paketleri güncelle
sudo apt upgrade

# Dağıtım sürümünü güncelle
sudo apt dist-upgrade
```

### Temel APT-GET Komutları

#### Sistem Güncelleme
```bash
# Paket listesini güncelle
sudo apt-get update

# Sistemdeki paketleri güncelle
sudo apt-get upgrade

# Dağıtım sürümünü güncelle
sudo apt-get dist-upgrade
```

#### Paket Kurulum ve Kaldırma (APT)
```bash
# Paket kurulumu
sudo apt install paket_adi

# Birden fazla paket kurulumu
sudo apt install paket1 paket2 paket3

# Paket kaldırma
sudo apt remove paket_adi

# Paket ve yapılandırma dosyalarını kaldırma
sudo apt purge paket_adi
```

#### Paket Kurulum ve Kaldırma (APT-GET)
```bash
# Paket kurulumu
sudo apt-get install paket_adi

# Birden fazla paket kurulumu
sudo apt-get install paket1 paket2 paket3

# Paket kaldırma
sudo apt-get remove paket_adi

# Paket ve yapılandırma dosyalarını kaldırma
sudo apt-get purge paket_adi
```

#### Paket Arama ve Bilgi
```bash
# APT ile paket arama
apt search arama_terimi

# APT-GET ile paket arama
apt-cache search arama_terimi

# APT ile paket bilgisi
apt show paket_adi

# APT-GET ile paket bilgisi
apt-cache show paket_adi
```

### APT ve APT-GET Yapılandırması

#### Paket Kaynakları
- `/etc/apt/sources.list`: Ana paket kaynak listesi
- `/etc/apt/sources.list.d/`: Ek paket kaynak dosyaları
- PPA (Personal Package Archive) ekleme:
  ```bash
  sudo add-apt-repository ppa:kullanici/paket
  ```

#### Önbellek Yönetimi
```bash
# APT ile önbellek temizleme
sudo apt clean
sudo apt autoremove

# APT-GET ile önbellek temizleme
sudo apt-get clean
sudo apt-get autoremove
```

## Snap

### Snap
- Canonical tarafından geliştirilen paket sistemi
- Otomatik güncellemeler
- Tüm Linux dağıtımlarında çalışır

## İyi Uygulamalar ve İpuçları

### Güvenlik
1. Sadece güvenilir paket kaynaklarını kullan
2. Sistem güncellemelerini düzenli yap
3. Kullanılmayan paketleri kaldır

### Performans
1. Önbelleği düzenli temizle
2. Gereksiz paketleri kaldır
3. Paket veritabanını optimize et

### Sorun Giderme
1. Bağımlılık sorunları
   ```bash
   # Bozuk bağımlılıkları düzelt
   sudo apt --fix-broken install
   # veya
   sudo apt-get -f install
   ```
2. Paket çakışmaları
3. Depo sorunları

## Özet
- APT ve APT-GET aynı sistemin farklı arayüzleridir
- APT daha modern ve kullanıcı dostudur
- APT-GET script yazımında tercih edilir
- Düzenli sistem güncellemeleri önemlidir
- Güvenilir paket kaynakları kullanılmalıdır
- Modern paket yönetim sistemleri (Flatpak, Snap) alternatif sunar

------   
<br>
<br>
<br>
<div align="center">

[🏠AnaSayfa](../README.md) &nbsp;&nbsp;&nbsp; • &nbsp;&nbsp;&nbsp; [📑Bölüm](README.md)
</div>