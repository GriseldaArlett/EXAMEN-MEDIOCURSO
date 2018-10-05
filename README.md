int diceSize;

void setup() {
  diceSize=117;
   frameRate(10);
  size(500,500);
  noLoop();
 
}

void draw() {
  background(#FA0000);

  //dado
  noStroke();
  fill(#FFFAFA);
  rectMode(CENTER);
  rect(width/2, height/2, diceSize, diceSize, diceSize/5);

  
  fill(50);
  int side = int(random(1, 7));
  if (side == 1 || side == 3 || side == 5)
    ellipse(width/2, height/2, diceSize/5, diceSize/5); 
  if (side == 2 || side == 3 || side == 4 || side == 5 || side == 6) { 
    ellipse(width/2 - diceSize/4, height/2 - diceSize/4, diceSize/5, diceSize/5);
    ellipse(width/2 + diceSize/4, height/2 + diceSize/4, diceSize/5, diceSize/5);
  }
  if (side == 4 || side == 5 || side == 6) {
    ellipse(width/2 - diceSize/4, height/2 + diceSize/4, diceSize/5, diceSize/5);
    ellipse(width/2 + diceSize/4, height/2 - diceSize/4, diceSize/5, diceSize/5);
  }
  if (side == 6) {
    ellipse(width/2, height/2 - diceSize/4, diceSize/5, diceSize/5);
    ellipse(width/2, height/2 + diceSize/4, diceSize/5, diceSize/5);
  }

  
  if (mousePressed && mouseButton == LEFT)
    noLoop();
}

void mousePressed() {
  loop();
}
