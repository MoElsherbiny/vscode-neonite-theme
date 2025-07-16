## Introduction to OOP

**Definition**: Object-Oriented Programming (OOP) is a paradigm centered around objects, organizing related variables and functions into units.

**JavaScript and OOP**:
- JavaScript is prototype-based but supports class syntax (ES6+).
- Frameworks like Angular use OOP concepts.

**Importance**:
- Widely used in industry.
- Common in technical interviews.
- Enhances job candidacy.

---

## Core OOP Concepts

### Encapsulation

Groups related properties and methods into objects, reducing complexity.

**Procedural Example**:
```javascript
let baseSalary = 30_000;
let overtime = 10;
let rate = 20;
function getWage(baseSalary, overtime, rate) {
  return baseSalary + overtime * rate;
}
```

**OOP Example**:
```javascript
let employee = {
  baseSalary: 30_000,
  overtime: 10,
  rate: 20,
  getWage() {
    return this.baseSalary + this.overtime * this.rate;
  }
};
console.log(employee.getWage());
```

**Benefits**:
- Fewer parameters.
- Easier maintenance.

### Abstraction

Hides implementation details, exposing only essential features.

**Example: DVD Player**:
```javascript
class DVDPlayer {
  #readDisc() {
    console.log('Reading disc...');
  }
  #decodeContent() {
    console.log('Decoding content...');
  }
  play() {
    console.log('Playing...');
    this.#readDisc();
    this.#decodeContent();
  }
}
const player = new DVDPlayer();
player.play();
```

**Benefits**:
- Simplified interfaces.
- Reduced change impact.

### Inheritance

Allows objects to share properties/methods, eliminating redundancy.

**Example: HTML Elements**:
```javascript
class HTMLElement {
  constructor() {
    this.hidden = false;
    this.innerHTML = '';
  }
  click() {
    console.log('Element clicked');
  }
}
class TextBox extends HTMLElement {
  constructor() {
    super();
    this.placeholder = 'Enter text';
  }
}
```

**Benefits**:
- Reusable code.
- Centralized logic.

### Polymorphism

Allows objects to use the same method name with different behaviors.

**Example: Rendering Elements**:
```javascript
class HTMLElement {
  render() {}
}
class TextBox extends HTMLElement {
  render() {
    console.log('Render TextBox');
  }
}
class Checkbox extends HTMLElement {
  render() {
    console.log('Render Checkbox');
  }
}
const elements = [new TextBox(), new Checkbox()];
elements.forEach((element) => element.render());
```

**Benefits**:
- Cleaner code.
- Dynamic behavior.

---

## OOP Stopwatch Implementation

An improved stopwatch using OOP principles:

```javascript
class StopWatch {
  #startTime;
  #elapsedTime;
  #intervalId;
  constructor() {
    this.#startTime = null;
    this.#elapsedTime = 0;
    this.#intervalId = null;
  }
  start() {
    if (this.#intervalId) {
      console.warn('Stopwatch is already running.');
      return;
    }
    if (!this.#startTime) {
      this.#startTime = Date.now() - this.#elapsedTime;
    }
    this.#intervalId = setInterval(() => {
      this.#elapsedTime = Date.now() - this.#startTime;
      console.log(this.formatTime(this.#elapsedTime));
    }, 1000);
  }
  stop() {
    if (!this.#intervalId) {
      console.warn('Stopwatch is not running.');
      return;
    }
    clearInterval(this.#intervalId);
    this.#intervalId = null;
  }
  reset() {
    this.stop();
    this.#startTime = null;
    this.#elapsedTime = 0;
    console.log('Stopwatch has been reset.');
  }
  formatTime(milliseconds) {
    const totalSeconds = Math.floor(milliseconds / 1000);
    const seconds = totalSeconds % 60;
    const minutes = Math.floor(totalSeconds / 60) % 60;
    const hours = Math.floor(totalSeconds / 3600);
    return `${hours.toString().padStart(2, '0')}:${minutes.toString().padStart(2, '0')}:${seconds.toString().padStart(2, '0')}`;
  }
  getElapsedTime() {
    return this.formatTime(this.#elapsedTime);
  }
  isRunning() {
    return !!this.#intervalId;
  }
}
const stopwatch = new StopWatch();
stopwatch.start();
setTimeout(() => stopwatch.stop(), 5000);
setTimeout(() => stopwatch.reset(), 7000);
```

**Improvements**:
- **Encapsulation**: Private properties (`#startTime`, `#elapsedTime`, `#intervalId`).
- **Public API**: Methods like `start`, `stop`, `reset`.
- **Error Handling**: Prevents misuse (e.g., starting an already running stopwatch).
- **Modularity**: Reusable `formatTime` method.
- **Extensibility**: Supports future features like lap tracking.

**Future Extensions**:
- **Lap Feature**:
  ```javascript
  #laps = [];
  recordLap() {
    if (!this.isRunning()) {
      console.warn("Stopwatch is not running.");
      return;
    }
    this.#laps.push(this.getElapsedTime());
    console.log("Lap recorded:", this.getElapsedTime());
  }
  getLaps() {
    return this.#laps;
  }
  ```
- Event handling for UI integration.
- Custom time display formats.