# インタラクティブとアニメーション

## setupとdraw
<br>
processingでは、最初の一回だけ実行したい処理をsetup()内に、常時繰り返し実行したい処理をdraw()内に記述します。<br>
（サイズや背景設定などはsetup()内に、描画部分はdraw()に記述するのが流儀）<br>
<strong style="color:red;">drawは1秒間に60回実行されます。</strong>
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
