# Interactive Coding - Review

Home content: http://imm.sheridanc.on.ca/2025/ic/index.html

# Keypoints for IM Theory


`Media` = many; `Medium` = one, something in between.

`IM` is about:
 - creates `context` -> people make `content`, 
 - diff vs `web design` which makes `content`
 - `MOTTO`: `goal of IM`: 
    - LESS ABOUT: `read` `look` `watch` `listen`
    - MORE ABOUT: `write` `draw` `make` `do` `operate` `play` `organize`
 - `code` -> `rules of the environment`

### Canvas VS DOM
Use the `Canvas` for free-form interaction, such as making `art` and `games`.  
The `DOM` is better for displaying and managing `text` and `information`.  
While text can be added to the canvas, it’s not easily `searchable` or `selectable` like in the DOM.  
The DOM excels for `long text`, `scrolling pages`, and `information apps` like social media, forums, and shopping sites.


### 10 usage of canvas (story mode): 
I began by making `Generative Art` for a fun `Game` to teach through `e-Learning`. Then, I improved the `UX/UI` of a `Data Visualization` project, ran some `Interactive Ads`, and created `Interactive Logos` for businesses. Finally, I designed `Puzzles` and `InfoActives` for a festive `Holiday Card`.


### Creator Diagram (formular mode):

**Creator** = `Ideator` && `Maker` && `Developer` &&  `Designer` 

( `I.M.D.D` for short or `DIDM`)


### Conclusion
Each `medium`(`Print`, `Radio`, `TV`, `Web`) has unique factors for effective content. 
Using these factors **advances culture**. 
Traditional media is `authoritative`, but the `Internet` lets users `create` and `communicate`. 
Combine this with `programming` for new `content creation` opportunities.



Ref Diagrams:
http://imm.sheridanc.on.ca/2025/ic/lesson01/context.jpg
http://imm.sheridanc.on.ca/2025/ic/lesson01/content.jpg



# Programming Basics and Logic

## 1. Know the Programming Basics

### Variables
- **var, const, let**
  - `var` is function-scoped, while `let` and `const` are block-scoped.
  - **`let`** allows reassignment of the variable.
  - **`const`** creates a constant and cannot be reassigned (though object properties can still change).

```javascript
var x = 10;
let y = 20;
y = 25; // valid, because let allows reassignment
const z = 30;
z = 35; // error, const cannot be reassigned
```

### Concatenation
- Using `+` to concatenate strings:

```javascript
let greeting = 'Hello' + ' ' + 'World!';
```

### Arrays
- Defined using `[]`, accessed by index:

```javascript
let fruits = ['apple', 'banana', 'cherry'];
console.log(fruits[0]); // apple
```


- Get random element from array
```javascript
// Get random element from array
let fruits = ['apple', 'banana', 'cherry'];
let randomFruit = fruits[Math.floor(Math.random() * fruits.length)];
console.log('Random fruit:', randomFruit);
```
### Objects
- Defined using `{}`, accessed with `.propName` or with bracket notation `['propName']`

```javascript
let person = { name: 'John', age: 25 };
console.log(person.name); // John
console.log(person['name']); // John

```

### Functions
- Named, anonymous, and arrow functions:

```javascript
function namedFunction() {
    console.log('I am a named function.');
}

const anonymousFunction = function() {
    console.log('I am an anonymous function.');
}

const arrowFunction = () => {
    console.log('I am an arrow function.');
}
```

### Classes
- Use the `new` keyword to create instances:

```javascript
class Car {
    constructor(brand, model) {
        this.brand = brand;
        this.model = model;
    }

    drive() {
        console.log(`${this.brand} ${this.model} is driving!`);
    }
}

let myCar = new Car('Toyota', 'Corolla');
myCar.drive(); // Toyota Corolla is driving!
```

### Properties and Methods
- **Properties** are values inside objects or classes.
- **Methods** are functions inside objects or classes.

```javascript
let car = { brand: 'Toyota', drive: function() { console.log('Driving!'); } };
car.drive(); // Driving!
```

### Parameters
- Values passed into functions:

```javascript
function sum(a, b) {
    return a + b;
}
console.log(sum(5, 10)); // 15
```

## 2. Logic and Flow

### Conditionals
- Using `if`, `else if`, and `else` for decision making:

```javascript
let age = 18;
if (age >= 18) {
    console.log('Adult');
} else {
    console.log('Not an adult');
}
```

### Loops
- `for` loop comparison between **ZIM** and **vanilla JS**:

**ZIM Example**:
```javascript
var container = new Container().alp(.1).addTo();
// LOOP FUNCTION - for more examples see the CODE Module loop() function
loop(1000, i=>{ // gets passed an index i, totalLoops 1000, startIndex 0, endIndex 999, obj 1000
   // make 1000 rectangles
   new Rectangle().loc(rand(W-100), rand(H-100), container);
});

// LOOP METHOD
// loop through children of the container
container.loop((child, i)=>{ // gets passed the child, index, total, start, end and obj
   child.x += i*2;
   child.y += i*2;
}, true); // true would reverse - so highest in stack to lowest, with i going from numChildren-1 to 0
```

**Vanilla JS Example**:
```javascript
for (let i = 0; i < 5; i++) {
    console.log('Loop iteration:', i);
}

// For loop using array length
let fruits = ['apple', 'banana', 'cherry'];
for (let i = 0; i < fruits.length; i++) {
    console.log('Fruit:', fruits[i]);
}

// forEach loop
fruits.forEach((fruit, index) => {
    console.log(`Fruit ${index + 1}: ${fruit}`);
});
```

### Timeout and Interval (Compare **ZIM** and **vanilla JS**):

**ZIM Example**:

Dan did mention why he designed this way: time comes first is more easy to use.

```javascript
// moves the circle 100 pixels after one second
timeout(1, ()=>{
   circle.x += 100;
   S.update();
});

// every second the circle will move 100 pixels
interval(1, ()=>{
   circle.x += 100;
   S.update();
});
```

**Vanilla JS Example**:
```javascript
setTimeout(() => {
    console.log('Timeout in Vanilla JS');
}, 1000);

setInterval(() => {
    console.log('Interval in Vanilla JS');
}, 500);
```

### Ticker and Request Animation Frame
- Compare **ZIM** `Ticker.add()` and **vanilla JS** `requestAnimationFrame()`:

**ZIM Example**:
```javascript
Ticker.add(() => {
    console.log('ZIM Ticker Animation');
});
```

**Vanilla JS Example**:
```javascript
function animate() {
    console.log('Vanilla JS Animation');
    requestAnimationFrame(animate);
}
requestAnimationFrame(animate);
```


# ZIM.js Review

## Shapes in ZIM
ZIM provides several shape constructors that allow you to create various forms on the canvas. Here are some commonly used shapes:

### Circle
Creates a circle.
```js
const circle = new Circle(100, purple).center().drag({onTop: false});
```

### Rectangle
Creates a rectangle.
```js
const rectangle = new Rectangle(100, 50, blue).center().drag();
```

### Triangle
Creates a triangle.
```js
const triangle = new Triangle(100, red).center();
```

### Blob
Creates a freeform shape.
```js
const blob = new Blob(200, green).center();
```

### Squiggle
Creates a wavy or irregular shape.
```js
const squiggle = new Squiggle().center();
```

## Frame: Loading and Showing Assets
The `Frame` is the ZIM workspace. It's required to render the stage and interact with various display objects.

```js
new Frame(FIT, 1024, 768, light, dark, ready, assets, path);
```

- `FIT`: Resizes canvas to fit within the window.
- `ready()`: A callback function that is invoked once the frame and assets are loaded.

### Loading Picture Assets
You can load assets by specifying an array of asset names and a path. Here's an example where images and fonts are loaded:
```js
const assets = ["bitcoin.png", "eth.png", "head.png", "Computer.ttf"];
const path = "assets/";
new Frame(FIT, 1024, 768, light, dark, ready, assets, path);
```

Once the assets are loaded, you can display them:
```js
const pic = new Pic("head.png").sca(0.3).center();
```

## UI Components

ZIM provides several pre-built UI components like buttons, sliders, dials, and labels.

### Buttons
```js
const button = new Button(AUTO, 60, "CLICK").center().tap(() => {
    zogy("Button clicked!");
});
```

### Slider
```js
const slider = new Slider({step: 1}).pos(0, 50, RIGHT, BOTTOM).change((e) => {
    zogo(e.target.currentValue);
});
```

### Dial
```js
const dial = new Dial({step:1, backgroundColor:"violet"})
   .center()
   .change(()=>{
      zog(dial.currentValue); // 1-10 in steps of 1
   });
S.update();
```

### Label
```js
const title = new Label({text: "Components in ZIM", color: purple}).pos(50, 50);
```

## Methods in ZIM

### `addTo()`

```js
const circle = new Circle(50, red);
circle.addTo(stage); 
// or just circle.addTo(); // for the default frame's stage
var circle = new Circle(50, red).addTo();
```

### `removeFrom()`
Removes a display object from its container.

```js
const circle = new Circle(50, red);
circle.addTo(); // adds to stage
// later
circle.removeFrom(); // same as circle.removeFrom(stage)
```

### `center()`
Centers a display object on the stage.

```js
const circle = new Circle(100, blue).center();
```

### `centerReg()`
Centers the registration point of a display object and then centers it on the stage.

```js
const rect = new Rectangle(100, 50, red).centerReg();
```

### `animate()`
Animates a display object with various properties.

```js
circle.animate({props: {scale: 2}, time: 1});
```

### `drag()`
Allows a display object to be dragged.

```js
circle.drag();
```

### `loc()`
Positions a display object based on x and y coordinates.

```js
new Circle().loc(400, 400); // places reg of circle at 400, 400
// note, this is different than pos(400, 400) which would place left top of circle at 400, 400
```

### `pos()`
Positions a display object relative to other objects.

```js
title.pos(50, 50);
```

### `rot()`
Rotates a display object.

```js
circle.rot(45);
```

### `alp()`
Sets the transparency of a display object.

```js
circle.alp(0.5);
```

### `sca()`
Scales a display object.

```js
circle.sca(1.5);
```

### `reg()`
Sets the registration point of a display object.

```js
circle.reg(CENTER);
```

## Events in ZIM

### `on()`
The `on()` method is used to capture events such as click, change, or keydown.

```js
button.on("click", () => {
    zogy("Button clicked!");
});
```
