# Dosya Sahipliği

## Dosya Sahibi Değiştirme

### chown (Change Owner)
```bash
# Temel Kullanım
chown kullanici dosya                  # Sahibi değiştir
chown kullanici:grup dosya            # Sahip ve grup değiştir
chown -R kullanici dizin              # Recursive sahip değiştir
```

## Grup Sahipliği

### chgrp (Change Group)
```bash
# Temel Kullanım
chgrp grup dosya                      # Grubu değiştir
chgrp -R grup dizin                   # Recursive grup değiştir
```

## Varsayılan İzinler

### umask
```bash
# umask değeri varsayılan izinlerden çıkarılır
umask                  # Mevcut umask değerini göster
umask 022             # umask değerini ayarla

# Varsayılan izinler:
# - Dosyalar için: 666 (rw-rw-rw-)
# - Dizinler için: 777 (rwxrwxrwx)
```

## Yaygın Senaryolar

### Proje Dizinleri
```bash
# Web sunucu dizini
chown -R www-data:www-data /var/www/html
chmod -R 755 /var/www/html

# Paylaşılan proje dizini
mkdir /proje
chown :developers /proje
chmod 2775 /proje      # SGID ile birlikte
```

### Özel Dosyalar
```bash
# SSH anahtarları
chmod 600 ~/.ssh/id_rsa
chmod 644 ~/.ssh/id_rsa.pub

# Yapılandırma dosyaları
chmod 644 ~/.bashrc
chmod 600 ~/.config/sensitive_config
```

## İyi Pratikler

1. **Dosya Sahipliği:**
   - Uygun kullanıcı ve grup ataması yapın
   - Recursive değişikliklerde dikkatli olun
   - Sistem dosyalarının sahipliğini değiştirmeyin

2. **Grup Yönetimi:**
   - Proje bazlı gruplar kullanın
   - Grup izinlerini düzenli gözden geçirin
   - Paylaşılan dizinlerde SGID kullanmayı düşünün

3. **Varsayılan İzinler:**
   - Uygun umask değeri belirleyin
   - Özel durumlar için ayrı umask kullanın
   - Güvenlik politikalarına uygun ayarlayın

------   
<br>
<br>
<br>
<div align="center">

[◀️Önceki](execute-izinleri.md) &nbsp;&nbsp;&nbsp; [🏠AnaSayfa](../README.md) • [📑Bölüm](README.md)

</div>