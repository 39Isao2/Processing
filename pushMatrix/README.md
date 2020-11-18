# 座標保存と回転

現在の座標の保存と回転を使ってみましょう。


<!--

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

-->

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



## レイヤーを増やす

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
      rotate(radians(frameCount*2.0));
      fill(255,255,0);
      rect(0,0,100,100);
  popMatrix();
  
  pushMatrix();
      rotate(radians(frameCount * 0.5));
      fill(0,0,255);
      rect(0,0,100,100);
  popMatrix();
  

  fill(255,0,0);
  rect(0,0,50,50);
 
}


```



## サンプル作品

```

int NUM = 100;
float[] hue = new float[NUM];
float[] rectPosX = new float[NUM];
float[] rectPosY = new float[NUM];

void setup(){
  size (500, 500);
  colorMode(HSB, 360, 100, 100, 100);
  background(255);
  noStroke();
  rectMode(CENTER);
  
  for(int i = 0; i<NUM; i++){
     hue[i] = random(360);
     rectPosX[i] = random(width);
     rectPosY[i] = random(height);
  }
  
}


void draw(){
  
  background(0,100,0,100);
  
  for(int i = 0; i<NUM; i++){
    fill(hue[i],100,100,100);
    rect(rectPosX[i], rectPosY[i], 20, 20);
  }
  
  // 中心点を移動して45度回転
  for(int i = 0; i<NUM; i++){
    pushMatrix();
        translate(rectPosX[i],rectPosY[i]);
        rotate(radians(frameCount));
        fill(hue[i],100,100,100);
        rect(0, 0, 20, 20);
    popMatrix();
  }
   
}


```


<img src="https://github.com/55Kaerukun/Processing/blob/master/images/konpeito.png" width="500px">
