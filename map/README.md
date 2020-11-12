# map関数

### 値の調整に使う。Arduionoなどのデバイスでもよく使用する。

```
// map(num, a, b, c, d) numを範囲a-bから別の範囲c-dへ変換する（マッピング）


float num;

void setup(){
  
  num = 2.0;
  
  // numを範囲0-10から別の範囲0-100へ変換する
  float value = map(num, 0, 10, 0, 100);
  
  // valueは 20
  println(value);
  
}

```


## サンプルコード

```
float diameter;

void setup(){
  size(500,500);
  noStroke();
  diameter = 0;
}

void draw(){
  background(255);
  
  // mouseXの値を変数posXに
  float posX = mouseX;
  
  // 値の調整 本来０〜500のところを0~100に変換！
  diameter = map(posX, 0, 500, 0, 100);
  //println(diameter);
  
  
    // 緑色
  fill(0,255,0);
  ellipse(width/2, height/2, diameter, diameter);
}

```


## mouseXをhueにマッピングする
```

void setup(){
  size(500,500);
  noStroke();
  colorMode(HSB,360,100,100,100);
}

void draw(){
  
  // 白で塗り潰し
  background(100,0,100,100);
  
  float hue = map(mouseX, 0, width, 0, 360);
  
  // 色をマウス座標で変更
  fill(hue,100,100,100);
  
  ellipse(width/2, height/2, 200, 200);
}

```

<img src="https://github.com/55Kaerukun/Processing/blob/master/images/map.png" width="700px">


# Arduionoでの使用例。
```
Arduionoでの使用例。（0 ~ 1023で返ってくる）

// 例えばrgbで使いたかったら (0,0,255);
float r = map(r,0,1023,0,255);

// 例えば360で使いたかったら (360,100,100,100);
float h = map(h,0,1023,0,360);

// その他半径に使ったり、大きすぎたり、小さすぎたりする値の調節によく使用する
```

