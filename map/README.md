# map関数

### 値の調整に使う。Arduionoなどのデバイスでもよく使用する。

```
map(num, a, b, c, d) numを範囲a-bから別の範囲c-dへ変換する

float num = 2.0;

// numを範囲0-10から別の範囲0-100へ変換する
float value = ofMap(num, 0, 10, 0, 100)

// value は 20

```

<img src="https://github.com/55Kaerukun/Processing/blob/master/images/map.png" width="400px">


## サンプルコード

```
void setup(){
  size(1000,1000);
  noStroke();
  colorMode(HSB,360,100,100,100);
}

void draw(){
  background(0,0,100);
  
  float hue = map(mouseY, 0, height, 0, 360);
  fill(hue,100,100);
  
  float r = map(mouseX, 0, width, 0 ,600);
  //ellipse(width/2,height/2,mouseX,mouseX);
  ellipse(width/2,height/2,r,r);
}

```

```
Arduionoでの使用例。（0 ~ 1023で返ってくる）
float val = 0;
float mapVal = map(val,0,1023,0,255);
```

