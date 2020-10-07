# Processingとは？

[https://www.processing.org/](https://www.processing.org/)

![processing_logo](https://github.com/55Kaerukun/Processing/blob/master/images/download.png)


2001年にCasey Reas（ケーシー・リース）と Ben Fry（ベン・フライ）の2人が開発。<br>
プログラミング・アート作成や教育用プログラミング環境として使用されている。<br>
学生、アーティスト、デザイナーが扱いやすいように配慮されている
ブラウザで動くJavaScript版P5.jsも広く普及。<br>
　


- 言語：JAVA(Processing用に簡単になってる)
- 開発環境：Processing IDE

<br>
<img src="https://github.com/55Kaerukun/Processing/blob/master/images/processing_ide.png" width="700px">
<br>

### 事例紹介

#### Flight Patterns
Aaron Koblin <br>
http://www.aaronkoblin.com/

http://www.aaronkoblin.com/project/flight-patterns/

[![Flight Patterns](http://img.youtube.com/vi/ystkKXzt9Wk/0.jpg)](http://www.youtube.com/watch?v=ystkKXzt9Wk)



## まずは色々な図形を覚えて絵を描けるようになりましょう。
<br>
<img src="https://github.com/55Kaerukun/Processing/blob/master/images/drra.png" width="700px">
<br>


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

<img src="https://github.com/55Kaerukun/Processing2/blob/master/images/colors.png" width="has 600px">

### 線幅の変更
strokeWeight(線幅);
```
strokeWeight(10);
```

### 線を無くす
noStroke(); // カッコの中は何もなし
```
noStroke();
```

### 円弧
中心のx座標、中心のy座標、円の幅、円の高さ、開始の角度(ラジアン)、終了の角度(ラジアン)、PIE
```
arc(250,250, 300, 100, radians(0), radians(180), PIE);
```

<img src="https://github.com/55Kaerukun/Processing/blob/master/images/arc.jpg" width="700px"> 
<br>






### レッツお絵かき
<br>
チャレンジ1 ニコちゃん？描いてみましょう！
<br>
<img src="https://github.com/55Kaerukun/Processing/blob/master/images/yellowface.pmg" width="500px">


<br>
チャレンジ2 カエルを描いてみよう！
<br>
<img src="https://github.com/55Kaerukun/Processing/blob/master/images/sample.png" width="500px">
<br>
ヒント: カエルの色 fill(204,255,102); <br>
答えはこちら！<br>
https://gist.github.com/55Kaerukun/edeb00bc9c9d0a1ab6d65b6c48bbf549


## 参考

### 複雑な形 : beginShape, endShape, vertex
https://htsuda.net/archives/1266


```

// 背景白色に
background(255);

// 黄色
fill(0,255,255);

// ひし形
beginShape();
  vertex(30, 100);
  vertex(200, 100);
  vertex(270, 200);
  vertex(100, 200);
endShape(CLOSE);

```

### ベジェ曲線
https://cc.musabi.ac.jp/kenkyu/cf/renew/program/processing/processing06.html
