# 基本的なスケッチ

## 図形の描画
<br>

<img src="https://github.com/55Kaerukun/Processing/blob/master/images/sketch1.png" width="300px">

### キャンバスサイズの設定

size(横幅,縦幅);
```
size(500,500);
```

<img src="https://github.com/55Kaerukun/Processing/blob/master/images/size.jpg" width="500px">
<br>


### 四角形
rect(x,y,横幅,縦幅);
```
rect(100,100,200,200);
```
<img src="https://github.com/55Kaerukun/Processing/blob/master/images/rect.jpg" width="500px">
<br>

### 楕円
ellipse(x,y,楕円の幅,高さ);
```
ellipse(200,200,100,100);
```
<img src="https://github.com/55Kaerukun/Processing/blob/master/images/ellipse.jpg" width="500px">
<br>

### 罫線
line(左上のX座標,左上のY座標,右上のY座標,右下のY座標);
```
line(40,40,400,500);
```
<br>

## 色や線幅の設定

### 背景色の設置

background(r,g,b); // 赤、緑、青(255がmax)
```
background(255,255,255);
```

### 塗り潰し
fill(r,g,b); // 赤、緑、青(255がmax)
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
arc(250,250, 300, 200, radians(0), radians(180), PIE);
```

<!-- <img src="https://github.com/55Kaerukun/Processing/blob/master/images/arc.jpg" width="700px"> -->
<br>






### レッツお絵かき
<br>
チャレンジ1  (face.txt)
<br>
<img src="https://github.com/55Kaerukun/Processing/blob/master/images/face.png" width="500px">
<br>
チャレンジ2  (frog.txt)
<br>
<img src="https://github.com/55Kaerukun/Processing/blob/master/images/sample.png" width="500px">
<br>
カエルの色 fill(204,255,102);

### 複雑な形 : beginShape, endShape, vertex
https://htsuda.net/archives/1266

### ベジェ曲線
https://cc.musabi.ac.jp/kenkyu/cf/renew/program/processing/processing06.html
