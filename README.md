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
