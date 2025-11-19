# Oyun Gelistirme

## Odev 0

Kendinizi README.md dosyasinda (Isim, ogrenci no, programlama gecmisi vb.) anlatiniz.

https://classroom.github.com/a/lTDcrdGL

## Videolar

https://www.youtube.com/playlist?list=PL8dPuuaLjXtPTrc_yg73RghJEOdobAplG (Crash Course Playlist)

https://www.youtube.com/watch?v=GoyGlyrYb9c&t=325s (Ahoy)

https://www.youtube.com/watch?v=uuxoThzFPPw (Cold Fusion)

https://www.youtube.com/watch?v=argpSxB1NQE (The Entire History of Video Games)

## Kitaplar

The Art of Game Design: A Book of Lenses (https://www.amazon.com/Art-Game-Design-Lenses-Third/dp/1138632058)

The Art of Game Design: Deck of Lenses Ucretsiz (https://deck.artofgamedesign.com/#/menu/0/?lang=en)

## Odev Kaynaklari

2. Odev

* https://chatgpt.com/share/68f8a70a-0570-8009-90b3-de51b38d2ddb
*  https://gusanmaz.github.io/chimp.html


```python
/*let squares = [["", "", "", ""],
              ["", "", "", ""],
              ["", "", "", ""],
              ["", "", "", ""],
              ["", "", "", ""],
              ["", "", "", ""]];*/

//let squares = [];


function create2DArray(){
  sqaures = [];
  for (let i = 0; i < 6; i++){
    squares[i] = [];
    for(let j = 0; j < 4; j++){
      squares[i][j] = "";
    }
  }
  return squares;
}

let squares = [];
let letter = "X";

function setup() {
  createCanvas(600, 400);
  drawBoard();
  textAlign(CENTER, CENTER);
  textSize(24);
  //initSquares();
  squares = create2DArray();
  print(squares);
  
}

function draw() {
  //background(220);
}

function drawBoard(){
  for (let i = 0; i < 7; i++){
    line(i * 100, 0, i * 100, 400);
  }
  
  for (let j = 0; j < 5; j++){
    line(0, j * 100, 600, j * 100);
  }
}

function mousePressed(){
  let xInd = Math.floor(mouseX / 100);
  let yInd = Math.floor(mouseY / 100);
  print("XInd:" + xInd);
  print("YInd:" + yInd);
  let xCenter = xInd * 100 + (100 / 2);
  let yCenter = yInd * 100 + (100 / 2);
  if (squares[xInd][yInd] == ""){
    text(letter, xCenter, yCenter);
    squares[xInd][yInd] = letter;
    if (letter == "X"){
      letter = "O";
    }else{
      letter = "X";
    }
    
    for (let rowInd = 0; rowInd < 4; rowInd++){
      for(let colInd = 0; colInd < 4; colInd++){
      if ((squares[colInd][rowInd] == "X") && (squares[colInd + 1][rowInd] == "O") && (squares[colInd + 2][rowInd] == "X")){
        print("Win");
      }
    }
    }
    
    
    
  }
  //text("A", xCenter, yCenter);
  //squares[xInd][yInd] = "A";
  print(squares);
}

```

## 19 Kasim 2025 

### Kismi Wordle Oyun Kodu (Derste Yazilan)


```js
let data;
let words

function preload() {
  // Dosya icerigi https://github.com/stuartpb/wordles baglantisindan alinmistir.
  data = loadJSON("wordles.json", jsonLoaded);
}

function jsonLoaded(result) {
  words = Object.values(result);
}


function setup() {
  createCanvas(400, 400);
  print(words);
  print(words[0]);
  print(words.length);
  /*for(let i = 0; i < 100; i++){
    let word = selectWord(words);
    print(word)
  }*/

  //let r = isValidWord2("cigar", words);
  //print(r);

  let l = wordControl("aeghh", "ahgyh");
  print(l);
}

function draw() {
  background(220);
}

function selectWord(wlist){
  let ind = Math.floor(random(0, wlist.length));
  return wlist[ind];
}

function selectWord2(wlist){
  return wlist[Math.floor(random(0, wlist.length))];
}

function selectWord3(wlist){
  return random(wlist);
}

// shuffle cagrisi diziden rastgele kelime secmek icin maliyetli.
function selectWord4(wlist){
  //shuffle(wlist);
  //return wlist[0];
  return shuffle(wlist)[0];
}

//Linear Search - Dogrusal Arama https://www.youtube.com/watch?v=SByG6SZdPQw

function isValidWord(wlist, candidate){
  for(let i = 0; i < wlist.length; i++){
    if (wlist[i] == candidate){
      return true;
    }
  }

  return false;
}

function isValidWord2(candidate, wlist){
  for(let i = 0; i < wlist.length; i++){
    if (wlist[i] == candidate){
      return true;
    }
  }

  return false;

}

function wordControl(aim, guess){
  let greenIndices = [];
  for(let i = 0; i < aim.length; i++){
    if (aim[i] == guess[i]){
      greenIndices[greenIndices.length] = i;
    }
  }
  return greenIndices;
}
```

https://editor.p5js.org/gusanmaz/sketches/QEE7PUQV9
Wordle kodunu son iki derste gosterilen VSCode ya da WebStorm editorlerinde de yazabilirsiniz.

#### Naming Conventions

* https://www.youtube.com/watch?v=UPNLmdRekFA&t=11s
* https://www.verimix.com.tr/yazilimda-adlandirma-kurallari/





