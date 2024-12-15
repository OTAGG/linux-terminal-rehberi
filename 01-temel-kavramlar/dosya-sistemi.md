# Linux Dosya Sistemi

Linux'ta her şey bir dosyadır ve dosya sistemi ters bir ağaç yapısına benzer.

## Temel Dizin Yapısı

```
/                   # Root (kök) dizini
├── bin/            # Temel sistem komutları
├── boot/           # Başlangıç dosyaları
├── dev/            # Cihaz dosyaları
├── etc/            # Sistem yapılandırması
├── home/           # Kullanıcı dizinleri
│   └── username/   # Kullanıcının kişisel dizini
├── lib/            # Sistem kütüphaneleri
├── media/          # Çıkarılabilir medya
├── mnt/            # Geçici bağlama noktası
├── opt/            # Opsiyonel yazılımlar
├── proc/           # Sistem bilgileri
├── root/           # Root kullanıcı dizini
├── sbin/           # Sistem yönetimi komutları
├── tmp/            # Geçici dosyalar
├── usr/            # Kullanıcı programları
└── var/            # Değişken veriler
```

## Önemli Dizinler ve Görevleri

### 1. /home
- Her kullanıcının kişisel dosyaları
- Yapılandırma dosyaları
- Kullanıcı bazlı ayarlar

### 2. /etc
- Sistem yapılandırma dosyaları
- Ağ ayarları
- Kullanıcı ve grup bilgileri

### 3. /bin ve /sbin
- Temel sistem komutları
- Yönetici komutları
- Başlangıç için gerekli programlar

## Dosya Tipleri

### 1. Normal Dosyalar (-)
- Metin dosyaları
- Binary dosyalar
- Resimler, videolar

### 2. Dizinler (d)
- Dosya ve klasörleri içerir
- Hiyerarşik yapı
- Gezinme noktaları

### 3. Sembolik Linkler (l)
- Kısayollar
- Başka dosyalara referanslar
- Esnek dosya organizasyonu

### 4. Cihaz Dosyaları (b,c)
- Blok cihazlar (b)
- Karakter cihazlar (c)
- Donanım erişimi

## Dosya Yolu Örnekleri

### Mutlak Yol
- `/home/kullanici/belgeler/dosya.txt`
- Root'tan başlayan tam yol
- Her zaman çalışır

### Göreceli Yol
- `./belgeler/dosya.txt`
- Bulunulan konuma göre
- Daha kısa yazım

## Özel Dizin İsimleri

- `.` : Mevcut dizin
- `..` : Üst dizin
- `~` : Kullanıcının ev dizini



------   
<br>
<br>
<br>
<div align="center">

[◀️Önceki](terminal.md) &nbsp;&nbsp;&nbsp; [🏠AnaSayfa](../README.md) • [📑Bölüm](README.md)

</div>