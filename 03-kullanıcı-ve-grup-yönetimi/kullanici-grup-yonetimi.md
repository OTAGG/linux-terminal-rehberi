# Linux Kullanıcı ve Grup Yönetimi

## Kullanıcı Yönetimi

### Kullanıcı Oluşturma

#### useradd
```bash
# Temel Kullanım
useradd kullanici                 # Temel kullanıcı oluşturma
useradd -m kullanici             # Ev dizini ile oluştur
useradd -m -s /bin/bash kullanici # Kabuk belirterek oluştur
useradd -u 1500 kullanici        # UID belirterek oluştur
useradd -g grup kullanici        # Grup belirterek oluştur
```

#### adduser (Debian-tabanlı sistemler)
```bash
# Daha interaktif bir araç
adduser kullanici                # İnteraktif kullanıcı oluşturma
```

### Kullanıcı Düzenleme

#### usermod
```bash
# Temel Kullanım
usermod -l yeni_ad eski_ad       # Kullanıcı adını değiştir
usermod -d /yeni/ev kullanici    # Ev dizinini değiştir
usermod -s /bin/zsh kullanici    # Kabuğu değiştir
usermod -g yeni_grup kullanici   # Birincil grubu değiştir
usermod -aG grup1,grup2 kullanici # İkincil gruplar ekle
```

### Kullanıcı Silme

#### userdel
```bash
# Temel Kullanım
userdel kullanici               # Kullanıcıyı sil
userdel -r kullanici           # Ev dizini ile birlikte sil
```

### Parola Yönetimi

#### passwd
```bash
# Temel Kullanım
passwd                          # Kendi parolanızı değiştirin
passwd kullanici               # Başka kullanıcının parolasını değiştir
passwd -l kullanici           # Hesabı kilitle
passwd -u kullanici           # Kilidini aç
```

#### chage
```bash
# Parola zamanlama ayarları
chage -l kullanici            # Parola bilgilerini göster
chage -M 90 kullanici         # Maksimum geçerlilik süresi
chage -m 5 kullanici          # Minimum değiştirme süresi
```

## Grup Yönetimi

### Grup Oluşturma

#### groupadd
```bash
# Temel Kullanım
groupadd grup                   # Yeni grup oluştur
groupadd -g 1500 grup          # GID belirterek oluştur
```

### Grup Düzenleme

#### groupmod
```bash
# Temel Kullanım
groupmod -n yeni_ad eski_ad     # Grup adını değiştir
groupmod -g 1600 grup           # GID değiştir
```

### Grup Silme

#### groupdel
```bash
groupdel grup                   # Grubu sil
```

### Grup Üyeliği

#### gpasswd
```bash
# Temel Kullanım
gpasswd -a kullanici grup      # Kullanıcıyı gruba ekle
gpasswd -d kullanici grup      # Kullanıcıyı gruptan çıkar
```

## Önemli Dosyalar

### /etc/passwd
```
kullanici:x:1000:1000:Ad Soyad:/home/kullanici:/bin/bash
│         │ │    │    │        │               └── Kabuk
│         │ │    │    │        └──────────────── Ev dizini
│         │ │    │    └─────────────────────── Açıklama
│         │ │    └──────────────────────────── GID
│         │ └───────────────────────────────── UID
│         └─────────────────────────────────── Parola (x=shadow'da)
└───────────────────────────────────────────── Kullanıcı adı
```

### /etc/group
```
grup:x:1000:kullanici1,kullanici2
│    │ │    └── Grup üyeleri
│    │ └──────── GID
│    └────────── Parola (genelde boş)
└────────────── Grup adı
```

## Güvenlik ve İyi Pratikler

1. **Kullanıcı Oluşturma:**
   - Uygun UID aralığı kullanın (1000+)
   - Anlamlı kullanıcı adları seçin
   - Gerekli gruplara ekleyin

2. **Grup Yönetimi:**
   - Proje bazlı gruplar oluşturun
   - Grup izinlerini düzenli gözden geçirin
   - Gereksiz grup üyeliklerini temizleyin

3. **Düzenli Bakım:**
   - Kullanılmayan hesapları tespit edin
   - Parola sürelerini kontrol edin
   - Grup üyeliklerini gözden geçirin

------   
<br>
<br>
<br>
<div align="center">

[◀️Önceki](README.md) &nbsp;&nbsp;&nbsp; [🏠AnaSayfa](../README.md) • [📑Bölüm](README.md) &nbsp;&nbsp;&nbsp; [Sonraki▶️](root-sudo-yonetimi.md)

</div>