# 🛡️ Anka Security (AnkaDefender)

Python ve `customtkinter` ile yazılmış, modern arayüzlü bir **tarama ve karantina uygulaması**.
Windows üzerinde yerel olarak çalışır.

> ⚠️ **Uyarı:** Bu proje gerçek bir antivirüs **değildir**. Tespit mantığı simüle edilmiş bir imza havuzuna
> (dosya adı kuralları, şüpheli uzantılar, örnek hash'ler) dayanır. Eğitim ve test amaçlıdır;
> gerçek bir güvenlik yazılımının yerine kullanmayın.

## ✨ Özellikler

- Sekmeli arayüz: **Tarama Ekranı** ve **Karantina Bölümü**
- Arka planda tarama (arayüz donmaz), ilerleme çubuğu ve canlı log ekranı
- Klasörleri, `.zip` (iç dosya adlarıyla) ve `.rar` arşivlerini kontrol eder
- Şüpheli öğeleri otomatik olarak karantinaya alır
- Karantina bilgileri SQLite veritabanında tutulur (orijinal yol, ad, tarih)
- Karantina listesinde **sağ tık → Geri Yükle** ile öğeyi eski yerine geri taşır

## 📥 Kurulum

### Seçenek 1: Tek tıkla .exe oluşturma (önerilen)

1. [Python](https://www.python.org/downloads/) kur. Kurulumda **"Add python.exe to PATH"** kutusunu işaretle.
2. Bu repoyu indir: **Code → Download ZIP** ve klasöre çıkar.
3. `EXE_OLUSTUR.bat` dosyasına çift tıkla (1-2 dakika sürer).
4. Aynı klasörde oluşan **`AnkaSecurity.exe`** dosyasını çalıştır.

### Seçenek 2: Python ile doğrudan çalıştırma

```bash
git clone https://github.com/KULLANICI_ADIN/AnkaDefender.git
cd AnkaDefender
pip install customtkinter
python anka_security.py
```

### Seçenek 3: Elle .exe oluşturma

```bash
pip install customtkinter pyinstaller
pyinstaller --onefile --windowed --name "AnkaSecurity" --collect-all customtkinter anka_security.py
```

Çıktı: `dist/AnkaSecurity.exe`

## 🚀 Kullanım

1. **Otomatik Tara**: İndirilenler, Masaüstü, Belgeler ve Temp klasörlerini tarar.
2. **Klasör Seç ve Tara**: Seçtiğin klasörü tarar.
3. Zararlı bulunan öğeler `Karantina_Deposu` klasörüne taşınır.
4. **Karantina Bölümü** sekmesinde bir öğeye sağ tıkla → **Geri Yükle**.

## 🧪 Test etme

Masaüstünde adı `test_virus.txt` olan boş bir dosya oluştur ve taramayı çalıştır.
Dosya karantinaya alınmalıdır. Geri yüklemek için karantina sekmesinde sağ tık kullan.

## 📁 Dosyalar

| Dosya | Açıklama |
|---|---|
| `anka_security.py` | Uygulamanın tüm kaynak kodu |
| `EXE_OLUSTUR.bat` | Gerekli paketleri kurup `.exe` oluşturur |

## ❓ Sık sorunlar

- **"Python bulunamadı"**: Python'u yeniden kurup *Add python.exe to PATH* ve *py launcher* kutularını işaretle.
- **Windows SmartScreen uyarısı**: *Ek bilgi → Yine de çalıştır* seçeneğini kullan (imzasız `.exe` dosyalarında normaldir).
- **Python 3.14'te hata**: Python 3.12 veya 3.13 kurup tekrar dene.

## 📄 Lisans

MIT Lisansı. Özgürce kullanabilir, inceleyebilir ve geliştirebilirsin.

---
© 2026 AnkaGRUP · Batuhan Bulutlu
