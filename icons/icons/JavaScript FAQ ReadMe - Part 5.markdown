## Dynamic Typing and Arguments

JavaScript is **dynamically typed**, allowing variables to hold different types:
```javascript
let example = 42;
example = 'Hello, world!';
```

### Function Parameters and Arguments

- **Fewer Arguments**: Undefined for missing parameters.
- **Extra Arguments**: Ignored unless handled.
```javascript
function sum(a, b) {
  return a + b;
}
console.log(sum(1, 2)); // 3
console.log(sum(1)); // NaN
console.log(sum(1, 2, 3)); // 3
```

### Arguments Object

Array-like object containing all passed arguments:
```javascript
function logArgs() {
  console.log(arguments);
}
logArgs(1, 2, 3); // {0: 1, 1: 2, 2: 3, length: 3}
```

**Sum All Arguments**:
```javascript
function sumAll() {
  let total = 0;
  for (let value of arguments) {
    total += value;
  }
  return total;
}
console.log(sumAll(1, 2, 3, 4, 5)); // 15
```

**Modern Alternative (Rest Operator)**:
```javascript
function sumAll(...args) {
  return args.reduce((total, value) => total + value, 0);
}
console.log(sumAll(1, 2, 3, 4, 5)); // 15
```

---

## Rest Operator

Collects all additional arguments into an array:
```javascript
function sum(...args) {
  console.log(args);
}
sum(1, 2, 3, 4, 5); // [1, 2, 3, 4, 5]
```

**Example: Shopping Cart**:
```javascript
function calculateTotal(discount, ...prices) {
  const total = prices.reduce((sum, price) => sum + price, 0);
  return total * (1 - discount);
}
console.log(calculateTotal(0.1, 20, 30)); // 45
```

**Rules**:
- Must be the last parameter.
```javascript
function example(param1, ...rest) {} // Valid
function invalidExample(...rest, param2) {} // SyntaxError
```

---

## Default Parameters

Provide default values for parameters:
```javascript
function calculateDiscountedPrice(price, discount = 10) {
  return price - (price * discount) / 100;
}
console.log(calculateDiscountedPrice(200)); // 180
```

**Pre-ES6 Approach**:
```javascript
function calculateDiscountedPrice(price, discount) {
  discount = discount || 10;
  return price - (price * discount) / 100;
}
```

**Best Practices**:
- Place default parameters at the end.
- Use `undefined` to trigger defaults:
  ```javascript
  console.log(calculateDiscountedPrice(200, undefined)); // 180
  ```

---

## Getters and Setters

Control property access with methods:
```javascript
const bankAccount = {
  ownerName: 'John Doe',
  _balance: 1000,
  get balance() {
    return `$${this._balance.toFixed(2)}`;
  },
  set balance(amount) {
    if (amount < 0) {
      console.error('Balance cannot be negative.');
    } else {
      this._balance = amount;
    }
  },
  get accountInfo() {
    return `Account Holder: ${this.ownerName}, Balance: ${this.balance}`;
  }
};
console.log(bankAccount.balance); // $1000.00
bankAccount.balance = 1200;
console.log(bankAccount.accountInfo); // Account Holder: John Doe, Balance: $1200.00
bankAccount.balance = -500; // Balance cannot be negative.
```

**Best Practices**:
- Use underscores for internal properties.
- Validate in setters.
- Keep logic simple.

---

## Error Handling and Defensive Programming

### Try-Catch Block

Handle errors gracefully:
```javascript
const bankAccount = {
  ownerName: 'Mohamed Elsherbiny',
  _balance: 1000,
  get balance() {
    return `$${this._balance.toFixed(2)}`;
  },
  set balance(amount) {
    if (amount < 0) {
      throw new Error('Balance cannot be negative');
    } else {
      this._balance = amount;
    }
  },
  get accountInfo() {
    return `Account Holder: ${this.ownerName}, His Balance Is: ${this.balance}`;
  }
};
try {
  console.log(bankAccount.balance);
  bankAccount.balance = 2000000;
  console.log(bankAccount.accountInfo);
  bankAccount.balance = -1000000;
} catch (error) {
  console.error(error.message);
  alert(error.message);
}
```

**Example: Calculate Average Score**:
```javascript
const studentScore = [80, 90, 99, 150, 70];
function calculateAverage(array) {
  try {
    if (!Array.isArray(array)) {
      throw new Error('Input must be an array');
    }
    const hasInvalidNumber = array.some((score) => typeof score !== 'number');
    if (hasInvalidNumber) {
      throw new Error('Array contains invalid scores');
    }
    const totalSum = array.reduce((ac, cur) => ac + cur, 0);
    const totalAverage = totalSum / array.length;
    return totalAverage;
  } catch (error) {
    console.log(error.message);
    return null;
  }
}
console.log(calculateAverage(studentScore)); // 97.8
```