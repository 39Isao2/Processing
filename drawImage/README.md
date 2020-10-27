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
image(hiyokoImage, 100, 100, width/2, height/2)); <br>
```

透明度を変更
```
// 位置とサイズを指定して画像を表示
tint(255,255,255,100);
```


参考サイト <br>
https://yoppa.org/proga10/1353.html

# 音の使い方

processingメニュー＞スケッチ＞ライブラリーを追加＞soundで検索  
出てきたら、soundを選択＞インストール。  
<br>
<img src="https://github.com/55Kaerukun/Processing/blob/master/images/sound.png" width="500px">
<br>

画像のようにpdeファイルと同階層に「data」フォルダを作成し、  
その中に音ファイルを入れる(mp3、wav形式などが使用可能)  
<br>
サンプルコード  
```

// 音ライブラリを使う宣言
import processing.sound.*;

// SoundFile型変数を定義
SoundFile music;

void setup(){
  // 音データ読み込み
  music = new SoundFile(this,"soudfile.mp3");
}

void draw(){
 //注意！drawの中でplay()させると基本的には再生され続けてします。（1秒間に60回play()が発動してるから）
  
}

void mousePressed(){
  // マウスを押すと音が鳴る
  music.play();
}


```
