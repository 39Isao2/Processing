# HSBカラー

## カラーモード


colorModeをHSBに変更して扱うと配色設計しやすい。<br>
色相環（hue circle） : https://www.petitmonte.com/javascript/color_wheel.html <br>
```
colorMode(HSB,360,100,100,100);
```
色相、彩度、明度、透明（アルファ）で表現 トーンが固定されるので配色設計しやすい<br>

<img src="https://github.com/55Kaerukun/Processing/blob/master/images/hsb.png" width="500px">

HSBで色を探すページ<br>
https://www.peko-step.com/tool/hsvrgb.html <br>
<br>

```

void setup(){
  size(500,500);
  colorMode(HSB,360,100,100,100);
}

void draw(){
  background(0);
  
  fill(0,100,100,100);
  ellipse(width/2,height/2,100,100);
  
  fill(90,100,100,100);
  ellipse(width/2 + 150,height/2,100,100);
  
  fill(180,100,100,100);
  ellipse(width/2 - 150,height/2,100,100);
}

```

参考リンク<br>
https://note.com/fukkuu/n/nfbc9eccbac69 <br>
https://ichi-up.net/2015/099 <br>
https://www.interior-heart.com/seven-color/color/color2.html <br>
