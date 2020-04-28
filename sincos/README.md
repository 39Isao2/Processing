# 三角関数

クリエイティブコーディングの肝<br>
慣れるまで少し難しいけど頑張りましょう。

<img src="https://thebookofshaders.com/05/sincos.gif">

<br>

## 三角関数で円を描いてみよう！ （ellipse を使わず。）

<br>
<img src="https://thebookofshaders.com/05/sin_cos.png">
<br>

<br>


```

// ここに円を描くコード

```


## サイン波形を書いてみよう。

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
  size(500,500);
  background(0);
  //初期値は画面の中央
  posX = width/2;
  posY = height/2;
  speed = 2.0;
  theta = 0;
  amplitude = 200;
}

void draw(){
  
  fill(0,0,0,10);
  rect(0,0,width,height);
  
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
