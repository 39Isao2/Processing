# 関数

「色を青にして、丸を描く」など、処理をひとまとめにして呼び出す機能<br>
setup、drawの外で定義する。<br>

```
// 記述の仕方。（戻り値のない場合）
void 関数名(){
  処理内容〜
}

```

<img src="https://github.com/55Kaerukun/Processing/blob/master/images/function.png" width="500px">

```

// 例 青い丸を描く関数

void setup(){
  setHS
}

void draw(){
  
  // 透明な四角を上から塗りつぶす
  fill(0,0,0,10);
  rect(0, 0, width, height);

  // 円の描画
  fill(0,0,255);
  ellipse(posX, height/2, 100, 100);
  
  // 座標の更新
  posX = posX+3;
  
  // 一番左に戻す
  if(posX > width){
    posX = 0;
  }
}

```

