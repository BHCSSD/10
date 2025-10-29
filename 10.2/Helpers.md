# Helper functions 
These are like calling `rect()` or `triangle()`, in the background p5js does all the calculations for you. For these though the code isn't hidden, it will live at the bottom of your screen. 

## How to rotate things:

copy this to the bottom of your code, **do not edit this**. 
```js
function drawRotatingShape(x, y, size, angle, drawFn) {
  push();
  translate(x, y);
  rotate(angle);
  drawFn(size);
  pop();
}
```
Inside of draw you have to use **THIS WHOLE CODE** brackes and all:
```js
  drawRotatingShape(200, 200, 50, 45, (size) => {
    rect(0, 0, 50, 100);// replace this with the things you want to rotate
    });// remember this too!
```
## How to skip count using Modulo
The modulo operator (`%`) returns the remainder of a division operation, often used to determine cyclic patterns or boundaries, such as wrapping around indices in a loop or checking for even/odd numbers (`n % 2 === 0` for even). It’s particularly useful for alternating colours, or having repeating patterns. 

```js
  //Make a repeating pattern of shapes using i%4 (mod)
  if (i % 4 === 0) {
    rect(150, 150, 100, 100); 
  } else if (i % 4 === 1) {
    ellipse(200, 200, 100, 100); 
  } else if (i % 4 === 2) {
    rect(125, 175, 150, 50);
  } else if (i % 4 === 3) {
    triangle(200, 100, 150, 300, 250, 300);
  }
```

## How to draw polygons

copy this polygon helper function to the bottom of your code.  **do not edit this**.:

```javascript
function polygon(x, y, radius, npoints) {
  const angle = 360 / npoints; // Calculate angle in degrees   
  beginShape();
  for (let i = 0; i < npoints; i++) {
    const currentAngle = angle * i - 90;
    const sx = x + cos(radians(currentAngle)) * radius; 
    const sy = y + sin(radians(currentAngle)) * radius; 
    vertex(sx, sy);
  }
  endShape(CLOSE);
}
```
in draw call something like this:
```js
polygon(100, 100, 80, 5)//x,y,size,how many points
```

## How to draw stars
copy this star helper function to the bottom of your code, **do not edit it**:
```js
function drawStar(x, y, radius1, radius2, npoints) {
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
```
call it in draw:
```js
drawStar(200, 200, 100, 50, 5)//x, y, radius1, radius2, npoints
```

## Spinning triangle of doom
```js
let amplitude = 50; // How far the triangle sways
let frequency = 0.05; // Speed of the sway

function setup() {
  createCanvas(400, 400);
}

function draw() {
  background(220);
  
  let xOffset = sin(frameCount * frequency) * amplitude; // Horizontal movement
  
  // Define the stationary point
  let x1 = 200
  let y1 = 250

  // Define the swaying points
  let x2 = x1 + xOffset;
  let y2 = y1 - 50; // Top point
  let x3 = x1 - xOffset;
  let y3 = y1 - 50; // Top-left point

  // Draw the triangle
  triangle(x1, y1, x2, y2, x3, y3);
}
```
