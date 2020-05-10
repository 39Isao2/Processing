

# 3Dプログラミング

boxの表示

<img src="https://github.com/55Kaerukun/Processing/blob/master/images/box.png" width="800px"> 

```
void setup() {
  size(500, 500, P3D);
}
 
void draw() {
  background(0);
  //stroke(0,0,255);
  //noFill();
  translate(width/2,height/2);
  rotateX(radians(mouseX));
  rotateY(radians(mouseY));
  box(100, 100, 100); //100x100x100pxの立方体を描
}
```

sphereの表示

<img src="https://github.com/55Kaerukun/Processing/blob/master/images/sphere.png" width="800px"> 


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

大量の線形パーティクル

```
int num = 100;
float[] x = new float[num]; //100個保存できる棚（配列）
float[] y = new float[num];
float[] z = new float[num];

void setup(){
  size(1000,1000,P3D);
  
  //0から100まで1ずつ増えるループ
  for(int i=0; i<num; i+=1){
    x[i] = random(width);
    y[i] = random(height);
    z[i] = i * -10; //-10にかけると奥にいく
  } 
}


void draw(){
  background(0);
  stroke(255); //線の色
  
  for(int i=0; i<num; i+=1){
    // 罫線 XYZ
    line(x[i],y[i],z[i],x[i],y[i],z[i]-40); //zの-40が線の長さ
    z[i] = z[i] + 20; //20ずつ手前に移動
    
    //z座標が0以上になったらランダムで再配置
    if(z[i] > 0){
      x[i] = random(width);
      y[i] = random(height);
      z[i] = -1000; 
    } 
  }
}


```





