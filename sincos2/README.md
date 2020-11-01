# 三角関数

クリエイティブコーディングの肝<br>
慣れるまで少し難しいけど頑張りましょう。

<img src="https://thebookofshaders.com/05/sincos.gif">
<br>

この2つの作品も三角関数（サイン、コサイン）を使ってでできています。<br><br>
<img src="https://github.com/55Kaerukun/Processing/blob/master/images/kyumen.png" width="500px">
<br>
<br>
<img src="https://github.com/55Kaerukun/Processing/blob/master/images/sin.png" width="500px">
<br>
<br>
PVなどにも使われてます。<br>
https://www.youtube.com/watch?v=Ga17MGaytbk


<br>

## 三角関数で円を描いてみよう！ （ellipse を使わず。）

<br>
<img src="https://github.com/55Kaerukun/Processing/blob/master/images/sin_cos.png">
<br>

<br>

## 三角関数を使って円を描くときは中心を起点にするとやりやすい。
（三角関数や3Dを扱う時によく使います。）
<br>
```
// translate(起点のx座標, 起点のy座標)
// 中心を起点に （drawの中に記述しないといけない）
translate(width/2, height/2
```

<br>

```
// とりあえずellipseで中心に円を描く
size(500,500);
translate(width/2,height/2);
ellipse(0,0,100,100);

```


冷静になると難しくないので公式を覚えて描いてみよう！<br>
これだけ覚えれば大丈夫！<br><br>
<strong>x座標 = 半径 * cos(θ)</strong> <br>
<strong>y座標 = 半径 * sin(θ)</strong>
<br>
<br>

```

float posX, posY;  //中心点のx, y座標
float radius; // 半径
int theta;  //角度
 
void setup() {
  size(500, 500);  
  noStroke();
  fill(255);
  radius = 200;
  theta = 0;
  background(233,178,27);
}
 
void draw() {
 
  translate(width/2,height/2);
  
  // 円を描く (落ちついて)
  posX = radius * cos(radians(theta));
  posY = radius * sin(radians(theta));
  ellipse(posX, posY, 10,10);
  
  // 角度更新
  theta++;
  
}

```

<br>
参考:ラジアンについて https://sci-pursuit.com/math/radian.html
<br>


## サイン波形を書いてみよう。

<img src="https://github.com/55Kaerukun/Processing/blob/master/images/bgsin.png" width="500px">
<br>


（最初は難しいのでsin(だんだん増える値)を入れると 
~1から1の値が返ってくると覚えればとりあえずOK！）
<br>

```
//X座標
float posX, posY;
//速度
float speed;
//角度を保存する変数
float theta;
//振幅の大きさ
float amplitude;

// ellipseのサイズ
float size;

void setup(){
  size(700,500);
  posX = 0;
  posY = 0;
  speed = 2.0;
  theta = 0;
  amplitude = 0;
  background(233,178,27);
}

void draw(){
  
  //画面のY座標起点を中央に下げる
  translate(width/2,0);
  
  noStroke();

  // sin()は -1 ~ +1の間の値を返す
  // sin(経過時間)
  float posX = amplitude * sin(radians(theta));
  println(posY);
 
  //円を描画
  size +=0.5;
  ellipse(posX,posY,size,size);
  
  //x座標にスピードを足す
  posY = posY + speed;
  
  //もしposXが画面幅を超えたら
  if(posY > height){
    // 背景クリア
    background(233,178,27);
    posX = random(width);
    posY = 0;
    size = 0;
  }
  
  //角度を1度ずつ増やす
  theta = theta + 2;
}

```

## だんだんと伸縮する円

```

int theta; // θ
float scale; // スケール
float radius; //半径

void setup() {
  size(500,500);
  scale = 300;
  theta = 0;
  radius = 0;
  noStroke();
  fill(255);
  background(233,178,27);
}

void draw() {

  background(233,178,27);
  
  // 起点を中心に
  translate(width/2, height/2);
  
  // 円の半径
  radius = sin(radians(theta)) * scale;
  
  // 円を描画
  ellipse(0, 0, radius, radius);
  
  // 角度更新
  theta++;
  
  if(theta > 360){
    theta = 0;
  }
  
}

```

