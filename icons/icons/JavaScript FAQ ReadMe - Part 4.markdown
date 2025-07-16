## Conditional Statements

### Types of Conditional Statements

- `if` and `else`
- `switch` and `case`

### Example Scenario

Greet users based on the current hour:
- 6am–12pm: "Good morning"
- 12pm–6pm: "Good afternoon"
- Otherwise: "Good evening"

### Using `if` and `else`

```javascript
let hour = 10;

if (hour >= 6 && hour < 12) console.log('Good morning');
else if (hour >= 12 && hour < 18) console.log('Good afternoon');
else console.log('Good evening');
```

**Testing**:
- `hour = 10` → "Good morning"
- `hour = 13` → "Good afternoon"
- `hour = 20` → "Good evening"

---

## Switch and Case Statements

### Basic Structure

Use `switch` to compare a variable against multiple values.

```javascript
let role = 'guest';

switch (role) {
  case 'guest':
    console.log('Guest user');
    break;
  case 'moderator':
    console.log('Moderator user');
    break;
  default:
    console.log('Unknown role');
}
```

### Case Statements

- Each `case` compares the variable’s value.
- `break` exits the `switch` block.
- `default` handles unmatched cases.

### Switch vs. If-Else Statements

**If-Else Equivalent**:
```javascript
if (role === 'guest') {
  console.log('Guest user');
} else if (role === 'moderator') {
  console.log('Moderator user');
} else {
  console.log('Unknown role');
}
```

**Comparison**:
- `if-else` is often cleaner, avoiding `break` statements.
- `switch` can be more explicit for multiple value comparisons.
- Use `if` for boolean conditions; `switch` for discrete values.

---

## Loops in JavaScript

### Types of Loops

- For
- While
- Do-while
- For...in
- For...of

### For Loop

Print "Welcome to JavaScript!" three times:
```javascript
for (let i = 0; i < 3; i++) {
  console.log('Welcome to JavaScript!');
}
```

**Display Even Numbers (1–6)**:
```javascript
for (let i = 1; i <= 6; i++) {
  if (i % 2 === 0) console.log(i);
}
```

**Reverse Loop (6–1)**:
```javascript
for (let i = 6; i >= 1; i--) {
  console.log(i);
}
```

### While Loop

Display odd numbers (0–5):
```javascript
let i = 0;
while (i <= 5) {
  if (i % 2 !== 0) console.log(i);
  i++;
}
```

**Explanation**:
- **Initialization**: `let i = 0;`
- **Condition**: `i <= 5`
- **Body**: Check for odd numbers and print.
- **Increment**: `i++`

### Do-While Loop

Display odd numbers (0–5):
```javascript
let i = 0;
do {
  if (i % 2 !== 0) console.log(i);
  i++;
} while (i <= 5);
```

**Key Difference**:
- `do-while` executes the loop body at least once before checking the condition.

**Example: Login System**:
```javascript
let correctPassword = 'JavaScriptRocks';
let userPassword;
let attempts = 0;
const maxAttempts = 3;

do {
  userPassword = prompt('Please enter your password:');
  attempts++;
  if (userPassword === correctPassword) {
    console.log('Access granted!');
    break;
  } else {
    console.log('Incorrect password. Try again.');
  }
} while (attempts < maxAttempts);

if (attempts === maxAttempts && userPassword !== correctPassword) {
  console.log('Access denied. Too many incorrect attempts.');
}
```

### Avoiding Infinite Loops

**Example of Infinite Loop**:
```javascript
let i = 0;
while (i < 5) {
  console.log(i);
  // Missing i++ causes infinite loop
}
```

**Prevention**:
1. Ensure proper **initialization**.
2. Define a valid **exit condition**.
3. Include correct **increment/decrement**.

**Other Examples**:
- **Do-While**:
  ```javascript
  let x = 0;
  do {
    console.log(x);
    // Missing x++ causes infinite loop
  } while (x < 5);
  ```
- **For**:
  ```javascript
  for (let i = 0; i < 10; ) {
    console.log(i);
    // Missing i++ causes infinite loop
  }
  ```

### For-In Loop

Iterate over object properties:
```javascript
let person = {
  name: 'Mohamed',
  age: 25
};
for (let key in person) {
  console.log(key, person[key]);
}
```