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
変数を順序付けてたくさんしまえるローカールームのような存在。


### mouseを使った例
<br>
<img src="https://github.com/55Kaerukun/Processing/blob/master/images/intaraction_sample.png" width="800px">
<br>


### マウスの座標取得
mouseX (現在のマウスのx座標)<br>
mouseY (現在のマウスのY座標)<br>
```
// 例
ellipse(mouseX,mouseY,100, 100);
```

### 乱数の生成
random(255); 0以上、255未満の数
random(30,100); 20以上、100未満の数
```
// 例
fill(random(255),random(255),random(255));
```


<br>
<br>

# 変数
変数とは値をいれる箱のこと。C言語やJavaScript、ほぼ全てのプログラム言語で利用する重要概念。<br>
processing初級では、主に数字や真偽地(true, false)を入れたりするのに利用する。<br>

### 型 名前 = 値; 
### int radius = 100;<br>
使用例: ellipse(250,250,radius,radius);<br>
radius = 200;<br>
のように、何度も上書きできる。<br>
<br>
<img src="https://github.com/55Kaerukun/Processing/blob/master/images/sample2.png" width="800px">
<br>
<br>

### 型の種類

<br>

型 | 内容
--- | ---
int | 整数
float | 少数
boolean | 真偽値
String | 文字列
PImage | 画像

<br>

# アニメーションの基礎
<br>
<br>
変数を使って、座標を少しずつ移動させてアニメーションを実現させる<br>

```
// 現在のposXの値に1ずつプラスする
posX = posX + 1;
```

<br>
<img src="https://github.com/55Kaerukun/Processing/blob/master/images/sample3.png" width="800px">
<br>

```
float posX = 250;

void setup(){
  size(500,500);
}

void draw(){
  // 白で再度塗りつぶす
  background(255,255,255);
  fill(0,0,255);
  
  ellipse(posX,250,50,50);
  
  // x座標の更新
  posX = posX+1;
}
```


### if文で、画面右までに行ったら左に戻る

```
void draw(){
  // 白で再度塗りつぶす
  background(255,255,255);
  fill(0,0,255);
  
  ellipse(posX,250,50,50);
  
  // x座標の更新
  posX = posX+1;
  
  /*
  if(posX > 500){
     posX = 0;
  }
  */
  
  if(posX > 550){
     posX = -50;
  }
  
}
```

<br>
問題！posYにして、上下運動に変更してみよう！<br><br>
問題！丸を二個にして、クロスするアニメーションを作ろう。

### 条件分岐(if文)は次回で詳しく！！
