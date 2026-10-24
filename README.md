# Kamera Merkezi

Tapo / ONVIF kameralar için modern masaüstü uygulaması: canlı izleme, hareket ve kişi algılama,
olay kaydı, PTZ joystick, konum hafızası (preset), günlük ve kayıt izleyici.

## Kamerada bir kez yapılacak ayar
Tapo uygulaması → kamera → Ayarlar → Gelişmiş Ayarlar → **Kamera Hesabı** bölümünden bir
kullanıcı adı ve şifre oluşturun. Uygulamaya bu bilgiyi gireceksiniz (Tapo hesabınızın şifresi değil).

## Çalıştırma
- Hızlı deneme: `calistir.bat` (paketleri kurar ve programı açar). Python 3.9+ gerekir.
- EXE yapmak için: `derle.bat` → `dist\KameraMerkezi_64bit.exe` (kurulu Python'un bitliğine göre ad alır).
- **32 bit (x86) Windows için:** 32 bit Python kurun (python.org → *Windows installer (32-bit)*, py launcher seçili) ve `derle.bat 32` çalıştırın → `dist\KameraMerkezi_32bit.exe`. Bu modda `requirements-32bit.txt` kullanılır (eski numpy/opencv sürümleri). 64 bit exe 32 bit Windows'ta açılmaz; 32 bit exe ise her iki sistemde de çalışır. Hızlı deneme için `calistir.bat 32`.

## İlk kullanım
1. **Kameraları Tara** (ya da **Kamera Ekle**) → kamerayı seçin, kullanıcı adı/şifreyi girin,
   **Bağlantıyı Test Et** ile doğrulayın, **Kaydet**.
2. **Kayıt Ayarları** → klasör ve mod (hareket / kişi / sürekli / kapalı).

## Ana sayfa düzeni (1–6 kamera)
Üstteki **GÖRÜNÜM** düğmeleriyle aynı anda **1, 2, 3, 4, 5 veya 6** kamerayı izleyebilirsiniz:
1 = tek büyük görüntü · 2 = alt alta (geniş pencerede yan yana) · 3 = üstte geniş, altta iki ·
4 = 2×2 · 5 = solda büyük, sağda ve altta dört · 6 = 3×2 (geniş pencerede 2×3).
- Karoda **⚙** → o karoya hangi kameranın geleceğini seçin (başka karodaysa ikisi yer değiştirir), düzenleyin veya karoyu boşaltın.
  Boş karoya tıklamak da aynı menüyü açar.
- Karoya **tıklayınca** o kamera seçilir (mavi çerçeve): sağdaki PTZ, hız, konum hafızası ve **Hızlı İşlemler** o kameraya gider.
  Sağdaki **Kamera seçin** listesi de aynı seçimi yapar.
- Karoda **⛶** ya da çift tıklama → o kamera tek karoya büyür; yeniden basın ya da **Esc** ile geri dönün.
- Karoda **📷** fotoğraf, **⏺** elle kayıt (o kamera için).
- **Kamera Listesi / Kontrol Paneli** düğmeleriyle yan paneller gizlenip görüntü alanı büyütülür; alttaki **Günlük** günlüğü açar/kapatır; **Tam Ekran** (F11) tüm menüleri gizler.
- Seçtiğiniz düzen, karolardaki kameralar ve panel durumları kapanışta saklanır, bir sonraki açılışta aynen gelir.
- Düzende kamera sayısından fazla karo varsa kalan karolar boş görünür; kamera ekledikçe boş karolar kendiliğinden dolar.

## Kayıtlar penceresi
**Kayıtları İzle** ile açılır. Kayıtlar güne göre gruplanır (Bugün, Dün, Pazartesi…) ve her biri küçük resim, kamera adı, saat, süre ve boyutla kart olarak görünür.
- Üstten **kameraya**, **tarihe** (bugün / dün / son 7 gün) göre süzün, **sıralamayı** değiştirin (en yeni / en eski / en büyük) veya arayın.
- Karta tıklayınca sağda büyük önizleme ve bilgiler (tarih, süre, çözünürlük, boyut) görünür; **Oynat** (ya da çift tıklama) kaydı açar, **Klasörde Göster** dosyayı gösterir, **Sil** siler.
- **Oynat** kaydı uygulamanın içindeki oynatıcıda açar: oynat/duraklat (boşluk), ilerleme çubuğundan ya da ←/→ ile atlama, ↺10 / 10↻, hız (0.5×–4×), önceki/sonraki kayıt (⏮ ⏭ ya da ↑/↓), 📷 anlık kare kaydetme, ⛶ tam ekran (F; Esc ile çıkış). Dış oynatıcı gerekirse **Harici oynatıcıda aç** düğmesi var.
- **Ctrl** ile birden fazla kayıt seçip birlikte silebilirsiniz. Liste 40’ar kayıt yüklenir; **Daha fazla göster** ile devam eder.

## Bildirimler (hareket / kişi algılanınca)
Kenar çubuğundaki **🔔** (ya da Kayıt Ayarları → *Bildirim ayarları*) ile açılır. Bildirimler yalnızca kayıt modu **Hareket algılanınca** veya **Kişi algılanınca** iken gelir (sürekli kayıtta algılama yapılmaz).
- **Masaüstü bildirimi:** Windows 10/11 bildirimi (ek program gerekmez); gösterilemezse ekranın sağ altında küçük bir pencere açılır, tıklayınca o kamera seçilir. İsteğe bağlı bildirim sesi.
- **WhatsApp:** Ücretsiz ve kişisel kullanıma yönelik [CallMeBot](https://www.callmebot.com/blog/free-api-whatsapp-messages/) ile. Botun numarasına WhatsApp'tan "I allow callmebot to send me messages" yazın; size gelen API anahtarını ve telefon numaranızı (+90…) pencereye girin, **WhatsApp'ı dene** ile doğrulayın. Yalnızca metin gider (kamera adı, saat; Cloudflare tüneli açıksa canlı izleme adresi); görüntü gönderilmez. Bot dolu olabilir; ücretli ve resim gönderebilen alternatifler: Twilio, TextMeBot.
- **Bekleme süresi:** Aynı kameradan en sık her 10 sn–10 dk'da bir bildirim (WhatsApp için en az 30 sn).
- Gizlilik: WhatsApp mesaj metni üçüncü taraf servisten geçer; API anahtarı `%APPDATA%\KameraMerkezi\ayarlar.json` içinde düz metin saklanır.

## Ses
Tapo kameranın mikrofonundaki ses RTSP akışından alınır (ek ayar gerekmez; ffmpeg, `imageio-ffmpeg` paketiyle gelir).
- **Canlı dinleme:** Karodaki 🔊 düğmesiyle o kameranın sesi açılır/kapanır; kenar çubuğundaki *Ses* kartından ses seviyesi ayarlanır. Aynı anda tek kamera dinlenir.
- **Sesli kayıt:** Kayıt Ayarları → *Kayıtlara ses ekle*. Kayıt bitince ses, videoya arka planda eklenir (AAC); eklenemezse video sessiz kalır. Kayıtlar listesinde sesli kayıtlar 🔊 rozetiyle görünür.
- **Oynatıcıda ses:** Kayıt oynatıcısında ses çalar; 🔊 ile kısılır. Ses ile görüntü yaklaşık senkron çalışır; hız 2×’in üstünde, ilerleme çubuğu sürüklenirken ve duraklatılmışken ses kesilir.
- Kamerada mikrofon açık olmalı (Tapo → Kamera ayarları → Ses). Ses cihazı veya ffmpeg bulunamazsa uygulama sessiz çalışmaya devam eder.
- Kapsam dışı: iki yönlü konuşma (kameraya ses gönderme) ve uzaktan erişim web sayfasında ses yoktur.

## Notlar
- Ayarlar ve günlük: `%APPDATA%\KameraMerkezi\` (şifre bu klasörde düz metin olarak durur).
- Tapo C200'de optik zoom yoktur; zoom düğmeleri **dijital zoom** yapar.
- Kayıtlara ses, kamerada ve uygulamada ses açıksa eklenir (aşağıdaki *Ses* bölümü); kapalıysa video sessizdir.
- Kayıt klasörü yolunda Türkçe/özel karakter varsa Windows'ta OpenCV yazamayabilir; program bunu
  fark edip kayıtları `C:\Users\Public\KameraKayitlari` içine yazar.
- Bağlantı koparsa program kendiliğinden yeniden bağlanır ve açık kaydı kapatır.

## Uzaktan erişim (Cloudflare Tüneli)
Yan çubuktaki ☁ simgesi veya üstteki **Uzaktan Erişim** düğmesi.

1. Web sayfası girişi için bir **kullanıcı adı** ve en az 8 karakterlik **şifre** belirleyin.
2. Yöntemi seçin:
   - **Hızlı tünel** — hesap gerekmez; başlatınca geçici bir `https://….trycloudflare.com` adresi verilir
     (her başlatmada değişir, deneme amaçlıdır).
   - **Kendi tünelim** — Cloudflare Zero Trust → Networks → Tunnels'ta tünel oluşturun, kurulum komutunu
     (veya yalnızca `eyJ…` token'ını) yapıştırın. Tünelin *Public Hostname* ayarında Service olarak
     `HTTP` ve `127.0.0.1:8787` girin (port, uygulamadaki yerel portla aynı olmalı).
   - **Tünelsiz (yerel)** — yalnızca bu bilgisayarda `http://127.0.0.1:8787`.
3. `cloudflared` kurulu değilse **İndir**'e basın (ya da **Dosya seç**).
4. **Başlat** → adres kutuda görünür; telefondan açıp kullanıcı adı/şifreyle girin.

Notlar:
- Web sayfasında (telefondan/tarayıcıdan) şunlar var:
  - **Canlı** sekmesi: uygulamadaki gibi **1–6 kameralı ızgara** (üstteki GÖRÜNÜM düğmeleri; karoda ⚙ ile kamera atama, ⛶ ya da çift tıklama ile büyütme, **Tam ekran**; seçim ve düzen tarayıcıda saklanır, telefonda karolar 2 sütunlu dizilir), kalite seçimi (küçük karolarda otomatik düşürülür; çok kamera + yüksek kalite tüneli yorar), fotoğraf çekme, **PTZ** (seçili karonun kamerası için; yön tuşları, ana konum,
    konum hafızasından “Git”), **elle kayıt başlat/durdur**. Yön tuşunu basılı tutarsınız; bırakınca (ya da
    bağlantı koparsa 1,5 sn içinde) kamera durur.
  - **Kayıtlar** sekmesi: kayıt listesi (kamera, tarih, boyut, süre, küçük resim), **oynatma** (duraklat,
    kaydırma, 1x/2x/4x/8x), **indirme**. Kayıtlar sunucuda çözülüp görüntü olarak aktarıldığı için tarayıcı
    kodek sorunu olmaz; web sayfasında ses yoktur. Hâlâ yazılmakta olan kayıt bitene kadar açılmaz.
- **İzinler:** Uzaktan Erişim penceresinden “Kamera kontrolü (PTZ) ve elle kayıt” ile “Kayıtları listele, oynat
  ve indir” ayrı ayrı kapatılabilir; kapalı özellikler sayfada gizlenir ve sunucuda da reddedilir.
- Değiştirici işlemler (PTZ, kayıt) başka bir sitenin sayfasından tetiklenemez (özel başlık + JSON gerekir);
  kayıt dosyaları yalnızca kayıt klasöründeki `ad.mp4` adlarıyla sunulur.
- Web sunucusu yalnızca `127.0.0.1` üzerinde dinler; dışarıdan yalnızca tünel üzerinden erişilir.
  10 yanlış şifre denemesinde o adres 5 dakika engellenir.
- Kalıcı tüneli Cloudflare Access (e-posta doğrulaması) ile korumanız önerilir.
- Şifre ve token, kamera şifreleri gibi `%APPDATA%\KameraMerkezi\ayarlar.json` içinde düz metin durur.
