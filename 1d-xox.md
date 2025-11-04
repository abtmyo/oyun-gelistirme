## 🎮 1D XOX Alıştırması**

### 🎯 **Amaç**
Bu projede öğrencilerden, verilen **başlangıç kodunu** kullanarak bir **ilerlemeli XOX çizgi oyunu** geliştirmeleri istenir. Amaç: yatay bir çizgide **XOX** deseni yakalayarak seviyeleri artırmak ve zorluğu kademeli olarak yükseltmek. Oyunun örnek sürümünü burada oynayabilirsiniz: 👉 [https://gusanmaz.itch.io/xox-1d](https://gusanmaz.itch.io/xox-1d)

---

### 🧩 **Oyun Özellikleri**
* Oyun **3 hücre** ile başlar (yatay 1D tahta).
* Oyuncular fare ile hücrelere sırayla **X** ve **O** yerleştirir (X başlar).
* **XOX** deseni yakalandığında:
  * Kazanan **kırmızı çizgi** 1 saniye gösterilir.
  * Sonra yeni seviye başlar (+1 hücre eklenir).
* Hücreler dolarsa ve **kazanan yoksa**, aynı seviye **tekrar başlar**.
* Seviyeler **20'ye** kadar artar; 20. seviyeden sonra **"Oyun Tamamlandı!"** mesajı gösterilir.
* Canvas boyutu **sabit 600x100**; hücreler **kare** şeklinde ve mümkün olduğunca büyük olacak şekilde boyutlandırılır.
* Her seviyede tahta temizlenir, X ile başlar.

---

### 🧠 **Gerekli P5.js ve Programlama Konuları**
1. **Temel p5 yapısı** → `setup()`, `draw()` fonksiyonları
2. **Değişkenler** → `let`, `const` (seviye, zaman takibi için)
3. **Koşullu ifadeler** → `if / else`, karşılaştırma operatörleri (kazanan kontrolü için)
4. **Döngüler** → `for` döngüsü (ızgara çizimi ve desen kontrolü için)
5. **Fonksiyonlar** → kendi alt görevlerinizi düzenleyin (örneğin, seviye başlatma veya çizgi çizme; zorunlu değil ama kodunuzu temiz tutar)
6. **Diziler** → birden fazla hücreyi saklamak için (`squares` dizisi)
7. **Fare etkileşimi** → `mousePressed()` (hücre seçimi için)
8. **Zaman ölçümü** → `millis()` fonksiyonu ile 5 saniye gecikme takibi


---

### 🧰 **Teslim Biçimi (GitHub Classroom)**
* GitHub Classroom davet linkine ([https://classroom.github.com/a/p5bhtIuA](https://classroom.github.com/a/p5bhtIuA)) tıklayarak **kendi repo’nuzu oluşturun.**
* Çalışmanızı yalnızca p5.js’in çalışması için gerekli dosyalarla paylaşın:
  * **sketch.js** (zorunlu)
  * **index.html** (isteğe bağlı; isterseniz editor.p5js.org’dan indirilen temel şablonu ekleyebilirsiniz)
* Her şey aynı klasörde (reponun kök dizininde) bulunmalıdır.
* **Zip dosyası yüklemeyin.**
* **sketch.js** dosyası [https://editor.p5js.org/](https://editor.p5js.org/) bağlantısından oluşturulan yeni bir sketch'e kopyalandığında oyun sorunsuz çalışabilmelidir.

**Başlangıç Kodu:** Aşağıdaki kodu `sketch.js` dosyanıza kopyalayın ve üzerine geliştirin.

```js
let squares = [];
let currentLetter = "X";
let won = false;
let cellNumber = 10;
let cellLen;

function setup() {
  createCanvas(600, 100);
  cellLen = width / cellNumber;
  for (i = 0; i < 600; i++){
    line(i * cellLen, 0, i * cellLen, cellLen);
  }

  for (i = 0; i < cellNumber; i++){
    squares[i] = "";
  }

  textAlign(CENTER, CENTER);
  textSize(20);
}

function draw() {

}

function mousePressed(){
  let cellIndex = Math.floor(mouseX / cellLen)
  let xCenter = cellIndex * cellLen + (cellLen / 2)
  let yCenter = (cellLen / 2)
  if ((squares[cellIndex] == "") && (won == false)){
    text(currentLetter, xCenter, yCenter)
    squares[cellIndex] = currentLetter
    if (currentLetter == "X"){
      currentLetter = "O";
    }else{
      currentLetter = "X";
    }
  }

  //Bu cagri yerine altta tanimladigimiz printBoard fonksiyonuna cagri yapiyoruz.
  //print(squares); 
  printBoard(squares);

  result = isGameOver(squares)
  if (result >= 0){
    print("Win");
    won = true;
    startX = result * cellLen + (cellLen / 2);
    endX = startX + cellLen * 2
    line(startX, cellLen/2, endX, cellLen / 2);
  }
}

function isGameOver(s){
  for (let i = 0; i <= s.length - 3; i++){
    if (s[i] == "X" && s[i + 1] == "O" && s[i + 2] == "X"){
      return i;
    }
  }
  return -1;
}

function printBoard(s) {
  let boardStr = "|"
  for (let i = 0; i < s.length; i++) {
    if (s[i] == ""){
      boardStr += " ";
    }else{
      boardStr += s[i];
    }
    boardStr += "|";
  }
  print(boardStr);
}
```

---

### 🧠 **İpuçları**
* Her değişiklikten sonra `git add . → git commit -m "update" → git push` adımlarını izleyin.
* Ya da yukarıdaki adımları Github.com üzerinden grafiksel arayüz yardımı ile yapabilirsiniz. (Create file, edit file, commit changes)
* Github kaynaklı yaşayacağınız sorunlar için arkadaşlarınızdan yardım alabilir ya da dersin hocası ile iletişime geçebilirsiniz.
* Kodunuzu açıklama satırlarıyla (`// yorumlar`) belgelendirin.
* Kodunuzda yapilan bazi isleri fonksiyon olarak yazmaya calisin.

---

### 📅 **Teslim Tarihi**
> 5 Kasım 2025, 13:00
