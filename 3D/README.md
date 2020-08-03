

# 3Dプログラミング

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

<img src="https://github.com/55Kaerukun/Processing/blob/master/images/sphere.png" width="800px"> 

## 大量のパーティクル

```

int num = 100;
float[] x = new float[num]; //100個保存できる棚（配列）
float[] y = new float[num];
float[] z = new float[num];

void setup(){
  size(1000,1000,P3D);
  
  ////0から100まで1ずつ増えるループ
  for(int i=0; i<num; i+=1){
    x[i] = random(width);
    y[i] = random(height);
    z[i] = random(-1000,0); //-1が奥、+が手前
  } 
  
}


void draw(){
  background(0);
  stroke(255,255,0); //線の色
  strokeWeight(2);
  
  for(int i=0; i<num; i+=1){
    
    // 点
    point(x[i], y[i],z[i]);
    
    z[i] = z[i] + 20; //20ずつ手前に移動
    
    
    //z座標が0以上になったらランダムで再配置
    if(z[i] > 100){
      x[i] = random(width);
      y[i] = random(height);
      z[i] = -1000; 
    }  
  }
}


```





