
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
// 音ライブラリを使う宣言
import processing.sound.*;

// シーンを管理する変数
int scene;

// SoundFile型変数を定義
SoundFile music1;
SoundFile music2;
SoundFile music3;

void setup( ) {
    size(600,600);
    colorMode(HSB,360,100,100,100);
    background(100,0,100);

    // 四角形の描画起点を真ん中に
    rectMode(CENTER);
    strokeWeight(3);
    
    // 最初のシーン
    scene = 1;
    
    // 音読み込み
    music1 = new SoundFile(this,"soudfile1.mp3");
    music2 = new SoundFile(this,"soudfile2.mp3");
    music3 = new SoundFile(this,"soudfile3.mp3");
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
      music1.play();
    } else if(key == 's'){
    // sを押したら
      scene = 2; // シーンを2に変更
      music2.play();
    } else if(key == 'd'){
    // dを押したら
      scene = 3; // シーンを3に変更
      music3.play();
    }
}
```

