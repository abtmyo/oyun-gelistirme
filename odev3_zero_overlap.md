## 🎮 **P5.js Ödevi — “Zero Overlap / Temassız”**

### 🎯 **Amaç**

Bu projede öğrencilerden, **çember çarpışma algoritmasını** kullanarak bir mini oyun geliştirmeleri istenir.
Amaç: ekrandaki çemberlerin **birbirine değmeden** belirli bir süre büyümesini sağlamak.
Oyunun örnek sürümünü burada oynayabilirsiniz:
👉 [https://gusanmaz.itch.io/zero-overlap](https://gusanmaz.itch.io/zero-overlap)

---

### 🧩 **Oyun Özellikleri**

* Her seviyede birkaç çember oluşturulur.
* Çemberler renklerine göre farklı hızlarda büyür:

  * 🟢 Yeşil → yavaş büyür
  * 🟡 Sarı → orta hızda büyür
  * 🔴 Kırmızı → hızlı büyür
  * ⚪️ Gri → büyümez ve taşınamaz (sabit)
* Oyuncu yalnızca sabit olmayan çemberleri **fareyle sürükleyebilir**.
* Çemberler çarpışırsa oyun biter.
* Belirli bir süre dayanılırsa sonraki seviyeye geçilir.
* Seviye ilerledikçe çember sayısı artar, büyüme hızları yükselir.

---

### 🧠 **Gerekli P5.js ve Programlama Konuları**

1. **Temel p5 yapısı** → `setup()`, `draw()` fonksiyonları
2. **Değişkenler** → `let`, `const`
3. **Koşullu ifadeler** → `if / else`, karşılaştırma operatörleri
4. **Döngüler** → `for` döngüsü (çemberleri kontrol etmek için)
5. **Fonksiyonlar** → kendi alt görevlerinizi düzenleyin
6. **Diziler** → birden fazla çemberi saklamak için
7. **Sınıflar / Nesne tabanlı programlama** → `class Circle { ... }`
8. **Fare etkileşimi** → `mousePressed()`, `mouseDragged()`, `mouseReleased()`
9. **Zaman ölçümü** → `millis()` fonksiyonu ile süre takibi
10. **Çarpışma denetimi** →

    ```js
    if (dist(x1, y1, x2, y2) < r1 + r2) { /* çarpışma */ }
    ```

---

### 🧮 **Değerlendirme Ölçütleri**

| Ölçüt                           | Açıklama                                 | Puan         |
| ------------------------------- | ---------------------------------------- | ------------ |
| Çemberlerin doğru oluşturulması | Farklı renk ve hızlarda büyüme           | 20           |
| Çarpışma kontrolü               | Oyunun doğru şekilde bitmesi             | 20           |
| Fare ile taşınabilirlik         | Sadece sabit olmayan çemberler           | 20           |
| Zorluk artışı                   | Seviye bazlı artış doğru kurgulanmış     | 20           |
| Kod düzeni ve okunabilirlik     | Anlaşılır değişken isimleri, açıklamalar | 20           |
| **Toplam**                      |                                          | **100 puan** |

---

### 🧰 **Teslim Biçimi (GitHub Classroom)**

* GitHub Classroom davet linkine (https://classroom.github.com/a/1U3utd2x) tıklayarak **kendi repo’nuzu oluşturun.**
* Çalışmanızı yalnızca p5.js’in çalışması için gerekli dosyalarla paylaşın:

  * **`sketch.js`** (zorunlu)
  * **`index.html`** (isteğe bağlı; isterseniz editor.p5js.org’dan indirilen temel şablonu ekleyebilirsiniz)
* Her şey aynı klasörde bulunmalıdır.
* **Zip dosyası yüklemeyin.** Sadece commit + push işlemi yapın.
* Kodunuzu tarayıcıda açtığınızda oyun doğrudan çalışmalıdır.

---

### 🧠 **İpuçları**

* P5.js editöründe test edip ardından GitHub’a push edin.
* Her değişiklikten sonra `git add .` → `git commit -m "update"` → `git push` adımlarını izleyin.
* `index.html` kullanıyorsanız, `<script src="sketch.js"></script>` satırının doğru olduğuna emin olun.
* Ya da yukaridaki adimlari Github.com uzerinden grafiksel arayuz yardimi ile yapabilirsiz. (Create file, edit file, commit changes)
* Kodunuzu açıklama satırlarıyla (// yorumlar) belgelendirin.

---

### 📅 **Teslim Tarihi**

> Örnek: 14 Kasım 2025, 23:59
