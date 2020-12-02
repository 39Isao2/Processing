

# Z軸を使った、3次元のプログラミング基礎

## boxの表示

```
void setup() {
  size(500, 500, P3D);
}
 
void draw() {
  background(0);
  stroke(255);
  noFill();
  translate(width/2,height/2);
  
  rotateX(radians(mouseX));
  rotateY(radians(mouseY));
  box(100, 100, 100); //100x100x100pxの立方体を描画
  
  
  // Box2
  pushMatrix();
      translate(100, 100, 0);
      box(40, 10, 50);   //box(横幅, 縦幅, 奥行き);
  popMatrix();
}
```

<img src="https://github.com/55Kaerukun/Processing/blob/master/images/3dbox.png" width="400px"> 

## sphereの表示

```

float theta;

void setup() {
  size(500, 500, P3D);
  theta = 0;
}
 
void draw() {
  background(0);
  stroke(0,0,255);
  noFill();
  translate(width/2,height/2);
  
  theta = theta+0.5;
  rotateY(radians(theta));
  sphere(150); 
  
  if(theta > 360){
    theta = 0;
  }
}

```

<img src="https://github.com/55Kaerukun/Processing/blob/master/images/sphere2.png" width="400px"> 

## z軸を使用したパーティクル

```

int NUM = 100;
float[] x = new float[NUM]; //100個保存できる棚（配列）
float[] y = new float[NUM];
float[] z = new float[NUM];

void setup(){
  size(1000,1000,P3D);
  
  ////0から100まで1ずつ増えるループ
  for(int i=0; i<NUM; i++){
    x[i] = random(width);
    y[i] = random(height);
    z[i] = random(-1000,0); //-1が奥、+が手前
  } 
  
}


void draw(){
  background(0);
  stroke(255,255,0); //線の色
  strokeWeight(2);
  
  for(int i=0; i<NUM; i++){
    
    // 点
    point(x[i], y[i],z[i]);
    
    z[i] = z[i] + 20; //20ずつ手前に移動
    
    
    //z座標が100以上になったらランダムで再配置
    if(z[i] > 100){
      x[i] = random(width);
      y[i] = random(height);
      z[i] = -1000; 
    }  
  }
}

```

<img src="https://github.com/55Kaerukun/Processing/blob/master/images/p1.png" width="600px"> 

## カラフルver

```
int NUM = 100;
float[] x = new float[NUM]; //100個保存できる棚（配列）
float[] y = new float[NUM];
float[] z = new float[NUM];
float[] col = new float[NUM];

void setup(){
  size(1000,1000,P3D);
  colorMode(HSB,360,100,100,100);
  
  ////0から100まで1ずつ増えるループ
  for(int i=0; i<NUM; i++){
    x[i] = random(width);
    y[i] = random(height);
    z[i] = random(-1000,0); //-1が奥、+が手前
    col[i] = random(360);
  } 
  
}


void draw(){
  background(0);
  strokeWeight(4);
  
  for(int i=0; i<NUM; i++){
    
    stroke(col[i],100,100,100); //線の色
      
    // 点
    point(x[i], y[i],z[i]);
    
    
    //// パーティクルの粒
    /*
    strokeWeight(20);
    stroke(col[i],100,20,100); 
    point(x[i], y[i],z[i]);
    
    strokeWeight(8);
    stroke(col[i],100,60,100); 
    point(x[i], y[i],z[i]);
    
    strokeWeight(4);
    stroke(col[i],100,80,100); 
    point(x[i], y[i],z[i]);
    */
    
    
    
    z[i] = z[i] + 20; //20ずつ手前に移動
    
    
    //z座標が100以上になったらランダムで再配置
    if(z[i] > 100){
      x[i] = random(width);
      y[i] = random(height);
      z[i] = -1000; 
    }  
  }
}


```

<img src="https://github.com/55Kaerukun/Processing/blob/master/images/p2.png" width="600px"> 


## 球面座標の公式

```
x = r * sinθ * cosφ
y = r * sinθ * sinφ
z = r * cosθ
  
参考: https://n2p5.hatenadiary.jp/entry/2018/03/30/172351
```


```
int POINTS = 3000;
int RADIUS = 300;
float[] x = new float[POINTS];
float[] y = new float[POINTS];
float[] z = new float[POINTS];

void setup() {
  size(800, 800, P3D);
  
  stroke(0, 192, 255, 180);
  strokeWeight(4);
  
  for(int i = 0; i<POINTS; i++){
    // 球面上の座標をランダムで計算
    float radianTheta = radians(random(180));
    float radianPhi = radians(random(360));
    x[i] = RADIUS * sin(radianTheta) * cos(radianPhi);
    y[i] = RADIUS * sin(radianTheta) * sin(radianPhi);
    z[i] = RADIUS * cos(radianTheta);
  }
  
}

void draw() {

  background(0);

  // 中心点を移動
  translate(width/2, height/2, 0);
  rotateY(frameCount*0.005);
  rotateZ(frameCount*0.005);
  
  for(int i = 0; i<POINTS; i++){
    point(x[i],y[i],z[i]);
  }
}

```

<img src="https://github.com/55Kaerukun/Processing/blob/master/images/kyuumen2.png" width="600px"> 


## ノイズでアレンジ


```

int POINTS = 5000;
int RADIUS = 500;
float[] x = new float[POINTS];
float[] y = new float[POINTS];
float[] z = new float[POINTS];
float step;

void setup() {
  size(800, 800, P3D);
  blendMode(ADD);
  
  stroke(0, 192, 255, 120);
  strokeWeight(4);
  step = 0;
  
  for(int i = 0; i<POINTS; i++){
    // 球面上の座標をランダムで計算
    float radianTheta = radians(random(180));
    float radianPhi = radians(random(360));
    x[i] = RADIUS * sin(radianTheta) * cos(radianPhi);
    y[i] = RADIUS * sin(radianTheta) * sin(radianPhi);
    z[i] = RADIUS * cos(radianTheta);
    
    x[i] = noise(step) * x[i];
    y[i] = noise(step) * y[i];
    z[i] = noise(step) * z[i];
    step+=0.5;
  }
 
  
}

void draw() {

  background(0);

  // 中心点を移動
  translate(width/2, height/2, 0);
  rotateY(frameCount*0.005);
  rotateZ(frameCount*0.005);
  
  for(int i = 0; i<POINTS; i++){
    point(x[i],y[i],z[i]);  
  }
  
}

```

<img src="https://github.com/55Kaerukun/Processing/blob/master/images/hoshikuzu.png" width="600px"> 


