# Linux Dosya İşlemleri

Dosya ve dizinleri yönetmek için gereken temel komutları öğrenelim.

## 📚 İçindekiler
* [Dosya Oluşturma](#dosya-oluşturma)
* [Dosya Okuma](#dosya-okuma)
* [Dosya Kopyalama/Taşıma](#dosya-kopyalamataşıma)
* [Dosya Silme](#dosya-silme)
* [Dosya İnceleme](#dosya-i̇nceleme)
* [Dosya Sıkıştırma](#dosya-sıkıştırma)
* [Joker Karakterler](#joker-karakterler)
* [Pratik İpuçları](#pratik-i̇puçları)

## Dosya Oluşturma

### `touch`
Boş dosya oluşturur veya varolan dosyanın zaman damgasını günceller.

```bash
# Temel Kullanım
touch dosya.txt                     # Tek dosya oluşturma
touch dosya1.txt dosya2.txt        # Çoklu dosya oluşturma
touch -t 202401011200 dosya.txt    # Belirli tarih/saat ile oluşturma
```

### `mkdir` (Make Directory)
Yeni dizin oluşturur.

```bash
# Temel Kullanım
mkdir dizin                        # Tek dizin oluşturma
mkdir -p a/b/c                     # İç içe dizinler oluşturma
mkdir -m 755 dizin                 # İzinlerle birlikte oluşturma
mkdir dizin{1..5}                  # Seri dizin oluşturma
```

### `cat` (Oluşturma Modu)
Dosya oluşturma ve içerik ekleme.

```bash
# Temel Kullanım
cat > dosya.txt                    # Yeni dosya oluştur (Ctrl+D ile kaydet)
cat dosya1.txt dosya2.txt > yeni.txt  # Dosyaları birleştir
```

## Dosya Okuma

### `head`
Dosyanın başından belirli sayıda satır gösterir.

```bash
# Temel Kullanım
head dosya.txt                     # İlk 10 satır
head -n 5 dosya.txt               # İlk 5 satır
head -c 100 dosya.txt             # İlk 100 byte
head -n -5 dosya.txt              # Son 5 satır hariç tümü
```

### `tail`
Dosyanın sonundan belirli sayıda satır gösterir.

```bash
# Temel Kullanım
tail dosya.txt                     # Son 10 satır
tail -n 5 dosya.txt               # Son 5 satır
tail -f dosya.txt                 # Canlı olarak takip et
tail +5 dosya.txt                 # 5. satırdan sonuna kadar
```

### `less`
Dosyayı sayfa sayfa görüntüleme.

**Klavye Komutları:**
* `Space` - Sonraki sayfa
* `b` - Önceki sayfa
* `/kelime` - İleri doğru ara
* `g` - Dosya başına git
* `G` - Dosya sonuna git
* `q` - Çıkış

### `more`
Basit sayfa sayfa görüntüleyici.

```bash
# Temel Kullanım
more dosya.txt                     # Dosyayı görüntüle
more -n 5 dosya.txt               # Sayfa başına 5 satır
```

## Dosya Kopyalama/Taşıma

### `cp` (Copy)
Dosya ve dizin kopyalama.

```bash
# Temel Kullanım
cp kaynak hedef                    # Dosya kopyala
cp -r kaynak hedef                # Dizin kopyala
cp -i kaynak hedef                # Üzerine yazmadan önce sor
cp -p kaynak hedef                # İzinleri koruyarak kopyala
cp -u kaynak hedef                # Sadece yeni dosyaları kopyala
```

### `mv` (Move)
Dosya/dizin taşıma ve yeniden adlandırma.

```bash
# Temel Kullanım
mv eski.txt yeni.txt              # Yeniden adlandırma
mv dosya /hedef/dizin/            # Taşıma
mv -i kaynak hedef                # Üzerine yazmadan önce sor
mv dosya{1..3}.txt dizin/         # Çoklu dosya taşıma
```

## Dosya Silme

### `rm` (Remove)
Dosya ve dizin silme. **DİKKAT:** Geri alınamaz!

```bash
# Temel Kullanım
rm dosya                          # Dosya sil
rm -r dizin                       # Dizin ve içeriğini sil
rm -i dosya                       # Silmeden önce sor
rm -f dosya                       # Zorla sil
rm -v dosya                       # Detaylı çıktı
```

### `rmdir`
Boş dizinleri siler.

```bash
# Temel Kullanım
rmdir dizin                       # Boş dizin sil
rmdir -p a/b/c                    # İç içe boş dizinleri sil
```

## Dosya İnceleme

### `file`
Dosya tipini gösterir.

```bash
file dosya.txt                    # Dosya tipini göster
```

### `stat`
Dosya/dizin detaylı bilgilerini gösterir.

```bash
stat dosya.txt                    # Detaylı bilgileri göster
```

### `wc` (Word Count)
Dosya içeriği istatistikleri.

```bash
wc dosya.txt                      # Satır, kelime ve byte sayısı
wc -l dosya.txt                   # Sadece satır sayısı
wc -w dosya.txt                   # Sadece kelime sayısı
```

## Dosya Sıkıştırma

### `tar`
Arşivleme ve sıkıştırma.

```bash
# Temel Kullanım
tar -cvf arsiv.tar dosyalar/      # Arşiv oluştur
tar -xvf arsiv.tar                # Arşivi aç
tar -czvf arsiv.tar.gz dosyalar/  # Gzip ile sıkıştır
tar -xzvf arsiv.tar.gz            # Gzip arşivi aç
```

### `zip/unzip`
Zip formatında sıkıştırma.

```bash
# Temel Kullanım
zip -r arsiv.zip dosyalar/        # Zip oluştur
unzip arsiv.zip                   # Zip aç
```

## Joker Karakterler

### `*` (Yıldız)
Sıfır veya daha fazla karakter.

```bash
*.txt               # Tüm .txt dosyaları
dosya*              # "dosya" ile başlayan tüm dosyalar
*rapor*             # İçinde "rapor" geçen tüm dosyalar
```

### `?` (Soru İşareti)
Tam olarak tek bir karakter.

```bash
dosya?              # "dosya" + tek karakter (dosya1, dosyaA)
rapor?.txt          # "rapor" + bir karakter + .txt
????.txt            # 4 karakterli isim + .txt
```

### `[]` (Köşeli Parantez)
Belirtilen karakterlerden biri.

```bash
dosya[123]          # dosya1, dosya2 veya dosya3
[aA]rapor           # arapor veya Arapor
rapor[0-9]          # rapor0'dan rapor9'a kadar
```

### `{}` (Süslü Parantez)
Virgülle ayrılmış alternatifler.

```bash
dosya{.txt,.pdf}    # dosya.txt ve dosya.pdf
proje{1,2,test}     # proje1, proje2 ve projetest
dizin{1..3}         # dizin1, dizin2 ve dizin3
```

## Pratik İpuçları

### Dosya Okuma İpuçları
1. Büyük dosyalar için `less` kullanın
2. Log takibi için `tail -f` tercih edin
3. Hızlı göz atma için `head` ve `tail` kullanın
4. Dosyaları birleştirip okumak için: `cat dosya1.txt dosya2.txt | less`
5. Log dosyası izleme: `tail -n 100 -f /var/log/syslog`

### Güvenli Kullanım
1. Silme işlemlerinde `-i` parametresini kullanın
2. Kritik silme işlemlerinden önce `ls` ile kontrol edin
3. Root dizininde tehlikeli komutlardan kaçının
4. Önemli dosyaların yedeğini alın

---

[◀️Önceki](navigasyon-komutlari.md) &nbsp;&nbsp;&nbsp; [🏠AnaSayfa](../README.md) • [📑Bölüm](README.md)