# map関数

### 値の調整に使う。Arduionoなどのデバイスでもよく使用する。

```
// map(num, a, b, c, d) numを範囲a-bから別の範囲c-dへ変換する


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


<img src="https://github.com/55Kaerukun/Processing/blob/master/images/map.png" width="700px">


# Arduionoでの使用例。
```
Arduionoでの使用例。（0 ~ 1023で返ってくる）
float val = 0;
float mapVal = map(val,0,1023,0,255);
```

