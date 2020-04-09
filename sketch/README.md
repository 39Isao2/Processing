# 基本的なスケッチ

## 図形の描画
<br>

### キャンバスサイズの設定

size(横幅,縦幅);
```
size(500,500);
```

### 四角形
rect(x,y,横幅,縦幅);
```
rect(100,100,100,50);
```

### 楕円
ellipse(x,y,楕円の幅,高さ);
```
ellipse(300,300,100,100);
```

### 罫線
line(左上のX座標,左上のY座標,右上のY座標,右下のY座標);
```
line(40,40,400,500);
```
<br>

## 色や線幅の設定

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
中心のx座標、中心のy座標、円の幅、円の高さ、開始の角度(ラジアン)、終了の角度(ラジアン)
```
arc(250,300, 300, 200, radians(0), radians(180));
```


<img src="https://github.com/55Kaerukun/Processing/blob/master/images/sample.png" width="500px">

### 複雑な形 : beginShape, endShape, vertex
https://htsuda.net/archives/1266
