# ノイズ

参考
https://qiita.com/takumi_tamacov/items/9d42d346dbf9d65745ba <br>
processingにはrandom()関数と似たようなnoise()という関数がある。<br>
noise関数は「パーリンノイズ」というアルゴリズムを利用している。<br>

<img src="https://github.com/55Kaerukun/Processing/blob/master/images/noise.png" width="800px">

<br>
パーリンノイズの例<br>
http://zellij.hatenablog.com/entry/20130507/p1
<br>


```
// 引数がいくつでも、必ず結果は0.0 ~ 1.0の間の値が返される
// 引数には変化する値入れる。
noise();
```


```

float step;
float y;

void setup(){
  
    size(400, 400);
    step = 0;
    background(255);
  
    for (int i = 0; i < width; i += 3) {
      
      
      // ランダムを使った場合は連続性がない  
      // y = random(height);
      
      //noise()の引数がいくつでも、必ず結果は0.0 ~ 1.0の間の値が返される
      //0.0 ~ 1.0にheightを掛けているので、結果は0.0 ~ 400.0
      y = noise(step) * height;  //ノイズを使ってy座標を設定
      

      line(i, 0, i, y);
      
      step += 0.1;   //ノイズの値を更新
    }
    
}

```

ランダムだとこうなる<br>
<img src="https://github.com/55Kaerukun/Processing/blob/master/images/random.png" width="800px">




## ノイズウォーカー

<img src="https://github.com/55Kaerukun/Processing/blob/master/images/randomwork.png" width="500px">

```

float stepX;
float stepY;
 
void setup(){
  size(500, 500);
  
  background(255);
  
  stepX = random(100);
  stepY = random(100);
}
 
void draw(){
  
  //for(int i =0; i<10; i++){
  
    float x = noise(stepX) * width;
    float y = noise(stepY) * height;
    
    //float x = random(width);
    //float y = random(height);
    
    stroke(0,0,0);
    point(x, y);
    
    stepX += 0.01;
    stepY += 0.01;
  //}
  
}

```

