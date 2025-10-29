# 10.1 Lesson: Boolean Quick Check 2


> ---
> ## INFO DUMP
> 
> **What are logical operators?**
> 
> Sometimes you need to check **more than one condition** at the same time. Logical operators help you do that.
> 
> The most common ones are:
> 
> * `&&` (AND): Both conditions must be true for the code to run.
> * `||` (OR): At least one condition must be true for the code to run.
>   * You can find the `|` right above the `enter` key
> * `!=` (NOT EQUAL): True if the two values are **not equal**.
> 
> ---


### 1. AND (`&&`)

Use `&&` when **both conditions must be true**.

```javascript
function draw() {
  background(220);

  if (mouseX > 100 && mouseX < 300) {
    fill("green"); // mouseX is between 100 and 300
  } else {
    fill("red");
  }

  circle(200, 200, 50);
}
```

**Explanation:**

* `mouseX > 100 && mouseX < 300` means the mouse must be **greater than 100 AND less than 300**.
* Only if both are true will the circle turn green.

---

### 2. OR (`||`)

Use `||` when **either condition can be true**.

```javascript
function draw() {
  background(220);

  if (mouseX < 100 || mouseX > 300) {
    fill("blue"); // mouseX is on the left or right side
  } else {
    fill("orange");
  }

  circle(200, 200, 50);
}
```

**Explanation:**

* `mouseX < 100 || mouseX > 300` means the circle turns blue if **the mouse is on either side**.
* Only when **both conditions are false** does it turn orange.

---

### 3. NOT EQUAL (`!=`)

Use `!=` to check if **two values are not the same**.

```javascript
function draw() {
  background(220);

  let mouseLeft = mouseX < 200;

  if (mouseLeft != true) {
    fill("purple"); // mouse is not on the left
  } else {
    fill("pink");
  }

  circle(200, 200, 50);
}
```

**Explanation:**

* `mouseLeft != true` checks if `mouseLeft` is **not true**.
* This is another way of saying **mouse is on the right side**.

---

### Combining Multiple Operators

You can also combine them:

```javascript
if ((mouseX > 50 && mouseX < 150) || (mouseY > 250 && mouseY < 350)) {
  fill("yellow"); // mouse is in a vertical OR horizontal zone
}
```

### Tips

* Use parentheses `()` to make your logic clear... BEDMAS FTW
* Start with simple conditions, then combine them.
* Logical operators are essential for **collision detection, interactive games, and controlling multiple rules at once**.

