```js
let cx = 200;
let cy = 120;
let rot = 0

function setup() {
  createCanvas(400, 600);
}

function draw() {
  background(30);
  noStroke();
  fill(34, 139, 34);

//star
  push()
    translate(200, 100)
      
      
    //drawStar(   )
  pop()


  // top
  push();
    translate(cx, cy);
 // missing something 
    triangle(0, 0,-40, 80, 40, 80 );
    //drawOrnament( )
  pop();

  // mid
  push();
    translate(cx, cy + 80);

    triangle(0, 0, -60, 100, 60, 100);
  pop();

  // BOTTOM 
  push();
    translate(cx, cy + 180);

    triangle(0, 0,-80, 120,80, 120 );
  pop();
}


function drawStar(x, y, radius1, radius2, npoints) {
  angleMode(RADIANS)
  const angle = TWO_PI / npoints; // Calculate angle in radians
  beginShape();
  for (let i = 0; i < npoints; i++) {
    // Outer points
    const outerAngle = angle * i - HALF_PI;  // Adjust to rotate correctly
    const sx1 = x + cos(outerAngle) * radius1;
    const sy1 = y + sin(outerAngle) * radius1;
    vertex(sx1, sy1);

    // Inner points
    const innerAngle = angle * (i + 0.5) - HALF_PI;  // Offset to create inner points
    const sx2 = x + cos(innerAngle) * radius2;
    const sy2 = y + sin(innerAngle) * radius2;
    vertex(sx2, sy2);
  }
  endShape(CLOSE);
}


function drawOrnament(x, y, size, r, g, b) {
  push()
  // Pulsing glow using sin
  let glow = map(sin(frameCount * 0.08), -1, 1, 20, 60);

  // Glow (drawn first, larger, transparent)
  noStroke();
  fill(r, g, b, 80);
  ellipse(x, y, size + glow);

  // Ornament body
  fill(r, g, b);
  ellipse(x, y, size);

  // Small highlight to make it look shiny
  fill(255, 180);
  ellipse(x - size * 0.2, y - size * 0.2, size * 0.25);
  pop()
}




```
