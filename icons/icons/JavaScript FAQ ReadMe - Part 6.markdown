## Scope in JavaScript

Scope determines where variables are accessible.

### Global Scope

Accessible throughout the program:
```javascript
const color = 'red';
function displayColor() {
  console.log(color); // red
}
displayColor();
```

### Local Scope

**Function Scope**:
```javascript
function start() {
  const message = 'hello';
  console.log(message); // hello
}
start();
console.log(message); // ReferenceError
```

**Block Scope**:
```javascript
if (true) {
  const conditionMessage = 'bye';
  console.log(conditionMessage); // bye
}
console.log(conditionMessage); // ReferenceError
```

**Loop Scope**:
```javascript
for (let i = 0; i < 5; i++) {
  console.log(i); // 0, 1, 2, 3, 4
}
console.log(i); // ReferenceError
```

**Same Variable Name**:
```javascript
function start() {
  const message = 'start message';
  console.log(message); // start message
}
function stop() {
  const message = 'stop message';
  console.log(message); // stop message
}
start();
stop();
```

**Local vs. Global**:
```javascript
const color = 'red';
function changeColor() {
  const color = 'blue';
  console.log(color); // blue
}
changeColor();
console.log(color); // red
```

### Best Practices

- Avoid global variables to prevent conflicts.
- Use `let` or `const` for block scope.
- Use descriptive names to avoid overwriting.

---

## Var vs. Let

**Var**:
- Function-scoped.
- Hoisted with `undefined`.
```javascript
function start() {
  for (var i = 0; i < 5; i++) {
    console.log(i);
  }
  console.log('Outside loop:', i); // 5
}
start();
```

**Let**:
- Block-scoped.
```javascript
function start() {
  for (let i = 0; i < 5; i++) {
    console.log(i);
  }
  console.log('Outside loop:', i); // ReferenceError
}
start();
```

**Global Var**:
```javascript
var color = 'blue';
let age = 30;
console.log(window.color); // blue
console.log(window.age); // undefined
```

**Problems with Var**:
- No block scope.
- Global namespace pollution.
- Hoisting issues.

**Best Practices**:
- Use `let` and `const`.
- Avoid `var` unless maintaining legacy code.

---

## The `this` Keyword

`this` refers to the object executing the current function.

### Methods in Objects
```javascript
const video = {
  title: 'JavaScript Tutorial',
  play() {
    console.log(this);
  }
};
video.play(); // video object
```

### Regular Functions
```javascript
function playVideo() {
  console.log(this);
}
playVideo(); // window/global
```

### Constructor Functions
```javascript
function Video(title) {
  this.title = title;
}
const myVideo = new Video('JavaScript Basics');
console.log(myVideo); // { title: 'JavaScript Basics' }
```

### Callbacks
```javascript
const video = {
  title: 'Advanced JavaScript',
  tags: ['a', 'b', 'c'],
  showTags() {
    this.tags.forEach(function(tag) {
      console.log(this.title, tag);
    });
  }
};
video.showTags(); // undefined a, undefined b, undefined c
```

**Fix with thisArg**:
```javascript
showTags() {
  this.tags.forEach(function(tag) {
    console.log(this.title, tag);
  }, this);
}
```

**Fix with Arrow Functions**:
```javascript
showTags() {
  this.tags.forEach((tag) => {
    console.log(this.title, tag);
  });
}
```

### Changing `this` Value

**Using Self**:
```javascript
const video = {
  title: 'My Video',
  tags: ['javascript', 'coding', 'tutorial'],
  showTags() {
    const self = this;
    this.tags.forEach(function(tag) {
      console.log(self.title, tag);
    });
  }
};
```

**Using bind**:
```javascript
showTags() {
  this.tags.forEach(function(tag) {
    console.log(this.title, tag);
  }.bind(this));
}
```

**Using call/apply**:
```javascript
function playVideo(a, b) {
  console.log(this.title, a, b);
}
playVideo.call({ title: 'Video 1' }, 1, 2); // Video 1 1 2
playVideo.apply({ title: 'Video 1' }, [1, 2]); // Video 1 1 2
```

**Using bind for Permanent Binding**:
```javascript
const boundPlayVideo = playVideo.bind({ title: 'Video 1' });
boundPlayVideo(1, 2); // Video 1 1 2
```