# Log ve Süreç İzleme

Linux sistemlerde log yönetimi ve süreç izleme.

## journalctl

### Temel Kullanım
```bash
# Genel log görüntüleme
journalctl                      # Tüm loglar
journalctl -f                   # Canlı log takibi
journalctl -n 100              # Son 100 kayıt

# Filtreleme
journalctl -u nginx.service     # Servis bazlı
journalctl --since "1 hour ago" # Zaman bazlı
journalctl -p err              # Önem seviyesine göre
```

### Gelişmiş Özellikler
- Boot bazlı filtreleme
- JSON çıktı
- Log rotasyonu
- Disk kullanım yönetimi

## tail ve grep

### Log Takibi
```bash
# Canlı log izleme
tail -f /var/log/syslog
tail -n 100 /var/log/apache2/error.log

# grep ile filtreleme
tail -f /var/log/syslog | grep ERROR
tail -f /var/log/auth.log | grep "Failed password"
```

### Log Analizi
- Hata tespiti
- Güvenlik olayları
- Performans sorunları
- Kullanıcı aktiviteleri

## lsof

### Açık Dosyaları İzleme
```bash
# Temel kullanım
lsof                      # Tüm açık dosyalar
lsof -u username         # Kullanıcı bazlı
lsof -i :80             # Port bazlı
lsof -p PID             # Süreç bazlı
```

### Network Bağlantıları
- Port kullanımı
- Ağ soketleri
- Protokol bilgileri

## Süreç Analizi

### ps Komutu
```bash
ps aux                   # Tüm süreçler
ps -ef | grep apache    # Süreç filtrele
ps --forest            # Süreç ağacı
```

### pgrep ve pkill
```bash
pgrep -l apache         # Süreç bul
pkill -9 process_name   # Süreç sonlandır
```

## Log Yönetimi

### logrotate
- Log dosyalarının rotasyonu
- Otomatik arşivleme
- Disk alanı yönetimi

### Log Analiz Araçları
- GoAccess
- Logwatch
- fail2ban

## En İyi Uygulamalar

### 1. Log Stratejisi
- Merkezi log yönetimi
- Log saklama politikası
- Yedekleme planı

### 2. İzleme Rutinleri
- Düzenli log kontrolü
- Kritik olayları filtreleme
- Uyarı sistemleri

### 3. Güvenlik
- Log erişim kontrolü
- Şüpheli aktivite tespiti
- Audit trail

------   
<br>
<br>
<br>
<div align="center">

[◀️Önceki](servis-yonetimi.md) &nbsp;&nbsp;&nbsp; [🏠AnaSayfa](../README.md) • [📑Bölüm](README.md) &nbsp;&nbsp;&nbsp; [Sonraki▶️](kaynak-izleme.md)

</div>