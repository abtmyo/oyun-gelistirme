# 🎮 Memory Game- Eşleştirme Oyunu - Adım Adım Kodlar

## 16 - 17 Aralık

### Adım 1

```javascript
let en = ['red', 'black', 'blue', 'green', 'white', 'yellow', 'orange', 'gray'];
let tr = ['kırmızı', 'siyah', 'mavi', 'yeşil', 'beyaz', 'sarı', 'turuncu', 'gri'];
let en_used = [false, false, false, false, false, false, false, false];
let tr_used = [false, false, false, false, false, false, false, false];

function setup() {
  createCanvas(400, 400);
  let r = allTrue(en_used);
  print(r);
}

function draw() {
  for(let y = 0; y < 400; y+= 100){
    for(let x = 0; x < 400; x += 100){
      rect(x,y,100,100);
    }
  }
}

function allTrue(a){
  for (let i = 0; i < a.length; i++){
    if (a[i] == false){
      return false;
    }
  }
  return true;
}

function selectText(){
  let r = random();
  if (r < 0.5){
  } else{
  }
}
```

### Adım 2

```javascript
let en = ['red', 'black', 'blue', 'green', 'white', 'yellow', 'orange', 'gray'];
let tr = ['kırmızı', 'siyah', 'mavi', 'yeşil', 'beyaz', 'sarı', 'turuncu', 'gri'];
let en_used = [false, false, false, false, false, false, false, false];
let tr_used = [false, false, false, false, false, false, false, false];

function setup() {
  createCanvas(400, 400);
  let r = allTrue(en_used);
  print(r);
  a = Math.floor(random(8));
  print(a);
  let word = selectText();
  print(word);
}

function draw() {
  for(let y = 0; y < 400; y+= 100){
    for(let x = 0; x < 400; x += 100){
      rect(x,y,100,100);
    }
  }
}

function allTrue(a){
  for (let i = 0; i < a.length; i++){
    if (a[i] == false){
      return false;
    }
  }
  return true;
}

function selectText(){
  let r = random();
  let p = allTrue(en_used);
  if ((r < 0.5) && !p){
    while(true){
      a = Math.floor(random(8));
      if (en_used[a] == false){
        return en[a];
      }
    }
    return en[a];
  }else{
    while(true){
      a = Math.floor(random(8));
      if (tr_used[a] == false){
        return tr[a];
      }
    }
    return tr[a];
  }
}
```

### Adım 3

```javascript
let en = ['red', 'black', 'blue', 'green', 'white', 'yellow', 'orange', 'gray'];
let tr = ['kırmızı', 'siyah', 'mavi', 'yeşil', 'beyaz', 'sarı', 'turuncu', 'gri'];
let en_used = [false, false, false, false, false, false, false, false];
let tr_used = [false, false, false, false, false, false, false, false];

function setup() {
  createCanvas(400, 400);
  let r = allTrue(en_used);
  for(let i = 0; i < 16; i++){
    let a = selectText();
    print(a);
  }
}

function draw() {
  for(let y = 0; y < 400; y+= 100){
    for(let x = 0; x < 400; x += 100){
      rect(x,y,100,100);
    }
  }
}

function allTrue(a){
  for (let i = 0; i < a.length; i++){
    if (a[i] == false){
      return false;
    }
  }
  return true;
}

function selectText(){
  let r = random();
  let p = allTrue(en_used);
  if ((r < 0.5) && !p){
    while(true){
      a = Math.floor(random(8));
      if (en_used[a] == false){
        en_used[a] = true;
        return en[a];
      }
    }
    return en[a];
  }else{
    while(true){
      a = Math.floor(random(8));
      if (tr_used[a] == false){
        tr_used[a] = true;
        return tr[a];
      }
    }
    return tr[a];
  }
}
```

### Adım 4

```javascript
let en = ['red', 'black', 'blue', 'green', 'white', 'yellow', 'orange', 'gray'];
let tr = ['kırmızı', 'siyah', 'mavi', 'yeşil', 'beyaz', 'sarı', 'turuncu', 'gri'];
let en_used = [false, false, false, false, false, false, false, false];
let tr_used = [false, false, false, false, false, false, false, false];

function setup() {
  createCanvas(400, 400);
  let r = allTrue(en_used);
  textAlign(CENTER, CENTER);
  for(let y = 0; y < 400; y+= 100){
    for(let x = 0; x < 400; x += 100){
      rect(x,y,100,100);
    }
  }
  for(let i = 0; i < 16; i++){
    let satir = floor(i / 4);
    let sutun = floor(i % 4);
    print("i:", i, "satir:", satir, "sutun:", sutun);
    let word = selectText();
    text(word, sutun * 100 + 50, satir * 100 + 50);
  }
}

function draw() {
  noLoop();
}

function allTrue(a){
  for (let i = 0; i < a.length; i++){
    if (a[i] == false){
      return false;
    }
  }
  return true;
}

function selectText(){
  let r = random();
  let p = allTrue(en_used);
  if ((r < 0.5) && !p){
    while(true){
      a = Math.floor(random(8));
      if (en_used[a] == false){
        en_used[a] = true;
        return en[a];
      }
    }
    return en[a];
  }else{
    while(true){
      a = Math.floor(random(8));
      if (tr_used[a] == false){
        tr_used[a] = true;
        return tr[a];
      }
    }
    return tr[a];
  }
}
```

### Adım 5

```javascript
let en = ['red', 'black', 'blue', 'green', 'white', 'yellow', 'orange', 'gray'];
let tr = ['kırmızı', 'siyah', 'mavi', 'yeşil', 'beyaz', 'sarı', 'turuncu', 'gri'];
let en_used = [false, false, false, false, false, false, false, false];
let tr_used = [false, false, false, false, false, false, false, false];

function setup() {
  createCanvas(400, 400);
  let r = isAllTrue(en_used);
  textAlign(CENTER, CENTER);
  for(let y = 0; y < 400; y+= 100){
    for(let x = 0; x < 400; x += 100){
      rect(x,y,100,100);
    }
  }
  for (let satir = 0; satir < 4; satir++){
    for (let sutun = 0; sutun < 4; sutun++){
      let word = selectText();
      text(word, sutun * 100 + 50, satir * 100 + 50);
    }
  }
}

function draw() {
  noLoop();
}

function isAllTrue(a){
  for (let i = 0; i < a.length; i++){
    if (a[i] == false){
      return false;
    }
  }
  return true;
}

function selectText(){
  let r = random();
  let p = isAllTrue(en_used);
  if ((r < 0.5) && !p){
    while(true){
      a = Math.floor(random(8));
      if (en_used[a] == false){
        en_used[a] = true;
        return en[a];
      }
    }
    return en[a];
  }else{
    while(true){
      a = Math.floor(random(8));
      if (tr_used[a] == false){
        tr_used[a] = true;
        return tr[a];
      }
    }
    return tr[a];
  }
}
```

### Adım 6

```javascript
let words = ['red', 'kirmizi', 'black', 'siyah', 'blue', 'mavi', 'green', 'yesil', 'white', 'beyaz', 'yellow', 'sari', 'orange', 'turuncu', 'gray', 'gri'];
let words_used = [false, false, false, false, false, false, false, false, false, false, false, false, false, false, false, false];

function setup() {
  createCanvas(400, 400);
  textAlign(CENTER, CENTER);
  for(let y = 0; y < 400; y+= 100){
    for(let x = 0; x < 400; x += 100){
      rect(x,y,100,100);
    }
  }
  for (let satir = 0; satir < 4; satir++){
    for (let sutun = 0; sutun < 4; sutun++){
      let word = selectText();
      text(word, sutun * 100 + 50, satir * 100 + 50);
    }
  }
}

function draw() {
  noLoop();
}

function isAllTrue(a){
  for (let i = 0; i < a.length; i++){
    if (a[i] == false){
      return false;
    }
  }
  return true;
}

function selectText(){
  let r = isAllTrue(words_used)
  if (r == true){
    return "ERROR";
  }
  for(;;){
    let i = floor(random(16));
    if (words_used[i] == false){
      let word = words[i];
      words_used[i] = true;
      return word;
    }
  }
}
```

### Adım 7

```javascript
let words = ['red', 'kirmizi', 'black', 'siyah', 'blue', 'mavi', 'green', 'yesil', 'white', 'beyaz', 'yellow', 'sari', 'orange', 'turuncu', 'gray', 'gri'];
let mixedWords = [];
let i = 0;

function setup() {
  createCanvas(400, 400);
  textAlign(CENTER, CENTER);
  for(let y = 0; y < 400; y+= 100){
    for(let x = 0; x < 400; x += 100){
      rect(x,y,100,100);
    }
  }
  mixedWords = shuffle(words);
  for (let satir = 0; satir < 4; satir++){
    for (let sutun = 0; sutun < 4; sutun++){
      let word = selectText();
      print(word);
      text(word, sutun * 100 + 50, satir * 100 + 50);
    }
  }
  print(mixedWords);
}

function draw() {
  noLoop();
}

function isAllTrue(a){
  for (let i = 0; i < a.length; i++){
    if (a[i] == false){
      return false;
    }
  }
  return true;
}

function selectText(){
  let word = mixedWords[i];
  i++;
  i = i % 16;
  return word;
}
```

### Adım 8

```javascript
let words = ['red', 'kirmizi', 'black', 'siyah', 'blue', 'mavi', 'green', 'yesil', 'white', 'beyaz', 'yellow', 'sari', 'orange', 'turuncu', 'gray', 'gri'];
let mixedWords = [];
let i = 0;

function setup() {
  createCanvas(400, 400);
  textAlign(CENTER, CENTER);
  for(let y = 0; y < 400; y+= 100){
    for(let x = 0; x < 400; x += 100){
      rect(x,y,100,100);
    }
  }
  mixedWords = shuffle(words);
  for (let satir = 0; satir < 4; satir++){
    for (let sutun = 0; sutun < 4; sutun++){
      let word = selectText();
      print(word);
      text(word, sutun * 100 + 50, satir * 100 + 50);
    }
  }
}

function draw() {
  noLoop();
}

function isAllTrue(a){
  for (let i = 0; i < a.length; i++){
    if (a[i] == false){
      return false;
    }
  }
  return true;
}

function selectText(){
  let word = mixedWords[i];
  i++;
  i = i % 16;
  return word;
}

function mousePressed(){
  print("MouseX:", mouseX);
  print("MouseY:", mouseY);
}
```

### Adım 9

```javascript
let words = ['red', 'kirmizi', 'black', 'siyah', 'blue', 'mavi', 'green', 'yesil', 'white', 'beyaz', 'yellow', 'sari', 'orange', 'turuncu', 'gray', 'gri'];
let mixedWords = [];
let i = 0;

function setup() {
  createCanvas(400, 400);
  textAlign(CENTER, CENTER);
  for(let y = 0; y < 400; y+= 100){
    for(let x = 0; x < 400; x += 100){
      rect(x,y,100,100);
    }
  }
  mixedWords = shuffle(words);
  for (let satir = 0; satir < 4; satir++){
    for (let sutun = 0; sutun < 4; sutun++){
      let word = selectText();
      text(word, sutun * 100 + 50, satir * 100 + 50);
    }
  }
}

function draw() {
  noLoop();
}

function isAllTrue(a){
  for (let i = 0; i < a.length; i++){
    if (a[i] == false){
      return false;
    }
  }
  return true;
}

function selectText(){
  let word = mixedWords[i];
  i++;
  i = i % 16;
  return word;
}

function mousePressed(){
  let loc = getCellLocation(mouseX, mouseY);
  print(loc[0], loc[1]);
}

function getCellLocation(x, y){
  let sutun = floor(x / 100);
  let satir = floor(y / 100);
  let loc = [satir, sutun];
  return loc;
}
```

### Adım 10

```javascript
let words = ['red', 'kirmizi', 'black', 'siyah', 'blue', 'mavi', 'green', 'yesil', 'white', 'beyaz', 'yellow', 'sari', 'orange', 'turuncu', 'gray', 'gri'];
let mixedWords = [];
let i = 0;
let gameBoard = [];

function setup() {
  createCanvas(400, 400);
  textAlign(CENTER, CENTER);
  for(let y = 0; y < 400; y+= 100){
    for(let x = 0; x < 400; x += 100){
      rect(x,y,100,100);
    }
  }
  mixedWords = shuffle(words);
  for (let satir = 0; satir < 4; satir++){
    gameBoard[satir] = [];
    for (let sutun = 0; sutun < 4; sutun++){
      let word = selectText();
      gameBoard[satir][sutun] = word;
      text(word, sutun * 100 + 50, satir * 100 + 50);
    }
  }
  print(gameBoard);
  print(gameBoard[2][0]);
}

function draw() {
  noLoop();
}

function isAllTrue(a){
  for (let i = 0; i < a.length; i++){
    if (a[i] == false){
      return false;
    }
  }
  return true;
}

function selectText(){
  let word = mixedWords[i];
  i++;
  i = i % 16;
  return word;
}

function mousePressed(){
  let loc = getCellLocation(mouseX, mouseY);
  print(loc[0], loc[1]);
}

function getCellLocation(x, y){
  let sutun = floor(x / 100);
  let satir = floor(y / 100);
  let loc = [satir, sutun];
  return loc;
}
```

### Adım 11

```javascript
let words = ['red', 'kirmizi', 'black', 'siyah', 'blue', 'mavi', 'green', 'yesil', 'white', 'beyaz', 'yellow', 'sari', 'orange', 'turuncu', 'gray', 'gri'];
let mixedWords = [];
let i = 0;
let gameBoard = [];
let satir1 = -1;
let sutun1 = -1;
let satir2 = -1;
let sutun2 = -1;

function setup() {
  createCanvas(400, 400);
  textAlign(CENTER, CENTER);
  for(let y = 0; y < 400; y+= 100){
    for(let x = 0; x < 400; x += 100){
      rect(x,y,100,100);
    }
  }
  mixedWords = shuffle(words);
  for (let satir = 0; satir < 4; satir++){
    gameBoard[satir] = [];
    for (let sutun = 0; sutun < 4; sutun++){
      let word = selectText();
      gameBoard[satir][sutun] = word;
      text(word, sutun * 100 + 50, satir * 100 + 50);
    }
  }
  print(gameBoard);
  print(gameBoard[2][0]);
}

function draw() {
  noLoop();
}

function isAllTrue(a){
  for (let i = 0; i < a.length; i++){
    if (a[i] == false){
      return false;
    }
  }
  return true;
}

function selectText(){
  let word = mixedWords[i];
  i++;
  i = i % 16;
  return word;
}

function mousePressed(){
  let loc = getCellLocation(mouseX, mouseY);
  if ((satir1 == -1) && (sutun1 == -1)){
    satir1 = loc[0];
    sutun1 = loc[1];
  }else if ((satir2 == -1) && (sutun2 == -1)){
    satir2 = loc[0];
    sutun2 = loc[1];
    let color1 = gameBoard[satir1][sutun1];
    let color2 = gameBoard[satir2][sutun2];
  }
}

function getCellLocation(x, y){
  let sutun = floor(x / 100);
  let satir = floor(y / 100);
  let loc = [satir, sutun];
  return loc;
}

function getWordIndex(arr, str){
  for(let i = 0; i < arr.length; i++){
    if (arr[i] == str){
      return i;
    }
  }
  return -1;
}
```

### Adım 12

```javascript
let words = ['red', 'kirmizi', 'black', 'siyah', 'blue', 'mavi', 'green', 'yesil', 'white', 'beyaz', 'yellow', 'sari', 'orange', 'turuncu', 'gray', 'gri'];
let mixedWords = [];
let i = 0;
let gameBoard = [];
let satir1 = -1;
let sutun1 = -1;
let satir2 = -1;
let sutun2 = -1;

function setup() {
  createCanvas(400, 400);
  textAlign(CENTER, CENTER);
  for(let y = 0; y < 400; y+= 100){
    for(let x = 0; x < 400; x += 100){
      rect(x,y,100,100);
    }
  }
  mixedWords = shuffle(words);
  for (let satir = 0; satir < 4; satir++){
    gameBoard[satir] = [];
    for (let sutun = 0; sutun < 4; sutun++){
      let word = selectText();
      gameBoard[satir][sutun] = word;
      text(word, sutun * 100 + 50, satir * 100 + 50);
    }
  }
  print(gameBoard);
  print(gameBoard[2][0]);
}

function draw() {
  noLoop();
}

function isAllTrue(a){
  for (let i = 0; i < a.length; i++){
    if (a[i] == false){
      return false;
    }
  }
  return true;
}

function selectText(){
  let word = mixedWords[i];
  i++;
  i = i % 16;
  return word;
}

function mousePressed(){
  let loc = getCellLocation(mouseX, mouseY);
  if ((satir1 == -1) && (sutun1 == -1)){
    satir1 = loc[0];
    sutun1 = loc[1];
  }else if ((satir2 == -1) && (sutun2 == -1)){
    satir2 = loc[0];
    sutun2 = loc[1];
    let color1 = gameBoard[satir1][sutun1];
    let color2 = gameBoard[satir2][sutun2];
    let ind1 = getWordIndex(words, color1);
    let ind2 = getWordIndex(words, color2);
    let a1 = floor(ind1 / 2);
    let a2 = floor(ind2 / 2);
    if (a1 == a2){
      print("Pair buldum");
    }
    satir1 = -1;
    sutun1 = -1;
    satir2 = -1;
    sutun2 = -1;
  }
}

function getCellLocation(x, y){
  let sutun = floor(x / 100);
  let satir = floor(y / 100);
  let loc = [satir, sutun];
  return loc;
}

function getWordIndex(arr, str){
  for(let i = 0; i < arr.length; i++){
    if (arr[i] == str){
      return i;
    }
  }
  return -1;
}
```

### Adım 13

```javascript
let words = ['red', 'kirmizi', 'black', 'siyah', 'blue', 'mavi', 'green', 'yesil', 'white', 'beyaz', 'yellow', 'sari', 'orange', 'turuncu', 'gray', 'gri'];
let mixedWords = [];
let i = 0;
let gameBoard = [];
let satir1 = -1;
let sutun1 = -1;
let satir2 = -1;
let sutun2 = -1;

function setup() {
  createCanvas(400, 400);
  textAlign(CENTER, CENTER);
  mixedWords = shuffle(words);
  drawGameBoard();
}

function draw() {
  noLoop();
}

function isAllTrue(a){
  for (let i = 0; i < a.length; i++){
    if (a[i] == false){
      return false;
    }
  }
  return true;
}

function selectText(){
  let word = mixedWords[i];
  i++;
  i = i % 16;
  return word;
}

function mousePressed(){
  let loc = getCellLocation(mouseX, mouseY);
  if ((satir1 == -1) && (sutun1 == -1)){
    satir1 = loc[0];
    sutun1 = loc[1];
  }else if ((satir2 == -1) && (sutun2 == -1)){
    satir2 = loc[0];
    sutun2 = loc[1];
    let color1 = gameBoard[satir1][sutun1];
    let color2 = gameBoard[satir2][sutun2];
    let ind1 = getWordIndex(words, color1);
    let ind2 = getWordIndex(words, color2);
    let a1 = floor(ind1 / 2);
    let a2 = floor(ind2 / 2);
    if (a1 == a2){
      print("Pair buldum");
    }
    satir1 = -1;
    sutun1 = -1;
    satir2 = -1;
    sutun2 = -1;
  }
}

function getCellLocation(x, y){
  let sutun = floor(x / 100);
  let satir = floor(y / 100);
  let loc = [satir, sutun];
  return loc;
}

function getWordIndex(arr, str){
  for(let i = 0; i < arr.length; i++){
    if (arr[i] == str){
      return i;
    }
  }
  return -1;
}

function drawGameBoard(){
  for(let y = 0; y < 400; y+= 100){
    for(let x = 0; x < 400; x += 100){
      rect(x,y,100,100);
    }
  }
  for (let satir = 0; satir < 4; satir++){
    gameBoard[satir] = [];
    for (let sutun = 0; sutun < 4; sutun++){
      let word = selectText();
      gameBoard[satir][sutun] = word;
      text(word, sutun * 100 + 50, satir * 100 + 50);
    }
  }
}
```

---

## 23 Aralık

### Adım 1

```javascript
let words = ['red', 'kirmizi', 'black', 'siyah', 'blue', 'mavi', 'green', 'yesil', 'white', 'beyaz', 'yellow', 'sari', 'orange', 'turuncu', 'gray', 'gri'];
let mixedWords = [];
let i = 0;
let gameBoard = [];
let satir1 = -1;
let sutun1 = -1;
let satir2 = -1;
let sutun2 = -1;

function setup() {
  createCanvas(400, 400);
  textAlign(CENTER, CENTER);
  mixedWords = shuffle(words);
  drawGameBoard();
}

function draw() {
  drawGameBoard();
}

function isAllTrue(a){
  for (let i = 0; i < a.length; i++){
    if (a[i] == false){
      return false;
    }
  }
  return true;
}

function selectText(){
  let word = mixedWords[i];
  i++;
  i = i % 16;
  return word;
}

function mousePressed(){
  let loc = getCellLocation(mouseX, mouseY);
  if ((satir1 == -1) && (sutun1 == -1)){
    satir1 = loc[0];
    sutun1 = loc[1];
  }else if ((satir2 == -1) && (sutun2 == -1)){
    satir2 = loc[0];
    sutun2 = loc[1];
    let color1 = gameBoard[satir1][sutun1];
    let color2 = gameBoard[satir2][sutun2];
    let ind1 = getWordIndex(words, color1);
    let ind2 = getWordIndex(words, color2);
    let a1 = floor(ind1 / 2);
    let a2 = floor(ind2 / 2);
    if (a1 == a2){
      print("Pair buldum");
    }else{
      print("Pair bulamadim");
    }
  }
}

function getCellLocation(x, y){
  let sutun = floor(x / 100);
  let satir = floor(y / 100);
  let loc = [satir, sutun];
  return loc;
}

function getWordIndex(arr, str){
  for(let i = 0; i < arr.length; i++){
    if (arr[i] == str){
      return i;
    }
  }
  return -1;
}

function drawGameBoard(){
  for (let satir = 0; satir < 4; satir++){
    for (let sutun = 0; sutun < 4; sutun++){
      fill('white');
      if ((satir1 == satir) && (sutun1 == sutun)){
        fill("yellow");
      }
      if ((satir2 == satir) && (sutun2 == sutun)){
        fill("orange");
      }
      rect(sutun * 100, satir * 100, 100,100);
    }
  }
  fill('black');
  for (let satir = 0; satir < 4; satir++){
    gameBoard[satir] = [];
    for (let sutun = 0; sutun < 4; sutun++){
      let word = selectText();
      gameBoard[satir][sutun] = word;
      text(word, sutun * 100 + 50, satir * 100 + 50);
    }
  }
}
```

### Adım 2

```javascript
let words = ['red', 'kirmizi', 'black', 'siyah', 'blue', 'mavi', 'green', 'yesil', 'white', 'beyaz', 'yellow', 'sari', 'orange', 'turuncu', 'gray', 'gri'];
let mixedWords = [];
let i = 0;
let gameBoard = [];
let satir1 = -1;
let sutun1 = -1;
let satir2 = -1;
let sutun2 = -1;
let counter = -1;

function setup() {
  createCanvas(400, 400);
  textAlign(CENTER, CENTER);
  mixedWords = shuffle(words);
  drawGameBoard();
}

function draw() {
  if (counter != -1){
    counter++;
  }
  if (counter == 120){
    satir1 = -1;
    sutun1 = -1;
    satir2 = -1;
    sutun2 = -1;
    counter = -1;
  }
  drawGameBoard();
}

function isAllTrue(a){
  for (let i = 0; i < a.length; i++){
    if (a[i] == false){
      return false;
    }
  }
  return true;
}

function selectText(){
  let word = mixedWords[i];
  i++;
  i = i % 16;
  return word;
}

function mousePressed(){
  let loc = getCellLocation(mouseX, mouseY);
  if ((satir1 == -1) && (sutun1 == -1)){
    satir1 = loc[0];
    sutun1 = loc[1];
  }else if ((satir2 == -1) && (sutun2 == -1)){
    satir2 = loc[0];
    sutun2 = loc[1];
    let color1 = gameBoard[satir1][sutun1];
    let color2 = gameBoard[satir2][sutun2];
    let ind1 = getWordIndex(words, color1);
    let ind2 = getWordIndex(words, color2);
    let a1 = floor(ind1 / 2);
    let a2 = floor(ind2 / 2);
    if (a1 == a2){
      print("Pair buldum");
    }else{
      print("Pair bulamadim");
    }
    counter = 0;
  }
}

function getCellLocation(x, y){
  let sutun = floor(x / 100);
  let satir = floor(y / 100);
  let loc = [satir, sutun];
  return loc;
}

function getWordIndex(arr, str){
  for(let i = 0; i < arr.length; i++){
    if (arr[i] == str){
      return i;
    }
  }
  return -1;
}

function drawGameBoard(){
  for (let satir = 0; satir < 4; satir++){
    gameBoard[satir] = [];
    for (let sutun = 0; sutun < 4; sutun++){
      fill('white');
      if ((satir1 == satir) && (sutun1 == sutun)){
        fill("yellow");
      }
      if ((satir2 == satir) && (sutun2 == sutun)){
        fill("orange");
      }
      rect(sutun * 100, satir * 100, 100,100);
      let word = selectText();
      gameBoard[satir][sutun] = word;
      fill('black');
      text(word, sutun * 100 + 50, satir * 100 + 50);
    }
  }
}
```

### Adım 3

```javascript
let words = ['red', 'kirmizi', 'black', 'siyah', 'blue', 'mavi', 'green', 'yesil', 'white', 'beyaz', 'yellow', 'sari', 'orange', 'turuncu', 'gray', 'gri'];
let mixedWords = [];
let i = 0;
let gameBoard = [];
let satir1 = -1;
let sutun1 = -1;
let satir2 = -1;
let sutun2 = -1;
let counter = -1;

function setup() {
  createCanvas(400, 400);
  textAlign(CENTER, CENTER);
  mixedWords = shuffle(words);
  drawGameBoard();
}

function draw() {
  if (counter != -1){
    counter++;
  }
  if (counter == 120){
    satir1 = -1;
    sutun1 = -1;
    satir2 = -1;
    sutun2 = -1;
    counter = -1;
  }
  drawGameBoard();
}

function isAllTrue(a){
  for (let i = 0; i < a.length; i++){
    if (a[i] == false){
      return false;
    }
  }
  return true;
}

function selectText(){
  let word = mixedWords[i];
  i++;
  i = i % 16;
  return word;
}

function mousePressed(){
  let loc = getCellLocation(mouseX, mouseY);
  if ((satir1 == -1) && (sutun1 == -1)){
    satir1 = loc[0];
    sutun1 = loc[1];
  }else if ((satir2 == -1) && (sutun2 == -1) && !((satir1 == loc[0]) && (sutun1 == loc[1]))){
    satir2 = loc[0];
    sutun2 = loc[1];
    let color1 = gameBoard[satir1][sutun1];
    let color2 = gameBoard[satir2][sutun2];
    let ind1 = getWordIndex(words, color1);
    let ind2 = getWordIndex(words, color2);
    let a1 = floor(ind1 / 2);
    let a2 = floor(ind2 / 2);
    if (a1 == a2){
      print("Pair buldum");
    }else{
      print("Pair bulamadim");
    }
    counter = 0;
  }
}

function getCellLocation(x, y){
  let sutun = floor(x / 100);
  let satir = floor(y / 100);
  let loc = [satir, sutun];
  return loc;
}

function getWordIndex(arr, str){
  for(let i = 0; i < arr.length; i++){
    if (arr[i] == str){
      return i;
    }
  }
  return -1;
}

function drawGameBoard(){
  for (let satir = 0; satir < 4; satir++){
    gameBoard[satir] = [];
    for (let sutun = 0; sutun < 4; sutun++){
      fill('white');
      if ((satir1 == satir) && (sutun1 == sutun)){
        fill("yellow");
      }
      if ((satir2 == satir) && (sutun2 == sutun)){
        fill("orange");
      }
      rect(sutun * 100, satir * 100, 100,100);
      let word = selectText();
      gameBoard[satir][sutun] = word;
      fill('black');
      text(word, sutun * 100 + 50, satir * 100 + 50);
    }
  }
}
```

### Adım 4

```javascript
let words = ['red', 'kirmizi', 'black', 'siyah', 'blue', 'mavi', 'green', 'yesil', 'white', 'beyaz', 'yellow', 'sari', 'orange', 'turuncu', 'gray', 'gri'];
let mixedWords = [];
let i = 0;
let gameBoard = [];
let satir1 = -1;
let sutun1 = -1;
let satir2 = -1;
let sutun2 = -1;
let counter = -1;
let gameStart = true;

function setup() {
  createCanvas(400, 400);
  textAlign(CENTER, CENTER);
  mixedWords = shuffle(words);
  drawGameBoard();
}

function draw() {
  if (counter != -1){
    counter++;
  }
  if (counter == 120){
    satir1 = -1;
    sutun1 = -1;
    satir2 = -1;
    sutun2 = -1;
    counter = -1;
  }
  drawGameBoard();
}

function isAllTrue(a){
  for (let i = 0; i < a.length; i++){
    if (a[i] == false){
      return false;
    }
  }
  return true;
}

function selectText(){
  let word = mixedWords[i];
  i++;
  i = i % 16;
  return word;
}

function mousePressed(){
  let loc = getCellLocation(mouseX, mouseY);
  if ((satir1 == -1) && (sutun1 == -1)){
    satir1 = loc[0];
    sutun1 = loc[1];
  }else if ((satir2 == -1) && (sutun2 == -1) && !((satir1 == loc[0]) && (sutun1 == loc[1]))){
    satir2 = loc[0];
    sutun2 = loc[1];
    let color1 = gameBoard[satir1][sutun1];
    let color2 = gameBoard[satir2][sutun2];
    let ind1 = getWordIndex(words, color1);
    let ind2 = getWordIndex(words, color2);
    let a1 = floor(ind1 / 2);
    let a2 = floor(ind2 / 2);
    if (a1 == a2){
      gameBoard[satir1][sutun1] = "";
      gameBoard[satir2][sutun2] = "";
    }else{
      print("Pair bulamadim");
    }
    counter = 0;
  }
}

function getCellLocation(x, y){
  let sutun = floor(x / 100);
  let satir = floor(y / 100);
  let loc = [satir, sutun];
  return loc;
}

function getWordIndex(arr, str){
  for(let i = 0; i < arr.length; i++){
    if (arr[i] == str){
      return i;
    }
  }
  return -1;
}

function drawGameBoard(){
  for (let satir = 0; satir < 4; satir++){
    if (gameStart == true){
      gameBoard[satir] = [];
    }
    for (let sutun = 0; sutun < 4; sutun++){
      fill('white');
      if ((satir1 == satir) && (sutun1 == sutun)){
        fill("yellow");
      }
      if ((satir2 == satir) && (sutun2 == sutun)){
        fill("orange");
      }
      rect(sutun * 100, satir * 100, 100,100);
      if (gameStart == true){
        let word = selectText();
        gameBoard[satir][sutun] = word;
      }
      let word = gameBoard[satir][sutun];
      fill('black');
      text(word, sutun * 100 + 50, satir * 100 + 50);
    }
  }
  if (gameStart == true){
    gameStart = false;
  }
}
```

### Adım 5

```javascript
let words = ['red', 'kirmizi', 'black', 'siyah', 'blue', 'mavi', 'green', 'yesil', 'white', 'beyaz', 'yellow', 'sari', 'orange', 'turuncu', 'gray', 'gri'];
let mixedWords = [];
let i = 0;
let gameBoard = [];
let satir1 = -1;
let sutun1 = -1;
let satir2 = -1;
let sutun2 = -1;
let counter = -1;
let gameStart = true;

function setup() {
  createCanvas(400, 400);
  textAlign(CENTER, CENTER);
  mixedWords = shuffle(words);
  drawGameBoard();
}

function draw() {
  if (counter != -1){
    counter++;
  }
  if (counter == 120){
    satir1 = -1;
    sutun1 = -1;
    satir2 = -1;
    sutun2 = -1;
    counter = -1;
  }
  drawGameBoard();
}

function isAllTrue(a){
  for (let i = 0; i < a.length; i++){
    if (a[i] == false){
      return false;
    }
  }
  return true;
}

function selectText(){
  let word = mixedWords[i];
  i++;
  i = i % 16;
  return word;
}

function mousePressed(){
  let loc = getCellLocation(mouseX, mouseY);
  if ((satir1 == -1) && (sutun1 == -1)){
    satir1 = loc[0];
    sutun1 = loc[1];
  }else if ((satir2 == -1) && (sutun2 == -1) && !((satir1 == loc[0]) && (sutun1 == loc[1]))){
    satir2 = loc[0];
    sutun2 = loc[1];
    let color1 = gameBoard[satir1][sutun1];
    let color2 = gameBoard[satir2][sutun2];
    let ind1 = getWordIndex(words, color1);
    let ind2 = getWordIndex(words, color2);
    let a1 = floor(ind1 / 2);
    let a2 = floor(ind2 / 2);
    if (a1 == a2){
      gameBoard[satir1][sutun1] = "";
      gameBoard[satir2][sutun2] = "";
    }else{
      print("Pair bulamadim");
    }
    counter = 0;
  }
}

function getCellLocation(x, y){
  let sutun = floor(x / 100);
  let satir = floor(y / 100);
  let loc = [satir, sutun];
  return loc;
}

function getWordIndex(arr, str){
  for(let i = 0; i < arr.length; i++){
    if (arr[i] == str){
      return i;
    }
  }
  return -1;
}

function drawGameBoard(){
  for (let satir = 0; satir < 4; satir++){
    if (gameStart == true){
      gameBoard[satir] = [];
    }
    for (let sutun = 0; sutun < 4; sutun++){
      fill('white');
      if (gameBoard[satir][sutun] == ""){
        fill('black');
      }
      if ((satir1 == satir) && (sutun1 == sutun)){
        fill("yellow");
      }
      if ((satir2 == satir) && (sutun2 == sutun)){
        fill("orange");
      }
      rect(sutun * 100, satir * 100, 100,100);
      if (gameStart == true){
        let word = selectText();
        gameBoard[satir][sutun] = word;
      }
      let word = gameBoard[satir][sutun];
      fill('black');
      text(word, sutun * 100 + 50, satir * 100 + 50);
    }
  }
  if (gameStart == true){
    gameStart = false;
  }
}
```

### Adım 6

```javascript
let words = ['red', 'kirmizi', 'black', 'siyah', 'blue', 'mavi', 'green', 'yesil', 'white', 'beyaz', 'yellow', 'sari', 'orange', 'turuncu', 'gray', 'gri'];
let mixedWords = [];
let i = 0;
let gameBoard = [];
let satir1 = -1;
let sutun1 = -1;
let satir2 = -1;
let sutun2 = -1;
let counter = -1;
let gameStart = true;

function setup() {
  createCanvas(400, 400);
  textAlign(CENTER, CENTER);
  mixedWords = shuffle(words);
  drawGameBoard();
}

function draw() {
  if (counter != -1){
    counter++;
  }
  if (counter == 120){
    satir1 = -1;
    sutun1 = -1;
    satir2 = -1;
    sutun2 = -1;
    counter = -1;
  }
  drawGameBoard();
}

function isAllTrue(a){
  for (let i = 0; i < a.length; i++){
    if (a[i] == false){
      return false;
    }
  }
  return true;
}

function selectText(){
  let word = mixedWords[i];
  i++;
  i = i % 16;
  return word;
}

function mousePressed(){
  let loc = getCellLocation(mouseX, mouseY);
  if ((satir1 == -1) && (sutun1 == -1) && gameBoard[loc[0]][loc[1]] != ""){
    satir1 = loc[0];
    sutun1 = loc[1];
  }else if ((satir2 == -1) && (sutun2 == -1) && !((satir1 == loc[0]) && (sutun1 == loc[1])) && gameBoard[loc[0]][loc[1]] != ""){
    satir2 = loc[0];
    sutun2 = loc[1];
    let color1 = gameBoard[satir1][sutun1];
    let color2 = gameBoard[satir2][sutun2];
    let ind1 = getWordIndex(words, color1);
    let ind2 = getWordIndex(words, color2);
    let a1 = floor(ind1 / 2);
    let a2 = floor(ind2 / 2);
    if (a1 == a2){
      gameBoard[satir1][sutun1] = "";
      gameBoard[satir2][sutun2] = "";
    }else{
      print("Pair bulamadim");
    }
    counter = 0;
  }
}

function getCellLocation(x, y){
  let sutun = floor(x / 100);
  let satir = floor(y / 100);
  let loc = [satir, sutun];
  return loc;
}

function getWordIndex(arr, str){
  for(let i = 0; i < arr.length; i++){
    if (arr[i] == str){
      return i;
    }
  }
  return -1;
}

function drawGameBoard(){
  for (let satir = 0; satir < 4; satir++){
    if (gameStart == true){
      gameBoard[satir] = [];
    }
    for (let sutun = 0; sutun < 4; sutun++){
      fill('white');
      if (gameBoard[satir][sutun] == ""){
        fill('black');
      }
      if ((satir1 == satir) && (sutun1 == sutun)){
        fill("yellow");
      }
      if ((satir2 == satir) && (sutun2 == sutun)){
        fill("orange");
      }
      rect(sutun * 100, satir * 100, 100,100);
      if (gameStart == true){
        let word = selectText();
        gameBoard[satir][sutun] = word;
      }
      let word = gameBoard[satir][sutun];
      fill('black');
      text(word, sutun * 100 + 50, satir * 100 + 50);
    }
  }
  if (gameStart == true){
    gameStart = false;
  }
}
```

### Adım 7

```javascript
let words = ['red', 'kirmizi', 'black', 'siyah', 'blue', 'mavi', 'green', 'yesil', 'white', 'beyaz', 'yellow', 'sari', 'orange', 'turuncu', 'gray', 'gri'];
let mixedWords = [];
let i = 0;
let gameBoard = [];
let satir1 = -1;
let sutun1 = -1;
let satir2 = -1;
let sutun2 = -1;
let counter = -1;
let gameStart = true;
let matchedPair = 0;

function setup() {
  createCanvas(400, 400);
  textAlign(CENTER, CENTER);
  mixedWords = shuffle(words);
  drawGameBoard();
}

function gameWin(){
  background("green");
  textAlign(CENTER, CENTER);
  text("TEBRIKLER!",width/2,height/2);
}

function draw() {
  if(matchedPair == 8){
    return;
  }
  if (counter != -1){
    counter++;
  }
  if (counter == 30){
    satir1 = -1;
    sutun1 = -1;
    satir2 = -1;
    sutun2 = -1;
    counter = -1;
  }
  drawGameBoard();
}

function isAllTrue(a){
  for (let i = 0; i < a.length; i++){
    if (a[i] == false){
      return false;
    }
  }
  return true;
}

function selectText(){
  let word = mixedWords[i];
  i++;
  i = i % 16;
  return word;
}

function mousePressed(){
  let loc = getCellLocation(mouseX, mouseY);
  if ((satir1 == -1) && (sutun1 == -1) && gameBoard[loc[0]][loc[1]] != ""){
    satir1 = loc[0];
    sutun1 = loc[1];
  }else if ((satir2 == -1) && (sutun2 == -1) && !((satir1 == loc[0]) && (sutun1 == loc[1])) && gameBoard[loc[0]][loc[1]] != ""){
    satir2 = loc[0];
    sutun2 = loc[1];
    let color1 = gameBoard[satir1][sutun1];
    let color2 = gameBoard[satir2][sutun2];
    let ind1 = getWordIndex(words, color1);
    let ind2 = getWordIndex(words, color2);
    let a1 = floor(ind1 / 2);
    let a2 = floor(ind2 / 2);
    if (a1 == a2){
      gameBoard[satir1][sutun1] = "";
      gameBoard[satir2][sutun2] = "";
      matchedPair++;
      if (matchedPair == 8){
        gameWin();
      }
    }else{
      print("Pair bulamadim");
    }
    counter = 0;
  }
}

function getCellLocation(x, y){
  let sutun = floor(x / 100);
  let satir = floor(y / 100);
  let loc = [satir, sutun];
  return loc;
}

function getWordIndex(arr, str){
  for(let i = 0; i < arr.length; i++){
    if (arr[i] == str){
      return i;
    }
  }
  return -1;
}

function drawGameBoard(){
  for (let satir = 0; satir < 4; satir++){
    if (gameStart == true){
      gameBoard[satir] = [];
    }
    for (let sutun = 0; sutun < 4; sutun++){
      fill('white');
      if (gameBoard[satir][sutun] == ""){
        fill('black');
      }
      if ((satir1 == satir) && (sutun1 == sutun)){
        fill("yellow");
      }
      if ((satir2 == satir) && (sutun2 == sutun)){
        fill("orange");
      }
      rect(sutun * 100, satir * 100, 100,100);
      if (gameStart == true){
        let word = selectText();
        gameBoard[satir][sutun] = word;
      }
      let word = gameBoard[satir][sutun];
      fill('black');
      text(word, sutun * 100 + 50, satir * 100 + 50);
    }
  }
  if (gameStart == true){
    gameStart = false;
  }
}
```

### Adım 8

```javascript
let words = ['red', 'kirmizi', 'black', 'siyah', 'blue', 'mavi', 'green', 'yesil', 'white', 'beyaz', 'yellow', 'sari', 'orange', 'turuncu', 'gray', 'gri'];
let mixedWords = [];
let i = 0;
let gameBoard = [];
let satir1 = -1;
let sutun1 = -1;
let satir2 = -1;
let sutun2 = -1;
let counter = -1;
let gameStart = true;
let matchedPair = 0;

function setup() {
  createCanvas(400, 400);
  textAlign(CENTER, CENTER);
  mixedWords = shuffle(words);
  drawGameBoard();
}

function gameWin(){
  background("green");
  textAlign(CENTER, CENTER);
  text("TEBRIKLER!",width/2,height/2);
}

function draw() {
  if (isGameBoardEmpty() == true){
    return;
  }
  if (counter != -1){
    counter++;
  }
  if (counter == 30){
    satir1 = -1;
    sutun1 = -1;
    satir2 = -1;
    sutun2 = -1;
    counter = -1;
  }
  drawGameBoard();
}

function isAllTrue(a){
  for (let i = 0; i < a.length; i++){
    if (a[i] == false){
      return false;
    }
  }
  return true;
}

function selectText(){
  let word = mixedWords[i];
  i++;
  i = i % 16;
  return word;
}

function mousePressed(){
  let loc = getCellLocation(mouseX, mouseY);
  if ((satir1 == -1) && (sutun1 == -1) && gameBoard[loc[0]][loc[1]] != ""){
    satir1 = loc[0];
    sutun1 = loc[1];
  }else if ((satir2 == -1) && (sutun2 == -1) && !((satir1 == loc[0]) && (sutun1 == loc[1])) && gameBoard[loc[0]][loc[1]] != ""){
    satir2 = loc[0];
    sutun2 = loc[1];
    let color1 = gameBoard[satir1][sutun1];
    let color2 = gameBoard[satir2][sutun2];
    let ind1 = getWordIndex(words, color1);
    let ind2 = getWordIndex(words, color2);
    let a1 = floor(ind1 / 2);
    let a2 = floor(ind2 / 2);
    if (a1 == a2){
      gameBoard[satir1][sutun1] = "";
      gameBoard[satir2][sutun2] = "";
      matchedPair++;
      if (isGameBoardEmpty() == true){
        gameWin();
      }
    }else{
      print("Pair bulamadim");
    }
    counter = 0;
  }
}

function getCellLocation(x, y){
  let sutun = floor(x / 100);
  let satir = floor(y / 100);
  let loc = [satir, sutun];
  return loc;
}

function getWordIndex(arr, str){
  for(let i = 0; i < arr.length; i++){
    if (arr[i] == str){
      return i;
    }
  }
  return -1;
}

function drawGameBoard(){
  for (let satir = 0; satir < 4; satir++){
    if (gameStart == true){
      gameBoard[satir] = [];
    }
    for (let sutun = 0; sutun < 4; sutun++){
      fill('white');
      if (gameBoard[satir][sutun] == ""){
        fill('black');
      }
      if ((satir1 == satir) && (sutun1 == sutun)){
        fill("yellow");
      }
      if ((satir2 == satir) && (sutun2 == sutun)){
        fill("orange");
      }
      rect(sutun * 100, satir * 100, 100,100);
      if (gameStart == true){
        let word = selectText();
        gameBoard[satir][sutun] = word;
      }
      let word = gameBoard[satir][sutun];
      fill('black');
      text(word, sutun * 100 + 50, satir * 100 + 50);
    }
  }
  if (gameStart == true){
    gameStart = false;
  }
}

function isGameBoardEmpty(){
  for (let satir = 0; satir < 4; satir++){
    for(let sutun =0; sutun < 4; sutun++){
      if (gameBoard[satir][sutun] != ""){
        return false;
      }
    }
  }
  return true;
}
```
