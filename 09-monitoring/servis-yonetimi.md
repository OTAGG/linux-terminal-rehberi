# Servis Yönetimi

Linux sistemlerde servis yönetimi ve izleme.

## systemctl

### Temel Komutlar
```bash
# Servis durumu kontrolü
systemctl status service-name

# Servis kontrolü
systemctl start service-name
systemctl stop service-name
systemctl restart service-name
systemctl reload service-name

# Açılış ayarları
systemctl enable service-name
systemctl disable service-name
```

### Servis Bilgileri
- Çalışma durumu
- Bağımlılıklar
- Son olaylar
- Kaynak kullanımı

### Sistem Çapında İşlemler
```bash
systemctl list-units            # Tüm birimleri listele
systemctl list-unit-files       # Birim dosyalarını listele
systemctl list-dependencies     # Bağımlılıkları göster
```

## service Komutu

### Temel Kullanım
```bash
service nginx status    # Nginx durumu
service apache2 restart # Apache'yi yeniden başlatma
service --status-all    # Tüm servislerin durumu
```

### Servis Tipleri
- Ağ servisleri
- Sistem servisleri
- Uygulama servisleri

## Özel Servis Yönetimi

### Servis Oluşturma
```ini
[Unit]
Description=My Custom Service
After=network.target

[Service]
Type=simple
ExecStart=/usr/local/bin/my-service
Restart=always

[Install]
WantedBy=multi-user.target
```

### Servis İzleme
- Log dosyaları
- Durum kontrolleri
- Performans metrikleri

## Güvenlik ve Yetkilendirme

### Yetki Kontrolü
- Root gereksinimleri
- sudo kullanımı
- Grup yetkileri

### Güvenlik Önlemleri
- Servis izolasyonu
- Kaynak sınırlaması
- Erişim kontrolü

## En İyi Uygulamalar

### 1. Düzenli Bakım
- Periyodik kontroller
- Güncellemeleri takip
- Log analizi

### 2. Otomasyon
- Başlatma scriptleri
- Kontrol scriptleri
- Yedekleme planı

### 3. Dokümantasyon
- Servis yapılandırması
- Bağımlılıklar
- Sorun giderme adımları

------   
<br>
<br>
<br>
<div align="center">

[◀️Önceki](sistem-monitorleri.md) &nbsp;&nbsp;&nbsp; [🏠AnaSayfa](../README.md) • [📑Bölüm](README.md) &nbsp;&nbsp;&nbsp; [Sonraki▶️](log-izleme.md)

</div>