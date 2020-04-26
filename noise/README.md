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

float step;

void setup(){
  
    step = 0;
    size(400, 400);
    background(255);
  
    for (int x = 0; x < width; x += 3) {
   
      //noise()の引数がいくつでも、必ず結果は0.0 ~ 1.0の間の値が返される
      //0.0 ~ 1.0にheightを掛けているので、結果は0.0 ~ 400.0
      float y = noise(step) * height;  //ノイズを使ってy座標を設定
     
      line(x, 0, x, y);
      //ランダムを使った場合は連続性がない
      //line(x, 0, x, random(height));
      step += 0.1;   //ノイズの値を更新
    }
    
}

```

ランダムだとこうなる<br>
<img src="https://github.com/55Kaerukun/Processing/blob/master/images/random.png" width="800px">
