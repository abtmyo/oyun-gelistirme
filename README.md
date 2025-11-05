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


