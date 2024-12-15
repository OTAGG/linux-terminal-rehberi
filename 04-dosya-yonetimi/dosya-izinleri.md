# Dosya İzinleri

## İzin Yapısı

### Dosya İzinleri Görüntüleme
```bash
# Örnek bir ls -l çıktısı
drwxr-xr-x  2 kullanici grup  4096 Dec 15 10:30 dizin
-rw-r--r--  1 kullanici grup   123 Dec 15 10:31 dosya.txt
```

### İzin Karakterleri
```
d | rwx | r-x | r-x
│   │     │     └── Diğerleri için izinler
│   │     └────── Grup için izinler
│   └──────────── Sahibi için izinler
└────────────────┐
                 ├── d: dizin
                 ├── -: normal dosya
                 ├── l: sembolik link
                 └── diğer özel dosya tipleri
```

### İzin Tipleri
- `r` (read): Okuma izni
- `w` (write): Yazma izni
- `x` (execute): Çalıştırma izni
- `-`: İzin yok

## chmod (Change Mode)

### Sembolik Mod
```bash
# Temel Kullanım
chmod u+x dosya        # Sahibi için çalıştırma izni ekle
chmod g-w dosya        # Grup için yazma iznini kaldır
chmod o=r dosya        # Diğerleri için sadece okuma izni
chmod a+x dosya        # Herkes için çalıştırma izni ekle

# Çoklu İzinler
chmod u+rwx,g+rx,o+r dosya
```

### Sayısal Mod (Octal)
```bash
# İzin Değerleri
# r = 4
# w = 2
# x = 1

chmod 755 dosya        # rwxr-xr-x
chmod 644 dosya        # rw-r--r--
chmod 700 dosya        # rwx------
chmod 777 dosya        # rwxrwxrwx (dikkatli kullanın!)
```

## İyi Pratikler

1. En az yeterli izinleri verin
2. Sistem dosyalarının izinlerini değiştirirken dikkatli olun
3. İzin değişikliklerini test edin

------   
<br>
<br>
<br>
<div align="center">

[◀️Önceki](README.md) &nbsp;&nbsp;&nbsp; [🏠AnaSayfa](../README.md) • [📑Bölüm](README.md) &nbsp;&nbsp;&nbsp; [Sonraki▶️](execute-izinleri.md)

</div>