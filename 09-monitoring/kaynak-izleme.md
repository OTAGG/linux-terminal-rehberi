# Linux Sistem Kaynakları İzleme Rehberi

## CPU İzleme

### vmstat Kullanımı
```bash
vmstat 1                # Her saniye güncelleme
vmstat -s              # Detaylı istatistikler
vmstat -d              # Disk istatistikleri
vmstat -a              # Aktif/inaktif bellek
```

### CPU İstatistikleri
- Kullanım yüzdesi
- Load average
- I/O wait süreleri
- İşlemci kuyrukları
- Context switch sayısı
- Interrupt sayısı

## Bellek Yönetimi

### free Komutu
```bash
free -h                # İnsan okunabilir format
free -s 1             # Sürekli izleme (1 sn aralıkla)
free -t               # Toplam gösterimi
free -w               # Geniş çıktı (buffer/cache ayrı)
```

### Bellek Analizi Metrikleri
- Toplam RAM kullanımı
- Swap kullanım durumu
- Buffer/cache kullanımı
- Kullanılabilir bellek miktarı
- Paylaşılan bellek miktarı

## Disk İzleme

### df (Disk Free) Kullanımı
```bash
df -h                  # Disk doluluk oranları (human readable)
df -i                  # Inode kullanımı
df -T                  # Dosya sistemi tiplerini göster
df --total            # Toplam kullanımı göster
```

### du (Disk Usage) Kullanımı
```bash
du -sh *              # Dizin boyutları
du -h --max-depth=1   # İlk seviye dizinler
du -ch               # Toplam boyutu göster
du --time            # Son değişiklik zamanları
```

### Disk Performans Metrikleri
- I/O istatistikleri
- Okuma/yazma hızları
- Disk kuyruk uzunluğu
- Disk latency değerleri
- IOPS (Input/Output Operations Per Second)

## Ağ İzleme

### ifconfig Kullanımı
```bash
ifconfig                # Tüm aktif arayüzleri göster
ifconfig -a            # Tüm arayüzleri göster (devre dışı olanlar dahil)
ifconfig eth0          # Belirli bir arayüzün detayları
ifconfig eth0 up       # Arayüzü aktif et
ifconfig eth0 down     # Arayüzü devre dışı bırak
```

### ip Komutu (Modern Alternatif)
```bash
ip addr show           # Arayüz adresleri
ip link show           # Link durumları
ip route show          # Routing tablosu
ip neigh show          # ARP tablosu
```

### netstat ve ss Kullanımı
```bash
netstat -tuln         # Açık portlar (TCP/UDP)
netstat -anp          # Tüm bağlantılar ve programlar
netstat -r            # Routing tablosu
ss -s                 # Soket istatistikleri
ss -tu               # TCP ve UDP bağlantıları
```

### iftop ile Trafik İzleme
```bash
iftop                 # Tüm arayüzlerde trafik
iftop -i eth0         # Belirli arayüz trafiği
iftop -n              # DNS çözümlemesi olmadan
iftop -P              # Port numaralarını göster
```

### Ağ Teşhis Araçları

#### ping Kullanımı
```bash
ping host             # Sürekli ping
ping -c 4 host        # 4 ping paketi gönder
ping -i 2 host        # 2 saniye aralıkla ping
ping -s 1000 host     # 1000 byte büyüklüğünde paket
```

#### traceroute Kullanımı
```bash
traceroute host       # Varsayılan rota takibi
traceroute -n host    # DNS çözümlemesi olmadan
traceroute -w 2 host  # 2 saniye timeout
mtr host             # Sürekli traceroute
```

## Performans İzleme İpuçları

1. Düzenli İzleme
   - Kritik servisleri sürekli monitör etme
   - Baseline değerlerini belirleme
   - Anormal durumları kaydetme

2. Kaynak Planlaması
   - CPU kullanım trendleri
   - Bellek büyütme ihtiyacı
   - Disk kapasite planlaması
   - Ağ bant genişliği analizi

3. Sorun Giderme
   - Darboğaz tespiti
   - Performans optimizasyonu
   - Kapasite planlaması
   - Log analizi

4. Otomasyon
   - İzleme scriptleri
   - Otomatik uyarı sistemleri
   - Periyodik raporlama
   - Trend analizi


------   
<br>
<br>
<br>
<div align="center">

[◀️Önceki](sistem-monitorleri.md) &nbsp;&nbsp;&nbsp; [🏠AnaSayfa](../README.md) • [📑Bölüm](README.md)

</div>