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


### Pratik Örnek: Python Counter Service
Basit bir sayaç servisinin oluşturulması ve yönetimi:

1. Python Script (`counter_service.py`):
```python
import time

if __name__ == "__main__":
    counter = 0
    while True:
        print("Counter:", counter)
        time.sleep(1)  # Her saniye güncelle
        counter += 1
```
2. Executable Etme:
```bash
chmod +x path_of_your_file/counter_service.py
```


3. Systemd Servis Dosyası Oluşturma:
```bash
sudo nano /etc/systemd/system/counter.service
```

4. Servis Dosyası İçeriği:
```ini
[Unit]
Description=Python Counter Service
After=network.target

[Service]
Type=simple
ExecStart=/usr/bin/python3 /path_of_file/counter_service.py
Restart=always
User=your_username
StandardOutput=append:/var/log/counter.log
StandardError=append:/var/log/counter.error.log

[Install]
WantedBy=multi-user.target
```

5. Servisi Etkinleştirme ve Başlatma:
```bash
# Systemd'yi yeni servis hakkında bilgilendir
sudo systemctl daemon-reload

# Servisi etkinleştir (sistem başlangıcında otomatik başlatır)
sudo systemctl enable counter.service

# Servisi başlat
sudo systemctl start counter.service
```

6. Servis Yönetimi:
```bash
# Durumu kontrol et
sudo systemctl status counter.service

# Logları izle
tail -f /var/log/counter.log

# Servisi durdur
sudo systemctl stop counter.service

# Servisi devre dışı bırak
sudo systemctl disable counter.service
```

[◀️Önceki](sistem-monitorleri.md) &nbsp;&nbsp;&nbsp; [🏠AnaSayfa](../README.md) • [📑Bölüm](README.md) &nbsp;&nbsp;&nbsp; [Sonraki▶️](log-izleme.md)

</div>