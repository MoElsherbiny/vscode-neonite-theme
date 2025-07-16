## JavaScript Data Types

JavaScript data types are divided into **Value Types (Primitives)** and **Reference Types (Objects)**.

### Value Types (Primitives)

- Stored directly in variables.
- Copies are independent.
- Immutable (changes create new values).
- Types: Number, String, Boolean, Symbol, Undefined, Null, BigInt.

**Example**:
```javascript
let a = 5;
let b = a;
a = 10;
console.log(a); // 10
console.log(b); // 5
```

### Reference Types (Objects)

- Store references to memory locations.
- Copies share the same reference.
- Mutable (changes affect all references).
- Types: Objects, Arrays, Functions, Dates, RegExp.

**Example**:
```javascript
let obj1 = { value: 5 };
let obj2 = obj1;
obj1.value = 10;
console.log(obj1.value); // 10
console.log(obj2.value); // 10
```

---

## Primitive Types

### String

Represents textual data (string literals).
```javascript
let greeting = 'Hello, Mohamed!';
```

### Number

Represents integers and floating-point numbers.
```javascript
let age = 25;
```

### Boolean

Represents `true` or `false`.
```javascript
let isStudent = true;
```

### Undefined

Represents uninitialized variables.
```javascript
let unknown;
console.log(unknown); // undefined
```

### Null

Represents the intentional absence of a value.
```javascript
let emptyValue = null;
```

### Symbol

Unique identifiers (introduced in ES6).
```javascript
let uniqueId = Symbol('id');
let user = { name: 'Alice', [uniqueId]: 123 };
console.log(user[uniqueId]); // 123
```

### BigInt

Represents large integers (introduced in ES2020).
```javascript
let bigNumber = BigInt(9007199254740991);
```

---

## Reference Types

### Objects

Collections of key-value pairs (object literals: `{}`).
```javascript
let person = {
  firstName: 'Mohamed',
  lastName: 'Elsherbiny',
  age: 25
};
console.log(person.firstName); // Mohamed
console.log(person['lastName']); // Elsherbiny
```

### Arrays

Ordered collections (array literals: `[]`).
```javascript
let fruits = ['Apple', 'Banana', 'Cherry'];
console.log(fruits[0]); // Apple
```

### Functions

First-class objects, callable and reusable.
```javascript
function greet(name) {
  return `Hello, ${name}!`;
}
console.log(greet('Mohamed')); // Hello, Mohamed!
```

**Function Example with Parameters**:
```javascript
function greet(firstName, lastName) {
  console.log('Hello ' + firstName + ' ' + lastName);
}
greet('John', 'Smith'); // Hello John Smith
```

### Dates

Represent moments in time.
```javascript
let today = new Date();
console.log(today); // Current date and time
```

### RegExp

Patterns for string matching.
```javascript
let pattern = /hello/;
let testString = 'hello world';
console.log(pattern.test(testString)); // true
```

### Null and Undefined as Reference Types

- **Null**: Intentional absence of an object value.
- **Undefined**: Uninitialized variables.

### Key Differences: Primitive vs. Reference Types

1. **Memory**: Primitives store values; reference types store memory addresses.
2. **Mutability**: Primitives are immutable; reference types are mutable.
3. **Equality**: Primitives are compared by value; reference types by reference.

**Example with Functions**:
```javascript
function increment(num) {
  num++;
}
let number = 5;
increment(number);
console.log(number); // 5 (primitive, unchanged)

function incrementValue(obj) {
  obj.value++;
}
let myObject = { value: 5 };
incrementValue(myObject);
console.log(myObject.value); // 6 (reference, changed)
```

---

## Operators

### Arithmetic Operators

- **Addition (`+`)**: `5 + 3 // 8`
- **Subtraction (`-`)**: `5 - 3 // 2`
- **Multiplication (`*`)**: `5 * 3 // 15`
- **Division (`/`)**: `6 / 3 // 2`
- **Modulus (`%`)**: `7 % 3 // 1`
- **Exponentiation (`**`)**: `2 ** 3 // 8`

### Assignment Operators

- **Assignment (`=`)**: `let x = 10;`
- **Addition Assignment (`+=`)**: `x += 5; // x = x + 5`
- **Subtraction Assignment (`-=`)**: `x -= 3;`
- **Multiplication Assignment (`*=`)**: `x *= 2;`
- **Division Assignment (`/=`)**: `x /= 2;`
- **Modulus Assignment (`%=`)**: `x %= 3;`

### Comparison Operators

- **Equal (`==`)**: `5 == '5' // true`
- **Strict Equal (`===`)**: `5 === '5' // false`
- **Not Equal (`!=`)**: `5 != '5' // false`
- **Strict Not Equal (`!==`)**: `5 !== '5' // true`
- **Greater Than (`>`)**: `5 > 3 // true`
- **Less Than (`<`)**: `5 < 3 // false`
- **Greater Than or Equal (`>=`)**: `5 >= 5 // true`
- **Less Than or Equal (`<=`)**: `5 <= 5 // true`

### Logical Operators

- **AND (`&&`)**: `true && false // false`
  ```javascript
  let highIncome = true;
  let goodCreditScore = true;
  let eligibleForLoan = highIncome && goodCreditScore;
  console.log(eligibleForLoan); // true
  ```
- **OR (`||`)**: `true || false // true`
  ```javascript
  console.log(false || 'Mosh'); // Mosh
  console.log(false || 1 || 2); // 1 (short-circuiting)
  ```
- **NOT (`!`)**: `!true // false`

**Logical Operators with Non-Booleans**:
```javascript
let userColor = 'red';
let defaultColor = 'blue';
let currentColor = userColor || defaultColor;
console.log(currentColor); // red
```

### Bitwise Operators

- **AND (`&`)**: `5 & 1 // 1`
- **OR (`|`)**: `5 | 1 // 5`
- **XOR (`^`)**: `5 ^ 1 // 4`
- **NOT (`~`)**: `~5 // -6`
- **Left Shift (`<<`)**: `5 << 1 // 10`
- **Right Shift (`>>`)**: `5 >> 1 // 2`
- **Zero-Fill Right Shift (`>>>`)**: `5 >>> 1 // 2`

### String Operators

- **Concatenation (`+`)**:
  ```javascript
  let greeting = 'Hello' + ' ' + 'Mohamed'; // Hello Mohamed
  ```

### Other Operators

- **Conditional (`?:`)**:
  ```javascript
  let age = 18;
  let canVote = age >= 18 ? 'Yes' : 'No'; // Yes
  ```
- **Comma (`,`)**:
  ```javascript
  let a = 1, b = 2, c = 3;
  ```