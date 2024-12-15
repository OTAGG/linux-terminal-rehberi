# Grep Kullanımı

Grep komutu, metin içinde arama yapmak için kullanılan güçlü bir araçtır.

## Temel Kullanım

### Syntax
```bash
grep [seçenekler] desen [dosya...]
```

### Temel Örnekler
```bash
# Dosyada kelime ara
grep "aranan" dosya.txt

# Birden fazla dosyada ara
grep "aranan" dosya1.txt dosya2.txt

# Mevcut dizindeki tüm dosyalarda ara
grep "aranan" *
```

## Arama Seçenekleri

### 1. Büyük/Küçük Harf Duyarlılığı
```bash
# Büyük/küçük harf duyarsız
grep -i "ArAnAn" dosya.txt

# Tam kelime eşleşmesi
grep -w "kelime" dosya.txt

# Ters arama (eşleşmeyenler)
grep -v "aranan" dosya.txt
```

### 2. Bağlam Kontrolü
```bash
# Eşleşen satırdan önceki 2 satır
grep -B 2 "aranan" dosya.txt

# Eşleşen satırdan sonraki 2 satır
grep -A 2 "aranan" dosya.txt

# Eşleşen satırın öncesi ve sonrası
grep -C 2 "aranan" dosya.txt
```

### 3. Çıktı Formatı
```bash
# Satır numaralarını göster
grep -n "aranan" dosya.txt

# Sadece eşleşen kısımları göster
grep -o "aranan" dosya.txt

# Eşleşme sayısını göster
grep -c "aranan" dosya.txt
```

## Düzenli İfadeler (Regex)

### 1. Temel Regex
```bash
# Herhangi bir karakter
grep "a.b" dosya.txt

# Satır başı
grep "^Merhaba" dosya.txt

# Satır sonu
grep "son$" dosya.txt

# Alternatif karakterler
grep "[aeiou]" dosya.txt
```

### 2. Genişletilmiş Regex
```bash
# Bir veya daha fazla tekrar
grep -E "a+" dosya.txt

# Sıfır veya bir tekrar
grep -E "a?" dosya.txt

# Sıfır veya daha fazla tekrar
grep -E "a*" dosya.txt

# Ya da operatörü
grep -E "kedi|köpek" dosya.txt
```

### 3. Karakter Sınıfları
```bash
# Rakamlar
grep "[0-9]" dosya.txt

# Harfler
grep "[a-zA-Z]" dosya.txt

# Alfanumerik karakterler
grep "[[:alnum:]]" dosya.txt
```

## İleri Seviye Kullanım

### 1. Rekürsif Arama
```bash
# Alt dizinlerde ara
grep -r "aranan" .

# Sembolik linkleri takip et
grep -R "aranan" .

# Belirli dosya tiplerinde ara
grep -r --include="*.txt" "aranan" .
```

### 2. Özel Seçenekler
```bash
# Binary dosyaları atla
grep -I "aranan" *

# Sadece eşleşen dosya isimlerini göster
grep -l "aranan" *

# Eşleşmeyen dosya isimlerini göster
grep -L "aranan" *
```

### 3. Performans İyileştirmeleri
```bash
# Hızlı arama (binary dosyaları tara)
grep -F "aranan" dosya.txt

# Paralel arama
grep -r --parallel=4 "aranan" .
```

## Pratik Örnekler

### 1. Log Analizi
```bash
# Hata mesajlarını bul
grep -i "error" /var/log/syslog

# Belirli IP adreslerini bul
grep -E "\b([0-9]{1,3}\.){3}[0-9]{1,3}\b" access.log
```

### 2. Kod İnceleme
```bash
# TODO yorumlarını bul
grep -r "TODO:" src/

# Kullanılmayan fonksiyonları bul
grep -r "function" . | grep -v "call"
```

### 3. Sistem Analizi
```bash
# Açık portları listele
netstat -tulpn | grep "LISTEN"

# CPU bilgisini göster
grep "model name" /proc/cpuinfo
```

------   
<br>
<div align="center">

[◀️Önceki](find-komutu.md) &nbsp;&nbsp;&nbsp; [🏠AnaSayfa](../README.md) • [📑Bölüm](README.md)

</div>