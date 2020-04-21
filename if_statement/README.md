# 条件分岐

## バウンドする円
前回のアニメーションしていた円をバウンドさせてみましょう！<br>

<br>
<img src="https://github.com/55Kaerukun/Processing/blob/master/images/sample4..png" width="800px">
<br>

### 左右にバウンド
```

int posX;
int posY;
int speed;

void setup(){
  // 背景サイズ
  size(500,500);
  
  // 初位置
  posX = width/2;
  posY = height/2;
  
  // スピード
  speed = 3.0;
  
  noStroke();
}


void draw(){
  // 背景塗り潰し
  background(255,255,255);
  
  // 色設定
  fill(0,255,0);
 
  // 丸の位置移動
  posX = posX + speed;
  
  
  //壁にぶつかっていたら-1をかける
  if (posX > width || posX < 0) {
    speed *= -1;
  }
 
  //丸を書く
  ellipse(posX, posY, 50, 50);
  
}
```

### 上下左右にバウンド
変数sppdをもう一つY用に作るとずれる<br>
```
//グローバル変数
//x座標
int posX;
int posY;
int speedX;
int speedY;
int diameter; //円の直径

void setup(){
  size(500,500);
  background(255);
  posX = width/2;
  posY = height/2;
  speedX = 4;
  speedY = 2;
  diameter = 30;
}


void draw(){
  
  background(255);
  
  // 円の位置更新
  posX = posX + speedX;
  posY = posY + speedY;
  
  //もし、posXが画面幅（width）より大きくなったら
  if(posX > width){
    //speedXに-1をかける
    speedX = speedX * -1;
  }
  //もし、posXが0より小さくなったら
  if(posX < 0){
    //speedXに-1をかける
    speedX = speedX * -1;
  }
  
  
  //もし、posYが画面高さより大きくなったら
  if(posY > height){
    speedY = speedY * -1;
  }
  //もし,posYが0より小さくなったら
  if(posY < 0 + diameter/2){
    speedY = speedY * -1;
  }
  
  // 円の描画
  fill(0,255,0);
  ellipse(posX,posY,diameter,diameter);
  
}
```


<br>
<br>
<br>

# 配列

値を順序付けてたくさんしまえるローカールームのような存在。<br>
（配列も変数。）宣言方法 ↓ <br><br>

### 型[] 変数名 = new 型[個数]<br>

### 例: ランダムに3つの円を描く
```
//円の個数
int NUM = 3;

// 円の座標
float[] posX = new float[NUM];
float[] posY = new float[NUM];

//円の直径
float[] diameter = new float[NUM];

void setup(){
  
  size(500,500);
  
  // X座標
  posX[0] = random(0,width);
  posX[1] = random(0,width);
  posX[2] = random(0,width);
  
  // Y座標
  posY[0] = random(0,height);
  posY[1] = random(0,height);
  posY[2] = random(0,height);
  
  // 半径
  diameter[0] = random(10,50);
  diameter[1] = random(10,50);
  diameter[2] = random(10,50);
  
}

void draw(){
  background(255);
  fill(255,0,255);
  ellipse(posX[0],posY[0],diameter[0],diameter[0]);
  ellipse(posX[1],posY[1],diameter[1],diameter[1]);
  ellipse(posX[2],posY[2],diameter[2],diameter[2]);
}


```


# for文

<br>
配列と相性がよく、一気に大量の処理が可能。
<br>



```

//円の個数
int NUM = 50;

// 円の座標
float[] posX = new float[NUM];
float[] posY = new float[NUM];

//円の直径
float[] diameter = new float[NUM];

void setup(){
  
  size(500,500);
  
  for(int i = 0; i<NUM; i++){
    posX[i] = random(0,width);
    posY[i] = random(0,height);
    diameter[i] = random(10,50);
  }
}

void draw(){
  background(255);
  fill(255,0,255);
  
  for(int i = 0; i<NUM; i++){
    ellipse(posX[i],posY[i],diameter[i],diameter[i]);
  }
}

```

#バウンドのアニメーションを配列 + for文で大量表示させてみよう！
  for(int i = 0; i<NUM; i++){の
  for(int i = 0; i<NUM; i++){
