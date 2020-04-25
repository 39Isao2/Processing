# 関数

処理をひとまとめにして呼び出す機能<br>
setup、drawの外で定義する。<br>

```
// 記述の仕方。（戻り値のない場合）
void 関数名(){
  処理内容〜
}

<br>

```

<img src="https://github.com/55Kaerukun/Processing/blob/master/images/function.png" width="800px">

```
void setup(){
  size(500,500);
  // カラーモードをHSBに（癖にしましょう）
  colorMode( HSB, 360, 100, 100,100);
  // 色(暗記しましょう)
  background(100,0,100);
}

void draw(){
  // 関数の呼び出し
  drawBlueCircle();
}

// 関数の定義
void drawBlueCircle(){
  fill(240,100,100);
  ellipse(width/2,height/2,100,100);
}

```

<br>

