```
DVD
```
```js
let dvd = {} // look at me, im an object... I need information to fill me. see setup. 

function setup() {
  createCanvas(800, 600);
  textSize(32);
  textAlign(CENTER, CENTER);

  //step 0 fill the cx and cy and speeds for the logo
  

}

function draw() {
  background(0);

  // Step 4 fill colour from the object's current colour
  fill(dvd.colour);
  text("DVD", dvd.cx, dvd.cy);

  //Step 1 Move the text


  //step 2 Bounce X wall hit and on the Y wall hit
  //step 3 add in colour change when wall hit
  



  

  
}

// Helper Function to return a random colour  you dont need to change anything here. 
function getRandomcolour() {
 colour = colour(random(255), random(255), random(255))
  return  colour // fancy, look you can save colour RGB into 1 variable 
}

```
