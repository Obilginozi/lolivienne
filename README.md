# GitHub Pages Statik Web Sayfası

Bu repository, GitHub Pages kullanarak statik bir web sayfası barındırmak için oluşturulmuştur.

## Kurulum Adımları

### 1. GitHub Pages'i Etkinleştirme

1. GitHub repository'nize gidin: https://github.com/Obilginozi/lolivienne
2. **Settings** (Ayarlar) sekmesine tıklayın
3. Sol menüden **Pages** seçeneğine tıklayın
4. **Source** bölümünden **Deploy from a branch** seçin
5. **Branch** olarak `main` (veya `master`) seçin
6. **Save** butonuna tıklayın

### 2. Özel Domain Bağlama

1. GitHub Pages ayarlarında **Custom domain** bölümüne domain adresinizi girin (örn: `example.com`)
2. **Save** butonuna tıklayın
3. Domain sağlayıcınızın (hosting.com.tr) DNS ayarlarına gidin
4. Aşağıdaki DNS kayıtlarını ekleyin:

#### DNS Kayıtları:

**A Kayıtları (IPv4):**
```
185.199.108.153
185.199.109.153
185.199.110.153
185.199.111.153
```

**CNAME Kayıdı (Alt domain için, örn: www):**
```
CNAME: www -> Obilginozi.github.io
```

**Veya sadece AAAA kayıtları (IPv6):**
```
2606:50c0:8000::153
2606:50c0:8001::153
2606:50c0:8002::153
2606:50c0:8003::153
```

### 3. DNS Yayılması

DNS değişikliklerinin yayılması 24-48 saat sürebilir. Kontrol etmek için:

```bash
dig yourdomain.com +nostats +nocomments +nocmd
```

veya online araçlar kullanabilirsiniz: https://dnschecker.org

### 4. HTTPS Aktifleştirme

GitHub Pages otomatik olarak HTTPS sertifikası sağlar. Domain bağlandıktan sonra:
- **Enforce HTTPS** seçeneğini işaretleyin (Settings > Pages)

## Yerel Geliştirme

Sayfayı yerel olarak görüntülemek için:

```bash
# Basit bir HTTP sunucusu başlatın
python3 -m http.server 8000
```

Sonra tarayıcınızda `http://localhost:8000` adresine gidin.

## Dosya Yapısı

```
.
├── index.html      # Ana sayfa
├── README.md       # Bu dosya
└── .nojekyll       # Jekyll'i devre dışı bırakmak için (isteğe bağlı)
```

## Özelleştirme

`index.html` dosyasını düzenleyerek sayfanızı özelleştirebilirsiniz. HTML, CSS ve JavaScript kullanabilirsiniz.

## Notlar

- GitHub Pages, Jekyll kullanır ancak statik HTML dosyaları da desteklenir
- `index.html` dosyası otomatik olarak ana sayfa olarak yüklenir
- Değişiklikler genellikle birkaç dakika içinde yayınlanır

## Yardım

Sorun yaşarsanız:
- [GitHub Pages Dokümantasyonu](https://docs.github.com/en/pages)
- [GitHub Community Forum](https://github.community/)
