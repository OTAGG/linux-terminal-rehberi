# Root ve Sudo Yönetimi

## Root Kullanıcısı

### Özellikleri
```bash
# Root kullanıcısının özellikleri
UID: 0                 # Root her zaman 0 UID'sine sahiptir
Ana Dizin: /root       # Root'un ev dizini
Kabuk: /bin/bash       # Varsayılan kabuk
```

### Root Erişimi
```bash
# Root'a geçiş yöntemleri
su                     # Root parolası ile geçiş
su -                   # Root olarak yeni oturum
sudo -i                # Sudo ile root kabuğuna geçiş
sudo -s                # Mevcut ortam değişkenleriyle root kabuğu
```

## Sudo Sistemi

### Sudo Kurulumu
```bash
# Debian/Ubuntu
apt install sudo

# Red Hat/CentOS
dnf install sudo
```

### Sudo Grubu Yönetimi
```bash
# Kullanıcıyı sudo grubuna ekleme
usermod -aG sudo kullanici     # Debian/Ubuntu
usermod -aG wheel kullanici    # Red Hat/CentOS

# Grup üyeliğini kontrol etme
groups kullanici
id kullanici
```

### Sudo Yapılandırması
```bash
# Sudo yapılandırmasını düzenleme
visudo                         # /etc/sudoers dosyasını güvenli düzenleme

# Temel sudo kuralları
kullanici ALL=(ALL:ALL) ALL    # Tüm komutlara izin
kullanici ALL=(ALL) NOPASSWD:ALL # Parola sormadan izin
%sudo ALL=(ALL:ALL) ALL        # Sudo grubu için tüm izinler
```

### Sudo Kullanımı
```bash
# Temel komutlar
sudo komut                     # Komutu root olarak çalıştır
sudo -u kullanici komut       # Başka kullanıcı olarak çalıştır
sudo -l                       # İzinleri listele
sudo !!                      # Son komutu sudo ile tekrarla
```

## Güvenlik En İyi Pratikleri

### Root Güvenliği

#### SSH Yapılandırması
```bash
# /etc/ssh/sshd_config
PermitRootLogin no            # Root SSH girişini kapat
```

#### Root Parolası
```bash
# Güçlü parola belirleme
passwd root                   # Root parolasını değiştir
```

### Sudo Güvenliği

#### Sudo Logları
```bash
# Sudo komutlarını izleme
tail -f /var/log/auth.log    # Debian/Ubuntu
tail -f /var/log/secure      # Red Hat/CentOS
```

#### Sudo Yapılandırma Örnekleri
```bash
# /etc/sudoers
# Zaman aşımı
Defaults timestamp_timeout=15

# Belirli komutlara izin
kullanici ALL=(ALL) /bin/ls, /usr/bin/apt
```

## Sorun Giderme

### Sudo Sorunları
```bash
# Sudo grubunu kontrol et
grep sudo /etc/group

# Sudo log kontrolü
sudo grep sudo /var/log/auth.log

# Sudo yapılandırma kontrolü
sudo visudo -c
```

## Önemli Güvenlik Notları

1. **Root Kullanımı:**
   - Root hesabını sadece gerektiğinde kullanın
   - Root parolasını güvenli tutun
   - Root girişini SSH üzerinden kapatın

2. **Sudo Kullanımı:**
   - Sudo yetkilerini minimum gereksinim prensibiyle verin
   - Sudo komutlarını düzenli olarak izleyin
   - Sudo yapılandırmasını düzenli kontrol edin

3. **Genel Güvenlik:**
   - Güvenlik güncellemelerini takip edin
   - Şüpheli aktiviteleri izleyin
   - Düzenli güvenlik denetimi yapın

------   
<br>
<br>
<br>
<div align="center">

[◀️Önceki](kullanici-grup-yonetimi.md) &nbsp;&nbsp;&nbsp; [🏠AnaSayfa](../README.md) • [📑Bölüm](README.md)

</div>