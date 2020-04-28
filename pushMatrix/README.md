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

いちいち座標を動かしたり戻したりするのが面倒,,,,

## 



## 綺麗なサンプル

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
