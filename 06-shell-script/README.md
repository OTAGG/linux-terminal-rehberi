# Shell Scripting

Shell scripting, Linux sistemlerde otomasyon ve sistem yönetimi için kullanılan güçlü bir araçtır.

## 📚 İçerik

1. [Temel Script Yazımı](#temel-script-yazımı)
2. [Değişkenler ve Veri Tipleri](#değişkenler-ve-veri-tipleri)
3. [Kontrol Yapıları](#kontrol-yapıları)
4. [Döngüler](#döngüler)
5. [Fonksiyonlar](#fonksiyonlar)
6. [Input/Output İşlemleri](#inputoutput-i̇şlemleri)

## 🎯 Hedefler
- Shell script yazımının temellerini öğrenmek
- Değişken kullanımı ve veri tiplerini anlamak
- Kontrol yapıları ve döngüleri etkili kullanabilmek
- Shell script ile otomasyon yapabilmek

## Temel Script Yazımı

### Script Dosyası Oluşturma

```bash
#!/bin/bash
# Bu bir yorum satırıdır
echo "Merhaba Dünya!"
```

### Çalıştırma İzinleri

```bash
chmod +x script.sh  # Çalıştırma izni ver
./script.sh        # Scripti çalıştır
```

### Script Yapısı
- İlk satır (shebang): `#!/bin/bash`
- Yorumlar: # ile başlar
- Komutlar: Her satırda bir komut
- Çıkış kodu: exit 0 (başarılı) veya exit 1 (hata)

## Değişkenler ve Veri Tipleri

### Değişken Tanımlama

```bash
isim="Ahmet"           # String değişken
yas=25                 # Sayısal değişken
export GLOBAL_VAR="Test"  # Global değişken
```

### Değişken Kullanımı

```bash
echo "Merhaba $isim"   # Değişken kullanımı
echo "Yaşınız: ${yas}" # Süslü parantez kullanımı
```

### Sistem Değişkenleri
- `$HOME`: Kullanıcı ev dizini
- `$PATH`: Sistem yolu
- `$USER`: Mevcut kullanıcı
- `$PWD`: Mevcut dizin

### Dizi (Array) Kullanımı

```bash
renkler=("kırmızı" "mavi" "yeşil")
echo ${renkler[0]}     # İlk element
echo ${renkler[@]}     # Tüm elementler
```

## Kontrol Yapıları

### If-Else Yapısı

```bash
if [ $yas -gt 18 ]; then
    echo "Yetişkin"
elif [ $yas -gt 12 ]; then
    echo "Genç"
else
    echo "Çocuk"
fi
```

### Case Yapısı

```bash
case $secim in
    1)
        echo "Birinci seçenek"
        ;;
    2)
        echo "İkinci seçenek"
        ;;
    *)
        echo "Geçersiz seçim"
        ;;
esac
```

## Döngüler

### For Döngüsü

```bash
# Sayısal döngü
for i in {1..5}; do
    echo "Sayı: $i"
done

# Dizi üzerinde döngü
for renk in "${renkler[@]}"; do
    echo "Renk: $renk"
done
```

### While Döngüsü

```bash
sayac=1
while [ $sayac -le 5 ]; do
    echo "Sayaç: $sayac"
    ((sayac++))
done
```

## Fonksiyonlar

### Fonksiyon Tanımlama

```bash
function selamla() {
    local isim=$1  # İlk parametre
    echo "Merhaba $isim!"
}

# Fonksiyon çağırma
selamla "Ahmet"
```

### Parametre Kullanımı

```bash
function toplama() {
    echo $(($1 + $2))
}

sonuc=$(toplama 5 3)
echo "Sonuç: $sonuc"
```

## Input/Output İşlemleri

### Kullanıcıdan Veri Alma

```bash
echo "İsminizi girin:"
read isim
echo "Merhaba $isim"
```

### Dosya İşlemleri

```bash
# Dosyaya yazma
echo "Test verisi" > dosya.txt

# Dosyaya ekleme
echo "Yeni veri" >> dosya.txt

# Dosyadan okuma
while IFS= read -r satir; do
    echo "$satir"
done < dosya.txt
```

## Örnekler

### Basit Hesap Makinesi

```bash
#!/bin/bash

function hesapla() {
    case $2 in
        "+") echo $(($1 + $3)) ;;
        "-") echo $(($1 - $3)) ;;
        "*") echo $(($1 * $3)) ;;
        "/") echo $(($1 / $3)) ;;
    esac
}

echo "İlk sayıyı girin:"
read sayi1
echo "İşlemi girin (+,-,*,/):"
read islem
echo "İkinci sayıyı girin:"
read sayi2

sonuc=$(hesapla $sayi1 $islem $sayi2)
echo "Sonuç: $sonuc"
```

### Dosya Yedekleme Scripti

```bash
#!/bin/bash

# Yedeklenecek dizin
KAYNAK_DIZIN="/home/kullanici/belgeler"
# Yedek dizini
YEDEK_DIZIN="/backup"
# Tarih
TARIH=$(date +%Y%m%d)

# Yedek dosya adı
YEDEK_ADI="yedek_${TARIH}.tar.gz"

# Yedekleme işlemi
tar -czf "${YEDEK_DIZIN}/${YEDEK_ADI}" "${KAYNAK_DIZIN}"

# Sonuç kontrolü
if [ $? -eq 0 ]; then
    echo "Yedekleme başarılı: ${YEDEK_ADI}"
else
    echo "Yedekleme başarısız!"
fi
```

------   
<br>
<br>
<br>
<div align="center">

[🏠AnaSayfa](../README.md)  &nbsp;&nbsp;&nbsp; [Sonraki▶️](shell-yapilandirma.md)

</div>