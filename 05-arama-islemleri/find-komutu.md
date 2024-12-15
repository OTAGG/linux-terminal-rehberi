# Find Komutu

Find komutu, Linux sistemlerde dosya ve dizinleri aramak için kullanılan güçlü bir araçtır.

## Temel Kullanım

### Syntax
```bash
find [başlangıç_dizini] [arama_kriterleri] [eylem]
```

### Temel Örnekler
```bash
# Mevcut dizinde dosya ara
find . -name "dosya.txt"

# Tüm sistemde ara
find / -name "dosya.txt"

# Case-insensitive arama
find . -iname "dosya.txt"
```

## Arama Kriterleri

### 1. İsme Göre Arama
```bash
# Belirli uzantılı dosyaları bul
find . -name "*.pdf"

# Birden fazla uzantı
find . -name "*.pdf" -o -name "*.txt"

# Wildcard kullanımı
find . -name "dosya*"
```

### 2. Boyuta Göre Arama
```bash
# 100MB'dan büyük dosyalar
find . -size +100M

# 50KB'dan küçük dosyalar
find . -size -50k

# Tam 1GB dosyalar
find . -size 1G
```

### 3. Zamana Göre Arama
```bash
# Son 7 günde değiştirilmiş
find . -mtime -7

# 30 günden eski
find . -atime +30

# Son 1 saatte değiştirilmiş
find . -mmin -60
```

## İleri Seviye Kullanım

### 1. Tip Filtreleme
```bash
# Sadece dizinler
find . -type d

# Sadece normal dosyalar
find . -type f

# Sadece sembolik linkler
find . -type l
```

### 2. İzinlere Göre Arama
```bash
# Çalıştırılabilir dosyalar
find . -perm /a=x

# 644 izinli dosyalar
find . -perm 644

# SUID biti olan dosyalar
find . -perm -4000
```

### 3. Mantıksal Operatörler
```bash
# VE operatörü
find . -name "*.txt" -size +1M

# VEYA operatörü
find . -name "*.jpg" -o -name "*.png"

# DEĞİL operatörü
find . ! -name "*.txt"
```

## Eylemler

### 1. Temel Eylemler
```bash
# Bulunan dosyaları sil
find . -name "*.tmp" -delete

# Bulunan dosyaların izinlerini değiştir
find . -type f -exec chmod 644 {} \;

# Bulunan dosyaları listele
find . -type f -ls
```

### 2. Özel Eylemler
```bash
# Bulunan dosyaları kopyala
find . -name "*.jpg" -exec cp {} /yedek/ \;

# Bulunan dosyaların içeriğini ara
find . -type f -exec grep "aranan" {} \;

# Bulunan dosyaları sıkıştır
find . -name "*.log" -exec gzip {} \;
```

## Performans İpuçları

### 1. Aramaları Sınırlandırma
```bash
# Maksimum derinlik belirtme
find . -maxdepth 2 -name "*.txt"

# Minimum derinlik belirtme
find . -mindepth 1 -name "*.txt"
```

### 2. Disk Kullanımını Azaltma
```bash
# Farklı dosya sistemlerini atla
find . -xdev -name "*.log"

# Önbelleği kullan
find . -name "*.txt" -print
```

## Pratik Örnekler

### 1. Büyük Dosyaları Bulma
```bash
# En büyük 10 dosyayı listele
find . -type f -exec du -h {} + | sort -rh | head -n 10
```

### 2. Eski Dosyaları Temizleme
```bash
# 30 günden eski geçici dosyaları sil
find /tmp -type f -mtime +30 -delete
```

### 3. Boş Dizinleri Bulma
```bash
# Boş dizinleri listele
find . -type d -empty
```

------   
<br>
<div align="center">

[◀️Önceki](README.md) &nbsp;&nbsp;&nbsp; [🏠AnaSayfa](../README.md) • [📑Bölüm](README.md) &nbsp;&nbsp;&nbsp; [Sonraki▶️](grep-komutu.md)

</div>