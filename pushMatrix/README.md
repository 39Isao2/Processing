# 座標保存と回転

現在の座標の保存と回転を使ってみましょう。

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

起点座標を計算した際に、いちいち座標を動かしたり戻したりするのが面倒,,,,

## 座標の保存 （スタック）
pushMatrixとpopMatrixを使って、座標の一時保存をします。

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
  

  fill(255,0,0);
  rect(0,0,100,100);

  
}

```

<img src="https://github.com/55Kaerukun/Processing/blob/master/images/pushMatrix2.png" width="500px">



## 実践！

```

int NUM = 720;

void setup(){
  size (500, 500);
  colorMode(HSB, 360, 100, 100, 100);
  background(0);
  noStroke();
  
  for (int i = 0; i < NUM; i++){
    pushMatrix();
    translate(random(width), random(height));
    rotate(random(radians(180)));
    fill(random(360), 100, 100, 100);
    ellipse(0, 0, 10, 50);
    popMatrix();
  }
}


```


<img src="https://github.com/55Kaerukun/Processing/blob/master/images/pushMatrix3.png" width="500px">
