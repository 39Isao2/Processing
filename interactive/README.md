# インタラクティブとアニメーション

## setupとdrawについて
<br>
processingでは、最初の一回だけ実行したい処理をsetup()内に、常時繰り返し実行したい処理をdraw()内に記述します。<br>
（サイズや背景設定などはsetup()内に、描画部分はdraw()に記述するのが流儀）<br><br>
<strong style="color:red;">drawは1秒間に60回実行されます。</strong>
<br><br>


### mouseを使った例
<br>
<img src="https://github.com/55Kaerukun/Processing/blob/master/images/intaraction_sample.png" width="800px">
<br>


### マウスの座標取得
mouseX (現在のマウスのx座標)<br>
mouseY (現在のマウスのY座標)<br>
```
// 例
ellipse(mouseX,mouseY,100, 100);
```

### 乱数の生成
random(255); 0以上、255未満の数
random(30,100); 20以上、100未満の数
```
// 例
fill(random(255),random(255),random(255));
```


<br>
<br>

# 変数
変数とは値をいれる箱のこと。C言語やJavaScript、ほぼ全てのプログラム言語で利用する重要概念。<br>
processing初級では、主に数字や真偽地(true, false)を入れたりするのに利用する。<br>

### 型 名前 = 値; 
使用例: int radius = 100;<br>
ellipse(250,250,radius,radius);<br>
radius = 200;<br>
のように、何度も上書きできる。<br>
<br>
<img src="https://github.com/55Kaerukun/Processing/blob/master/images/sample2.png" width="800px">
<br>
<br>
### 型の種類
<br>
型 | 内容
--- | ---
int | 整数
float | 少数
boolean | 真偽値
String | 文字列
PImage | 画像


# アニメーション
<br>
<br>
変数を使って、座標を少しずつ移動させてアニメーションを実現させる<br>

```
// 現在のposXの値に1ずつプラスする
posX = posX + 1;
```



```
float posX = 250;

void setup(){
  size(500,500);
}

void draw(){
  // 白で再度塗りつぶす
  background(255,255,255);
  fill(0,0,255);
  
  ellipse(posX,250,50,50);
  
  // x座標の更新
  posX = posX+1;
}
```


### 背景色の設置
background(r,g,b);
```
background(255,255,255);
```

### 塗り潰し
fill(r,g,b); // 赤、青、緑(255がmax)
```
fill(255,0,0);
```

### 線幅の変更
strokeWeight(線幅);
```
strokeWeight(3);
```

### 線を無くす
noStroke(); // カッコの中は何もなし
```
noStroke();
```

### 円弧
中心のx座標、中心のy座標、円の幅、円の高さ、開始の角度(ラジアン)、終了の角度(ラジアン)、PIE
```
arc(250,300, 300, 200, radians(0), radians(180), PIE);
```

### レッツお絵かき
<br>
<img src="https://github.com/55Kaerukun/Processing/blob/master/images/sample.png" width="500px">
<br>

### 複雑な形 : beginShape, endShape, vertex
https://htsuda.net/archives/1266
