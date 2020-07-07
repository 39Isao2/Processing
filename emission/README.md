# 発光の表現

<img src="https://github.com/55Kaerukun/Processing/blob/master/emission/images/particle.png" width="300px">



```

// この方法はすごい手っ取り早いが重いのでアニメーションには不向き

void setup(){
  size(500,500);
  blendMode(BLEND);
  noStroke();
}

void draw(){
  background(0);
  translate(width/2,height/2);
  
  fill(0,0,255);
  ellipse(0,0,80,80);
  
  fill(230,230,230);
  ellipse(0,0,40,40);
  
  fill(255);
  ellipse(0,0,20,20);
  
  filter(BLUR, 10);
  
  fill(255);
  ellipse(0,0,18,18);
  
  
}

```

参考:filterについて  
https://qiita.com/umi_mori/items/5b5d0123e2ea533d49eb
<br>
<br>


## まずはblendMode()の種類を3つ把握  （初期値、ADD、SCREEN）

参考リンク<br>
ProcessingのblendMode()の使い方<br>
http://aa-deb.hatenablog.com/entry/2016/11/03/181953 <br><br>
ぼんやり光る効果を出す簡単な方法 その2 : Processing Tips <br>
https://note.com/deconbatch/n/nadd699e04580 <br><br>

加算とスクリーンを正しく使い分けて綺麗な光を描くヒント(photoshop) ← グラフの曲線見るのオススメ！！<br>
http://compojigoku.blog.fc2.com/blog-entry-7.html







## ぼんやり光る表現方法
中心部分に明るいものを描いて、<br>
その周りにちょっとずつ暗いものを描く。<br>


<img src="https://github.com/55Kaerukun/Processing/blob/master/emission/images/img1.png" width="300px"><br>

<img src="https://github.com/55Kaerukun/Processing/blob/master/emission/images/ring.png" width="300px">


## 発光step1 

```

int radius;

void setup(){
  size(600,600);
  radius = 200;
  //blendMode(BLEND);  // (初期値)
  blendMode(SCREEN);
  noFill();
  colorMode(HSB,360,100,100,100);
}

void draw(){
  background(0);
  translate(width/2, height/2);
  
  strokeWeight(10);
  stroke(100, 100, 100, 100);  // 緑
  ellipse(0, 0, radius, radius);
  
  strokeWeight(25); // 線を太くする
  stroke(100, 100,  50, 100); // 薄い緑
  ellipse(0, 0, radius, radius);
  
  strokeWeight(50); // 線をもっと太くする
  stroke(100, 100,  20, 100); // もっと薄い緑
  ellipse(0, 0, radius, radius);
}

```


## step2 

<img src="https://github.com/55Kaerukun/Processing/blob/master/emission/images/img2.png" width="300px">
<br>
<img src="https://github.com/55Kaerukun/Processing/blob/master/emission/images/ring2.png" width="300px">

```

int radius;

void setup(){
  size(600,600);
  radius = 200;
  //blendMode(BLEND);  // (初期値)
  blendMode(SCREEN);
  noFill();
  colorMode(HSB,360,100,100,100);
}

void draw(){

background(0);
translate(width/2, height/2);

 for (int i = 0; i < 25; ++i) {
   strokeWeight(i * 2); // 0*2 1*2 3*2 とだんだん太さを足しいる
   stroke(100, 100, 25 - i, 100); // 25-0 25-1 25-2 とだんだん色を薄くしてグラデーションを表現
   ellipse(0, 0, radius, radius);
 }

}


```

## step3

<img src="https://github.com/55Kaerukun/Processing/blob/master/emission/images/img3.png" width="300px">


```

int radius;

void setup(){
  size(600,600);
  radius = 200;
  //blendMode(BLEND);  // (初期値)
  blendMode(SCREEN);
  noFill();
  colorMode(HSB,360,100,100,100);
}

void draw(){

background(0);
translate(width/2, height/2);

 for (int i = 1; i < 50; i++) {
   strokeWeight(i);
   stroke( map(i, 1, 50, 180, 360) , 100 , map(i, 1, 50, 15, 1),100);
   
   // 緑バージョン
   //stroke(map(i, 1, 50, 90, 120), 100 , map(i, 1, 50, 15, 1), 100);
   ellipse(0, 0, radius,radius);
 }

}

```

色相環（hue circle） : https://www.petitmonte.com/javascript/color_wheel.html
