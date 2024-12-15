# Sistem Monitör Araçları

Linux sistemlerde kullanabileceğiniz temel ve gelişmiş monitör araçları.

## top

### Genel Bakış
- Sistem kaynaklarının gerçek zamanlı görüntülenmesi
- CPU, bellek ve süreç yönetimi
- İnteraktif kullanım özellikleri

### Temel Kullanım
```bash
top               # Temel görünüm
top -u username   # Belirli kullanıcının süreçleri
top -p PID       # Belirli sürecin izlenmesi
```

### İnteraktif Kısayollar
- `k`: Süreç sonlandırma
- `r`: Yeniden önceliklendirme
- `f`: Alanları yönetme
- `o`: Sıralama seçenekleri
- `h`: Yardım menüsü
- `q`: Çıkış

## htop

### Özellikler
- Renkli ve interaktif arayüz
- Mouse desteği
- İşlem ağacı görünümü
- Dikey/yatay kaydırma

### Görünüm Özellikleri
- CPU, bellek ve swap göstergeleri
- İşlem filtreleme ve arama
- Renk kodlaması
- Detaylı sistem bilgileri

### Kısayollar
- `F1-F10`: Fonksiyon menüleri
- `t`: İşlem ağacı görünümü
- `/`: Arama
- `\`: Filtreleme

## nvidia-smi

### GPU İzleme
```bash
# Temel komutlar
nvidia-smi                    # Anlık durum
nvidia-smi -l 1              # Her saniye güncelleme
nvidia-smi --query-gpu=gpu_name,temperature.gpu,utilization.gpu,utilization.memory --format=csv
```

### İzlenen Metrikler
- GPU kullanımı
- GPU bellek durumu
- Sıcaklık
- Güç tüketimi
- Fan hızı

## watch

### Kullanım Örnekleri
```bash
watch -n 1 free -m           # Bellek kullanımını izleme
watch -d nvidia-smi          # GPU durumunu izleme
watch "ps aux | grep python" # Python süreçlerini izleme
```

### Özellikler
- Herhangi bir komutu periyodik izleme
- Değişiklikleri vurgulama
- Özelleştirilebilir güncelleme aralığı

## atop

### Özellikler
- Sistem ve süreç aktivitesi izleme
- Geçmiş verileri kaydetme
- Detaylı kaynak kullanım analizi

### Görünüm Modları
- CPU görünümü
- Bellek görünümü
- Disk görünümü
- Ağ görünümü

## iotop

### Disk I/O İzleme
- Süreç bazlı disk kullanımı
- Gerçek zamanlı istatistikler
- Toplam I/O aktivitesi

### Temel Kullanım
```bash
iotop                   # Tüm süreçler
iotop -o               # Sadece aktif süreçler
iotop -b               # Batch modu
```

## En İyi Uygulamalar

### 1. Düzenli İzleme
- Kritik servisleri sürekli kontrol
- Performans metriklerini kaydetme
- Eşik değerlerini belirleme

### 2. Otomasyon
- İzleme scriptleri oluşturma
- Otomatik uyarı sistemleri
- Periyodik raporlama

### 3. Sorun Giderme
- Darboğazları tespit etme
- Kaynak kullanımını optimize etme
- Performans analizi

------   
<br>
<br>
<br>
<div align="center">

[◀️Önceki](README.md) &nbsp;&nbsp;&nbsp; [🏠AnaSayfa](../README.md) • [📑Bölüm](README.md) &nbsp;&nbsp;&nbsp; [Sonraki▶️](servis-yonetimi.md)

</div>