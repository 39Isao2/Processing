
# シーンの切り替え （keyPressed)

キーボードの入力と関数を利用して、シーンを切り替える<br>

```

// シーンを管理する変数
int scene;

void setup( ) {
    size(600,600);
    colorMode(HSB,360,100,100,100);
    background(100,0,100);

    // 四角形の描画起点を真ん中に
    rectMode(CENTER);
    strokeWeight(3);
    
    // 最初のシーン
    scene = 1;
}


void draw() {
  
    background(100,0,100);
    
    if(scene == 1){
      // 丸を描画
      fill(90,100,100,100);
      ellipse(width/2,height/2,200,200);
    } else if(scene == 2){
      // 四角を描画
      fill(0,100,100,100);
      rect(width/2,height/2,200,200);
    } else if(scene == 3){
      // 線を描画
      line(0,0,width,height);
      line(width,0,0,height);
    }
    
}


void keyPressed(){
  
    if(key == 'a'){
    // aを押したら      
      scene = 1; // シーンを1に変更  
    } else if(key == 's'){
    // sを押したら
      scene = 2; // シーンを2に変更
    } else if(key == 'd'){
    // dを押したら
      scene = 3; // シーンを3に変更
    }
}

```


## シーン切り替えのタイミングで音を鳴らす


```
import ddf.minim.*;
import ddf.minim.analysis.*;
import ddf.minim.effects.*;
import ddf.minim.signals.*;
import ddf.minim.spi.*;
import ddf.minim.ugens.*;

// minim使用する状態を設定
Minim minim = new Minim(this);

// //サウンドデータ格納用の変数
AudioPlayer se1;
AudioPlayer se2;
AudioPlayer se3;

// シーン管理の変数
int scene;


void setup( ) {
    size(600,600);
    colorMode(HSB,360,100,100,100);
    background(100,0,100);

    // 四角形の描画起点を真ん中に
    rectMode(CENTER);
    strokeWeight(3);
    
    // 最初のシーン
    scene = 0;
    
    // 音楽データの読み込み
    se1 = minim.loadFile("se5.mp3");
    se2 = minim.loadFile("se6.mp3");
    se3 = minim.loadFile("se7.mp3");
}

void draw() {
  
    background(100,0,100);
    
    if(scene == 1){
      // 丸を描画
      fill(90,100,100,100);
      ellipse(width/2,height/2,200,200);
    } else if(scene == 2){
      // 四角を描画
      fill(0,100,100,100);
      rect(width/2,height/2,200,200);
    } else if(scene == 3){
      // 線を描画
      line(0,0,width,height);
      line(width,0,0,height);
    }
    
}


void keyPressed(){
  
    if(key == 'a'){
    // aを押したら      
      scene = 1; // シーンを1に変更  
      se1.play();
      se1.rewind();
    } else if(key == 's'){
    // sを押したら
      scene = 2; // シーンを2に変更
      se2.play();
      se2.rewind();
    } else if(key == 'd'){
    // dを押したら
      scene = 3; // シーンを3に変更
      se3.play();
      se3.rewind();
    }
}
```

