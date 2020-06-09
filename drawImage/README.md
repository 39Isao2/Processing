# 画像の表示方法
jpg、png、gif、svg 形式に対応している。  
Processingで画像を表示するためには、  
pdeファイルと同階層に「data」フォルダを作成し、その中に画像ファイルを入れる  
<img src="https://github.com/55Kaerukun/Processing/blob/master/images/fd.png">


サンプルコード  

```

// PImage型の変数を定義 
PImage hiyokoImage;

void setup(){
  size(500,500);
  background(255);
  // 変数hiyoko に画像データを読み込む
  hiyokoImage = loadImage("hiyoko.jpg");
}

void draw(){
  // 変数名、x座標、y座標
  image(hiyokoImage, 100, 100);
}

// web上の画像も読み込めます
// hiyoko = loadImage("https:xxxxxxxxxxxxxxx.png");


```

<img src="https://github.com/55Kaerukun/Processing/blob/master/images/drawImage.png">


