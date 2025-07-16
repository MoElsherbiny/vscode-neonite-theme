## Where Does JavaScript Code Run?

- **Originally**: Designed to run in browsers.
- **Browser Engines**: Each browser has a JavaScript engine (e.g., SpiderMonkey in Firefox, V8 in Chrome).
- **Node.js (2009)**: Allows JavaScript to run outside browsers, enabling back-end development for web and mobile applications.

---

## Difference Between JavaScript and ECMAScript

- **ECMAScript**: A specification for scripting languages.
- **JavaScript**: A programming language that conforms to the ECMAScript specification.
- **History**: ECMAScript’s first version was released in 1997. Since 2015, annual releases have introduced new features, with **ES6 (2015)** being a major milestone.

### ECMAScript

- **Specification**: Defines core features and functionalities for scripting languages.
- **Standards Body**: Maintained by ECMA International, specifically Technical Committee 39 (TC39).

### TC39

- **Role**: A group of JavaScript developers, implementers, and academics collaborating to evolve JavaScript.
- **Versions**: Each ECMAScript version introduces new features (e.g., ES6 added classes, modules, arrow functions).
- **JavaScript Implementation**: JavaScript is an implementation of ECMAScript, executed by engines like V8 (Chrome), SpiderMonkey (Firefox), and Chakra (Edge).
- **Extensions**: JavaScript includes features beyond ECMAScript, such as the Document Object Model (DOM) for web page interaction.

**Key Points**:
- **Relationship**: ECMAScript is the blueprint; JavaScript is the implementation.
- **Evolution**: JavaScript evolves with ECMAScript updates.
- **Compatibility**: Code adhering to ECMAScript standards works across supported environments.

---

## Quick Demo

1. Open Chrome, right-click on an empty area, and select **Inspect**.
2. Go to the **Console** tab.
3. Type `console.log('Hello World');` and press Enter to see the output.
4. Try mathematical expressions like `2 + 2` (outputs `4`).
5. Type `alert('Hello World');` to display an alert popup.

---

## Variables

Variables store data temporarily in memory, like labeled boxes for organizing data. The **value** is the data stored, and the **name** is the label used to access it.

### Code Example

```javascript
let name = 'Mohamed';
console.log(name); // Outputs: Mohamed
```

- **Before ES6**: Variables were declared with `var` (has issues, covered later).
- **Modern Practice**: Use `let` for variable declarations.
- **Strings**: Use single (`'`) or double (`"`) quotes; single quotes are more common.
- **Undefined**: Variables declared without a value are `undefined`.

### Rules for Naming Variables

1. **No Reserved Keywords**: Avoid keywords like `let`, `if`, `var`.
   ```javascript
   let if; // Invalid
   ```
2. **Meaningful Names**: Use descriptive names for clarity.
   ```javascript
   let firstName; // Good
   ```
3. **No Numbers at Start**: Variable names cannot begin with a number.
   ```javascript
   let 1name; // Invalid
   ```
4. **No Spaces or Hyphens**: Use camelCase for multi-word names.
   ```javascript
   let firstName; // Valid
   ```
5. **Case-Sensitive**: `firstName` and `FirstName` are different variables.

### Declaring Multiple Variables

1. **Single Line**:
   ```javascript
   let firstName = 'Mohamed', lastName = 'Elsherbiny';
   ```
2. **Multiple Lines (Preferred)**:
   ```javascript
   let firstName = 'Mohamed';
   let lastName = 'Elsherbiny';
   ```

**Note**: Console may show `undefined` for `let` declarations due to no return value, but variables are correctly assigned.

---

## Variables: Let vs. Const vs. Var

### Let

- **Scope**: Block-scoped (confined to `{}` blocks).
- **Hoisting**: Hoisted but not initialized (`ReferenceError` if accessed before declaration).
- **Reassignment**: Values can be reassigned.
  ```javascript
  let city = 'Cairo';
  city = 'Alexandria'; // Valid
  ```

### Const

- **Scope**: Block-scoped.
- **Hoisting**: Hoisted but not initialized (`ReferenceError` if accessed before declaration).
- **Reassignment**: Cannot reassign the variable, but object/array properties can change.
  ```javascript
  const country = 'Egypt';
  // country = 'Jordan'; // Error
  const person = { name: 'Mohamed' };
  person.name = 'Elsherbiny'; // Valid
  ```

### Var

- **Scope**: Function-scoped or global.
- **Hoisting**: Hoisted and initialized as `undefined`.
- **Reassignment**: Values can be reassigned.
  ```javascript
  var age = 25;
  age = 26; // Valid
  ```

### Key Differences

1. **Scope**: `let` and `const` are block-scoped; `var` is function-scoped.
2. **Hoisting**: `let` and `const` cause `ReferenceError` if accessed before initialization; `var` returns `undefined`.
3. **Reassignment**: `const` prevents reassignment; `let` and `var` allow it.

### Hoisting

Hoisting moves variable and function declarations to the top of their scope during compilation.

- **Var**:
  ```javascript
  console.log(name); // undefined
  var name = 'Mohamed';
  ```
- **Let/Const**:
  ```javascript
  console.log(age); // ReferenceError
  let age = 30;
  ```
- **Functions**:
  ```javascript
  greet(); // Hello!
  function greet() {
    console.log('Hello!');
  }
  ```