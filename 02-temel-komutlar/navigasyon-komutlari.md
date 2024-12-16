# Linux Navigasyon Komutları

Terminal üzerinde etkili gezinmek için gereken temel komutları öğrenelim.

## 📚 İçindekiler
* [pwd - Print Working Directory](#pwd-print-working-directory)
* [cd - Change Directory](#cd-change-directory)
* [ls - List](#ls-list)
* [tree](#tree)
* [which](#which)
* [whereis](#whereis)
* [locate](#locate)
* [Gezinme İpuçları](#gezinme-i̇puçları)

## pwd (Print Working Directory)
Mevcut çalışma dizinini ve mutlak yol bilgisini gösterir.

```bash
# Temel Kullanım
pwd                    # Çıktı: /home/kullanici/belgeler
```

## cd (Change Directory)
Dizinler arası geçiş yapar.

```bash
# Temel Kullanımlar
cd /                   # Root dizinine git
cd ~                   # Ev dizinine git
cd ..                  # Üst dizine git
cd -                   # Önceki dizine dön
cd ./dizin             # Mevcut dizindeki alt dizine git
cd /mutlak/yol         # Belirtilen mutlak yola git
```

## ls (List)
Dizin içeriğini listeler.

```bash
# Temel Parametreler
ls                     # Basit liste
ls -l                  # Detaylı liste
ls -a                  # Gizli dosyaları göster
ls -h                  # İnsan okunabilir boyutlar
ls -R                  # Alt dizinleri recursive listele
ls -t                  # Zaman damgasına göre sırala
ls -S                  # Boyuta göre sırala
ls -r                  # Ters sıralama
ls --color            # Renkli çıktı

# Kombinasyonlar
ls -lah               # Detaylı, gizli dosyalar, okunabilir boyutlar
ls -ltr               # Detaylı, zamana göre, ters sıralı
```

## tree
Dizin yapısını ağaç şeklinde gösterir.

```bash
# Temel Kullanım
tree                   # Tüm alt dizinleri göster
tree -L 2             # Sadece 2 seviye göster
tree -d               # Sadece dizinleri göster
tree -a               # Gizli dosyaları da göster
```

## which
Komutların tam yolunu gösterir.

```bash
# Temel Kullanım
which python          # Python komutunun yolunu göster
which bash            # Bash kabuğunun yolunu göster
```

## whereis
Komutların binary, kaynak ve man sayfalarını bulur.

```bash
# Temel Kullanım
whereis bash          # Bash ile ilgili tüm dosyaları göster
whereis python        # Python ile ilgili dosyaları göster
```


## Gezinme İpuçları

### Tab Tamamlama
- Dosya/dizin isimlerini otomatik tamamlar
- İki kez tab basarak seçenekleri görüntüler

### Klavye Kısayolları
```bash
Ctrl + L              # Ekranı temizle (clear komutu gibi)
Alt + .               # Son komuttaki son argümanı kullan
Ctrl + A              # Satır başına git
Ctrl + E              # Satır sonuna git
Ctrl + U              # İmleçten satır başına kadar sil
Ctrl + K              # İmleçten satır sonuna kadar sil
```

### Özel Karakterler
```bash
~                     # Ev dizini
.                     # Mevcut dizin
..                    # Üst dizin
-                     # Önceki dizin
```

### Dizin Yığını Komutları
```bash
pushd dizin           # Dizini yığına ekle ve geç
popd                  # Yığındaki son dizine dön
dirs                  # Dizin yığınını göster

# Örnek Kullanım
pushd /var/log        # /var/log dizinine git ve yığına ekle
pushd /etc            # /etc dizinine git ve yığına ekle
dirs                  # Yığındaki dizinleri göster
popd                  # Bir önceki dizine dön
```

## Pratik Örnekler

```bash
# Dizinleri tarihe göre listele
ls -lt

# Gizli dosyalar dahil tüm içeriği göster
ls -la

# İki seviye derinlikte dizin ağacı
tree -L 2

# Belirli bir komutu bulma
which gcc

# Dizin yığını kullanımı
pushd /tmp
pushd /var/log
dirs
popd
```

---

[◀️Önceki](README.md) &nbsp;&nbsp;&nbsp; [🏠AnaSayfa](../README.md) • [📑Bölüm](README.md) &nbsp;&nbsp;&nbsp; [Sonraki▶️](dosya-islemleri.md)
