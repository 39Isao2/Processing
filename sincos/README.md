# 三角関数

クリエイティブコーディングの肝<br>
慣れるまで少し難しいけど頑張りましょう。

<img src="https://thebookofshaders.com/05/sincos.gif">

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
// 中心を起点に
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
<strong>x座標 = 半径 * cos（θ）</strong> <br>
<strong>y座標 = 半径 * sin(θ)</strong>
<br>
<br>

```

float posX, posY;  //中心点のx, y座標
float radius; //直径
int theta = 0;  //角度
 
void setup() {
  size(500, 500);  
  noStroke();
  fill(0,255,0);
  radius = 200;
  background(0);
}
 
void draw() {
 
  //background(0);
  translate(width/2,height/2);
  

  // 円を描く
  posX = radius * cos(radians(theta));
  posY = radius * sin(radians(theta));
  ellipse(posX, posY, 10,10);
  

  theta++;
  
  //もしthetaが360以上になったら0にする。
  if (theta >= 360){
    theta = 0;
  }
  

}

```

<br>
参考:ラジアンについて https://sci-pursuit.com/math/radian.html
<br>


## サイン波形を書いてみよう。

<img src="https://github.com/55Kaerukun/Processing/blob/master/images/sin1.png" width="800px">
<br>


（最初は難しいのでsin(だんだん増える値)を入れると 
~1から1の値が返ってくると覚えればとりあえずOK！）
<br>

```

//X座標
float posX;
//Y座標
float posY;
//速度
float speed;
//角度を保存する変数
float theta;
//振幅の大きさ
float amplitude;

void setup(){
  size(1000,500);
  background(0);
  //初期値は画面の中央
  posX = width/2;
  posY = height/2;
  speed = 2.0;
  theta = 0;
  amplitude = 200;
}

void draw(){
  
  //fill(0,0,0,10);
  //rect(0,0,width,height);
  
  //画面のY座標起点を中央に下げる
  translate(0,height/2);
  
  //線なし
  noStroke();

  //塗り
  fill(0,255,255);
  

  // sin()は -1 ~ +1の間の値を返す
  // sin(経過時間)
  float posY = amplitude * sin(radians(theta));
  println(posY);
 
  //円を描画
  ellipse(posX,posY,40,40);
  
  //x座標にスピードを足す
  posX = posX + speed;
  
  //もしposXが画面幅を超えたら
  if(posX > width){
    posX = 0;
  }
  
  //角度を1度ずつ増やす
  theta = theta + 2;
  
  //もしthetaが360度を超えたら
  if(theta > 360){
    theta = 0;
  }
}


```

## だんだんと伸縮する円

```

float theta; //角度
float scale; 

void setup() {
  size(500,500);
  scale = 300;
  theta = 0;
}

void draw() {

  background(0);
  
  // 起点を中心に
  translate(width/2, height/2);
  
  // 半径を徐々に増減
  float diameter = sin(radians(theta)) * scale;
  
  // 円を描画
  ellipse(0, 0, diameter, diameter);
  
  theta++;
  
  if(theta > 360){
    theta = 0;
  }
  
}

```

