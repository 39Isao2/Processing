発光効果、グロウ(glow)効果。
電球や星、ホタルなど、それ自体が光っているような効果を出す。


blendMode(SCREEN) を使う。
blendMode(ADD)は色が重なって白くなってします。

blendMode(SCREEN) を入れると、
その後に描画される図形は重なった部分の色が足されます。

/*
blendMode() を何も指定しない場合は blendMode(BLEND) 
モードとなり、図形は単に上書きされてしまいます。
*/




じゃあ、そもそも「ぼんやり光る」ってどんな感じかというと、
ということは、中心部分に明るいものを描いて、
その周りにちょっとずつ暗いものを描く。

描画を重ねるということと合わせると、
明るい小さいのを描いて、
ちょっと暗い大きいのをその上に重ねて描く。



/*
1.明るい細い線の円を描く
2.ちょっと暗く、ちょっと太くした円を同じ場所に描く
3.もうちょっと暗く、もうちょっと太くした円を同じ場所に描く
4.これを繰り返し、よきところで止める。
で良さそうですね。
*/



# 発光step1 

<img src="https://github.com/55Kaerukun/Processing/blob/master/emission/images/img1.png" width="300px">

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
  
  // R B G アルファ  
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


# step2 

<img src="https://github.com/55Kaerukun/Processing/blob/master/emission/images/img2.png" width="300px">

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

 for (int i = 1; i < 25; ++i) {
   strokeWeight(i * 2); // 0*25 1*25 2*25 とだんだん太さを足しいる
   stroke(100, 100, 25 - i, 100); // 25-0 25-1 25-2 とだんだん色を薄くしてグラデーションを表現
   ellipse(0, 0, radius, radius);
 }

}


```

# step3

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

 for (int i = 1; i < 50; ++i) {
   strokeWeight(i);
   //stroke( map(i, 1, 50, 180, 360) , 80 , map(i, 1, 50, 15, 1),100);
   
   // 緑バージョン
   //stroke(map(i, 1, 50, 90, 180), 100 , map(i, 1, 50, 30, 1), 100);
   ellipse(0, 0, radius,radius);
 }

}

```
