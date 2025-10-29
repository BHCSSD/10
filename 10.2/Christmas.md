
```
let cx = 200;
let cy = 200;

function setup() {
  createCanvas(400, 600);
}

function draw() {
  background(30); // Dark background for night effect

  // Draw the tree
  fill(34, 139, 34); // Green colour for the tree
  noStroke();

  // Tree layers 
  triangle(cx, cy, cx, cy, cx , cy); // Top layer
  triangle(cx, cy, cx, cy , cx, cy); // Middle layer
  triangle(cx, cy, cx, cy , cx, cy); // Bottom layer
}
```
