# イージング
だんだんと目的地に近づいていくアニメーションの効果。<br>
公式を覚えて使おう。<br>

### 現在地 = 現在地 + 目的地までの差分 * イージング係数 （公式）

<br>
サンプルコード
<br>

```

// 円のx座標
float x;

// 目的地のx座標
float targetX;

// イージング係数
float easing;


void setup(){
  size(500, 500);
  background(0);
  
  // 円の座標初期値
  x = 0;
  
  // 目的地初期値
  targetX = 400;
  
  // イージング係数
  easing = 0.05;
}

void draw(){
  background(0);
  
  // 現在の位置と目的地の距離を計測
  float distanceX = targetX - x;
  
  //現在地 = 現在地 + 目的地までの差分 * イージング係数 （公式）
  x = x + distanceX * easing;

  //　塗りと円の描画
  fill(255,0,0);
  ellipse(x, height/2 ,40,40);
}


```

<br>
イージングの公式（簡略版） https://qiita.com/39_isao/items/67cf63a6f802ac2f2a9b
<br>

