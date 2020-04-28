# 座標保存と回転

現在の座標の保存と回転を使ってみましょう。

<img src="https://github.com/55Kaerukun/Processing/blob/master/images/pushMatrix.png" width="500px">

## translateで座標を移動してみる。

```
size(300,300);

// 一つ目の四角
rect(0, 0, 30, 20);

// 座標移動
translate(width/2, height/2); 
// 二つ目の四角
rect(0, 0, 30, 20);

// さらに座標移動
translate(100, 30); 
rect(0, 0, 30, 20);

```

いちいち座標を動かしたり戻したりするのが面倒,,,,

## 座標の保存 （スタック）
pushMatrixとpopMatrixを使って、座標の一時保存をします。

<img src="https://github.com/55Kaerukun/Processing/blob/master/images/pushMatrix2.png" width="500px">

```
void setup(){
  size(300,300);
  rectMode(CENTER);
}

void draw(){
  
  background(255);
  
  // 原点を中心に
  translate(width/2, height/2);
  
  // pushMatrix ~ popMatrixの間の座標空間が保存される
  pushMatrix();
      rotate(radians(45));
      fill(255,255,0);
      rect(0,0,100,100);
  popMatrix();
  
  pushMatrix();
    fill(255,0,0);
    rect(0,0,100,100);
  popMatrix();
  
}

```





## 実践！

<img src="https://github.com/55Kaerukun/Processing/blob/master/images/pushMatrix3.png" width="500px">

```

size (1000, 500);
colorMode(HSB, 360, 100, 100, 100);
background(100,100,0,100);
noStroke();
smooth();
rectMode(CENTER);

for (int i = 0; i < 720; i++){
  pushMatrix();
  translate(random(width), random(height));
  rotate(random(radians(180)));
  //scale(random(0.5, 1));
  fill(360, random(100), 100, 100);
  ellipse(0, 0, 10, 50);
  popMatrix();
}


```
