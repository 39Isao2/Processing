# 関数

処理をひとまとめにして呼び出す機能<br>
setup、drawの外で定義する。<br>

```
// 記述の仕方。（戻り値のない場合）
void 関数名(){
  処理内容〜
}

```

<!--<img src="https://github.com/55Kaerukun/Processing/blob/master/images/function.png" width="800px">-->

### 例:青い丸を描く関数 drawBlueCircle()
```
void setup(){
  size(500,500);
  background(255);
}

void draw(){

  // 関数の呼び出し
  drawBlueCircle();
  
}

// 関数の定義
void drawBlueCircle(){
  fill(0,0,255);
  ellipse(width/2,height/2,100,100);
}

```

<br>

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

void draw( ) {
    background(100,0,100);
    
    if(scene == 1){
      // 丸を描画
      ellipse(width/2,height/2,200,200);
    } else if(scene == 2){
      // 四角を描画
      rect(width/2,height/2,200,200);
    } else if(scene == 3){
      // 線を描画
      line(0,0,width,height);
      line(width,0,0,height);
    }
    
}


void keyPressed(){
  
    // ランダムに色変更
    fill(random(100),100,100);
  
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
