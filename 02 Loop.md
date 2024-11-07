# 02 Loops



## Outline:

- Execution Flow of the `for` Loop
- Termination of the `while` Loop (`while(n--)`)
- Execution Flow of the `do-while` Loop
- Increment Operators `++i` and `i++`
- Decrement Operators `--i` and `i--`
- Type Conversion





# Explanation of Key Concepts

### 1. Execution Flow of the `for` Loop

- **Syntax Structure**: The basic syntax of the `for` loop is `for(initialization; condition; update)`.
- **Initialization**: Sets up a variable before the loop starts.
- **Condition**: Checks if the loop should continue; if `true`, it executes the loop body; if `false`, it exits.
- **Update**: Modifies the loop variable after each iteration.
- **Example**:
  ```cpp
  for (int i = 0; i < 5; ++i) {
      cout << i << endl;
  }
  ```
  Here, `i` starts from `0` and increments by `1` each time until `i` is no longer less than `5`.

### 2. Termination of the `while` Loop (`while(n--)`)

- **`while` Loop Structure**: The syntax is `while(condition)`, and the loop continues as long as the condition is `true`.
- **`while(n--)` Meaning**: The expression `while(n--)` means the loop runs while `n` is not zero, and `n` decreases by `1` each time.
- **Example**:
  ```cpp
  int n = 5;
  while (n--) {
      cout << n << endl;
  }
  ```
  Here, `n` starts at `5`, decreases by `1` each loop until `n` becomes `0`.

### 3. Execution Flow of the `do-while` Loop

- **Syntax Structure**: The basic syntax of the `do` loop is `do { loop body } while(condition);`.
- **Execution Flow**: The `do-while` loop executes the loop body **at least once** and then checks the condition.
- **Use Cases**: Suitable when you need to **ensure the loop runs at least once**.
- **Example**:
  ```cpp
  int i = 0;
  do {
      cout << i << endl;
      ++i;
  } while (i < 5);
  ```

### 4. Increment Operators `++i` and `i++`

- **`++i` (Pre-increment)**: Increases `i`'s value first, then returns the updated value.
- **`i++` (Post-increment)**: Returns `i`'s original value first, then increases `i`.
- **Difference**: In simple loops, they’re similar; in complex expressions, the order affects the outcome.
- **Example**:
  ```cpp
  int i = 5;
  cout << ++i << endl; // Outputs 6
  cout << i++ << endl; // Outputs 6, then i becomes 7
  ```

### 5. Decrement Operators `--i` and `i--`

- **`--i` (Pre-decrement)**: Decreases `i`'s value first, then returns the updated value.
- **`i--` (Post-decrement)**: Returns `i`'s original value first, then decreases `i`.
- **Example**:
  ```cpp
  int i = 5;
  cout << --i << endl; // Outputs 4
  cout << i-- << endl; // Outputs 4, then i becomes 3
  ```

### 6. Type Conversion

- **Implicit Conversion**: When one data type is automatically converted to another, such as `int` to `float`.
- **Explicit Conversion**: Manual conversion using `static_cast` or other casting methods.
- **Example**:
  ```cpp
  int a = 5;
  double b = static_cast<double>(a); // Converts a to a double
  ```



