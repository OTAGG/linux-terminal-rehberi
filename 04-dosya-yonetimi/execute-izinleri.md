# Execute İzinleri

## Execute (Çalıştırma) İzni

### Temel Kavramlar
```bash
# Execute izni karakteri: x
-rwxr-xr-x    # Sahibi için tüm izinler, diğerleri için okuma ve çalıştırma
-rw-r--r--    # Çalıştırma izni olmayan normal dosya
```

### Execute İzni Verme
```bash
# Çalıştırma izni ekleme
chmod +x dosya.sh         # Tüm kullanıcılar için çalıştırma izni
chmod u+x dosya.sh        # Sadece sahibi için çalıştırma izni
chmod g+x dosya.sh        # Sadece grup için çalıştırma izni
chmod o+x dosya.sh        # Diğer kullanıcılar için çalıştırma izni

# Sayısal mod ile izin verme
chmod 755 dosya.sh        # rwxr-xr-x
chmod 700 dosya.sh        # rwx------
```

## Script Dosyaları

### Shebang (#!) Kullanımı
```bash
#!/bin/bash              # Bash script
#!/usr/bin/python3       # Python script
#!/usr/bin/perl         # Perl script
```

### Script Çalıştırma Yöntemleri
```bash
# Doğrudan çalıştırma (execute izni gerekir)
./script.sh

# Yorumlayıcı ile çalıştırma (execute izni gerekmez)
bash script.sh
python3 script.py

# Source ile çalıştırma (mevcut kabukta)
source script.sh
. script.sh
```

## Güvenlik Hususları

### Execute İzinleri İçin Güvenlik
```bash
# Sadece sahibi çalıştırabilsin
chmod 700 ozel_script.sh

# Grup ile paylaşılan script
chmod 750 paylasilan_script.sh

# Güvenli çalıştırma için tam yol kullanımı
/usr/local/bin/script.sh
```

### Kontrol ve İzleme
```bash
# Çalıştırılabilir dosyaları bulma
find /home -type f -perm /111

# Son 24 saatte değiştirilen çalıştırılabilir dosyalar
find /home -type f -perm /111 -mtime -1
```

## İyi Pratikler

### Script Yerleşimi
1. Sistem scriptleri: /usr/local/bin/
2. Kişisel scriptler: ~/bin/ veya ~/scripts/
3. Geçici scriptler: /tmp/ (dikkatli kullanın)

### Güvenlik Kontrolleri
1. Scriptleri çalıştırmadan önce içeriğini kontrol edin
2. Bilinmeyen kaynaklardan gelen scriptlere dikkat edin
3. Regular kullanıcı ile test edin, sonra root ile çalıştırın

------   
<br>
<br>
<br>
<div align="center">

[◀️Önceki](dosya-izinleri.md) &nbsp;&nbsp;&nbsp; [🏠AnaSayfa](../README.md) • [📑Bölüm](README.md) &nbsp;&nbsp;&nbsp; [Sonraki▶️](dosya-sahipligi.md)

</div>