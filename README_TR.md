# Kebab Proxy

**Kebab Proxy**, birden fazla yapay zekâ sağlayıcısını ve kodlama aracını tek bir yerel uç nokta arkasında birleştiren, self-hosted ve gizlilik odaklı bir AI gateway/proxy katmanıdır.

Amaç; **Claude Code**, **Codex / OpenAI uyumlu istemciler**, **Gemini tabanlı akışlar** ve diğer desteklenen servisleri tek bir operasyon katmanında toplamak, yönetmek ve ürünleştirilebilir hale getirmektir.

---

## Neden Kebab Proxy?

Modern AI araçları dağınık çalışıyor:

- farklı auth akışları
- farklı API beklentileri
- farklı model adları ve sağlayıcı davranışları
- zorlaşan operasyon ve konfigürasyon yönetimi

Kebab Proxy bu dağınıklığı toparlayarak araya bir **kontrol katmanı** koyar.

Böylece:

- araçlara **tek bir endpoint** verirsin
- birden çok upstream provider’ı tek yerden yönetirsin
- credential ve auth dosyalarını **lokalde / kendi sunucunda** tutarsın
- built-in management panel ile sistemi tarayıcıdan yönetirsin
- daha büyük **Kebab SaaS** ürünleri için altyapı katmanı oluşturursun

Kısacası: **Kebab Proxy, dağınık AI erişimini yönetilebilir bir sisteme dönüştürür.**

---

## Temel Değer Önerisi

### 1. Birleşik Erişim
Birden fazla sağlayıcıyı ve entegrasyonu tek bir API yüzeyinde toplar.

### 2. Operasyonel Kontrol
Auth dosyaları, config, routing, model mapping ve kullanım yönetimini merkezileştirir.

### 3. Gizlilik
Secret’ları, OAuth verilerini ve makineye özel bilgileri lokal tarafta tutar.

### 4. Ürün Hazırlığı
Sadece kişisel kullanım değil; daha büyük ürün ve SaaS yapıları için de temel altyapı katmanı olarak kullanılabilir.

---

## Özellikler

### Çoklu sağlayıcı yönlendirme
Desteklenen upstream AI sağlayıcıları arasında routing yapabilir.

### OpenAI uyumlu endpoint
OpenAI tarzı API bekleyen araçlarla entegrasyonu kolaylaştırır.

### Dahili yönetim paneli
Tarayıcıdan:

- auth dosyalarını
- config ayarlarını
- operasyon görünürlüğünü
- kullanım ve yönetim akışlarını

yönetmeyi kolaylaştırır.

### Lokal-first credential yönetimi
Gizli bilgileri public repo’ya veya dağınık script’lere yaymak yerine yerel kontrol altında tutar.

### Model mapping ve kontrol
İstemci beklentileri ile upstream model erişimi arasında çeviri/routing katmanı olarak görev yapar.

### Self-hosted çalışma modeli
Kendi bilgisayarında, workstation’da, sunucuda veya ürün altyapında çalıştırılmak üzere tasarlanmıştır.

---

## Kullanım Senaryoları

### AI coding merkezi
Birden fazla kodlama aracını tek endpoint ile kullanmak.

### Lokal AI operasyon katmanı
Provider erişimi, auth dosyaları ve routing’i tek yerde toplamak.

### SaaS altyapı bileşeni
Kebab tarzı ürünler için yönetilebilir AI bağlantı katmanı oluşturmak.

### Ekip / iç araç standardizasyonu
İç araçların upstream AI sistemlerine standart şekilde bağlanmasını sağlamak.

---

## Hızlı Başlangıç

### 1. Repo’yu klonla

```bash
git clone https://github.com/burhanettinerkent/kebab-proxy.git
cd kebab-proxy
```

### 2. Bağımlılıkları kur

```bash
go mod tidy
```

### 3. Local config oluştur

```bash
cp config.example.yaml config.yaml
```

Ardından `config.yaml` dosyasını kendi local ayarlarınla düzenle.

### 4. Sunucuyu başlat

```bash
go run ./cmd/server
```

### 5. Paneli aç

- `http://localhost:8317/management.html`

---

## Güvenlik ve Gizlilik

Bu public repo temizlenmiş haldedir ve aşağıdakileri içermez:

- kişisel `config.yaml`
- gerçek `auths/` içeriği
- OAuth export dosyaları
- makineye özel secret’lar
- local binary’ler
- özel token / credential verileri

### Öneri

- `config.yaml` private kalsın
- `auths/` private kalsın
- canlı credential’ları GitHub’a commit etme
- public repo’yu kod için kullan, secret saklamak için değil

---

## Projenin Stack İçindeki Yeri

**Clients / Tools**
→ Claude Code, Codex uyumlu istemciler, Gemini akışları, custom uygulamalar

**Kebab Proxy**
→ routing, auth handling, config, management UI, operasyon katmanı

**Upstream Providers**
→ gerçek model sağlayıcıları ve dış AI servisleri

Yani Kebab Proxy, istemciler ile sağlayıcılar arasındaki **kontrol katmanıdır**.

---

## Lisans

MIT
