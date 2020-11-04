# 画像の表示方法
jpg、png、gif、svg 形式に対応している。  
Processingで画像を表示するためには、  
pdeファイルと同階層に「data」フォルダを作成し、その中に画像ファイルを入れる  
<br>
<img src="https://github.com/55Kaerukun/Processing/blob/master/images/fd.png" width="500px">
<br>

サンプルコード  

```

// PImage型の変数を定義 
PImage hiyokoImage;

void setup(){
  size(500,500);
  background(255);
  // 変数hiyoko に画像データを読み込む
  hiyokoImage = loadImage("hiyoko.png");
}

void draw(){
  // 変数名、x座標、y座標
  image(hiyokoImage, 100, 100);
}

// web上の画像も読み込めます
// hiyoko = loadImage("https:xxxxxxxxxxxxxxx.png");


```
<br>
<img src="https://github.com/55Kaerukun/Processing/blob/master/images/drawImage.png" width="">
<br>

画像を表示 <br>
```
// 変数名、x座標、y座標 
image(hiyokoImage, 100, 100); 
```

```
// 位置とサイズを指定して画像を表示
image(hiyokoImage, 100, 100, width/2, height/2);

```


## ピクセレイト

<br>
<img src="https://github.com/55Kaerukun/Processing/blob/master/images/pixcelate.png" width="800px">
<br>



```
PImage img;

void setup(){
  size(750,1053);
  img = loadImage("image.jpg");
  background(0);
  noStroke();
}

void draw(){
  
  for(int i = 0; i<10; i++){
    // 色を取得する位置をランダムに決定
    int x = (int)random(width);
    int y = (int)random(height);
    
    // 指定した場所の色を取得
    color col = img.get(x,y);
    fill(col,127);
    
    //色の明度を求めるには、brightness(色)
    float size = brightness(col) /8.0;
    
    ellipse(x,y,size,size);
  }
}

void mousePressed() {
    noLoop();  // ボタンを押すと停止
}

void keyPressed(){
    loop();   // 再度draw()が始まる
}

```



参考サイト <br>
https://yoppa.org/proga10/1353.html



## color型について
指定した場所の色を取得するには、で可能だが、それぞれのrgbの値の確認が少し面倒。
```
// ↑上のソースだと

color col = img.get(x,y);
float r = red(col);
float g = green(col);
float b = blue(col);
println(r);

```



# 音の使い方

processingメニュー＞スケッチ＞ライブラリーを追加＞Minimで検索  
出てきたら、Minimを選択＞インストール。  
<br>
<img src="https://github.com/55Kaerukun/Processing/blob/master/images/sound2.png" width="500px">
<br>

画像のようにpdeファイルと同階層に「data」フォルダを作成し、  
その中に音ファイルを入れる(mp3、wav形式などが使用可能)  
<br>
サンプルコード  
```

// スケッチ→ライブラリをインポート → minimを選択すると自動で書かれる

import ddf.minim.*;
import ddf.minim.analysis.*;
import ddf.minim.effects.*;
import ddf.minim.signals.*;
import ddf.minim.spi.*;
import ddf.minim.ugens.*;

// minim使用する状態を設定
Minim minim = new Minim(this);

// //サウンドデータ格納用の変数
AudioPlayer bgm;
AudioPlayer se1;
AudioPlayer se2;

void setup(){
  size(500, 500);
  // 音楽データの読み込み
  bgm = minim.loadFile("bgm.mp3");
  se1 = minim.loadFile("se1.mp3");
  se2 = minim.loadFile("se2.mp3");
}

void draw(){
  // 自動再生
  bgm.play();
}

// キーを押された時
void keyPressed(){
  if(key=='a'){
    se1.play();
    se1.rewind();  //再生が終わったら巻き戻しておく
  }
  
  if(key=='s'){
    se2.play();
    se2.rewind();
  }
}

```
