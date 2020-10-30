# 関数の作り方

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

# 関数を使ってコードを綺麗に書く

<br>
<img src="https://github.com/55Kaerukun/Processing/blob/master/images/face.png" width="300px">
<br>

このコードを関数を使ってわかりやすいプログラムにしてみよう！

```
void setup(){
  size(500,500);
  background(255);
}

void draw(){

  // 顔
  fill(204,255,102);
  rect(50,50,400,400);

  // 目
  fill(0);
  ellipse(250-100,150,50,50);
  ellipse(250+100,150,50,50);

  // 鼻
  rect(250,220,30,30);


  //　口
  fill(255,0,0);
  arc(250,300, 250, 250, radians(0), radians(180), PIE);
}

```



# 引数とreturnについて

今までの関数はvoid（戻り値がない）もののみでしたが、
引数やreturnを使うと、関数の中で値の変換や返却ができます。  
<br>

```

float banana;

void setup(){
  // バナナの値段
  banana = 150;
}

void draw(){
  float price = calc(banana);
}

// 今まではvoid だったけど返却する(returnする型)を書く
float calc(float banana){
  banana = banana * 1.10;
  return banana;
}


```
