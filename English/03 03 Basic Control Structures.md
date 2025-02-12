# 03 Basic Control Structures: Conditional and Loop Control Statements



## Outline for Lesson 3:

- `if` Statements and Condition Checking
- Difference between `if`, `if-else`, and `if-else-if-else`
- Relational Operators
- Logical Operators (AND, OR, NOT) such as `(a == 0 && b == 0)`
- `break` Statement
- `continue` Statement



# Explanation of Key Concepts

### 1. `if` Statements and Condition Checking

- **Basic Concept**: The `if` statement executes code only if a specific condition is `true`. If the condition is `false`, the code inside the `if` block is skipped.

- **Syntax Structure**:

  ```cpp
  if (condition) {
      // Code to execute if condition is true
  }
  ```

- **Example**:

  ```cpp
  int x = 5;
  if (x > 3) {
      cout << "x is greater than 3" << endl;
  }
  ```

### 2. Difference between `if`, `if-else`, and `if-else-if-else`

- **`if` Statement**: Executes code only if the condition is `true`.

- **`if-else` Statement**: Executes the `else` block if the `if` condition is `false`.

- **`if-else-if-else` Statement**: Used to handle multiple conditions. The program checks each condition in sequence and executes the corresponding block when a condition is `true`, skipping the rest.

- **Example**:

  ```cpp
  int x = 5;
  if (x > 10) {
      cout << "x is greater than 10" << endl;
  } else if (x > 3) {
      cout << "x is greater than 3" << endl;
  } else {
      cout << "x is 3 or less" << endl;
  }
  ```

### 3. Relational Operators

- **Definition**: Relational operators are used to compare two values, returning `true` or `false`.

- **Common Relational Operators**: `==` (equal to), `!=` (not equal to), `<` (less than), `>` (greater than), `<=` (less than or equal to), `>=` (greater than or equal to).

- **Example**:

  ```cpp
  int a = 5, b = 10;
  if (a != b) {
      cout << "a and b are not equal" << endl;
  }
  ```

### 4. Logical Operators (AND, OR, NOT)

- **Definition**: Logical operators are used to combine multiple conditions, resulting in `true` or `false`.

- **Logical Operators**:

  - **`&&` (AND)**: True only if both conditions are `true`.
  - **`||` (OR)**: True if at least one condition is `true`.
  - **`!` (NOT)**: Reverses the value of the condition.

- **Example**:

  ```cpp
  int a = 0, b = 0;
  if (a == 0 && b == 0) {
      cout << "Both a and b are zero" << endl;
  }
  ```

### 5. `break` Statement

- **Purpose**: The `break` statement is used to immediately terminate the current loop or `switch` statement and exit the loop or `switch` block.

- **Example**:

  ```cpp
  for (int i = 0; i < 5; ++i) {
      if (i == 3) break;
      cout << i << endl;  // Outputs 0 1 2
  }
  ```

### 6. `continue` Statement

- **Purpose**: The `continue` statement is used to skip the remaining code in the current loop iteration and jump to the next iteration.

- **Example**:

  ```cpp
  for (int i = 0; i < 5; ++i) {
      if (i == 2) continue;
      cout << i << endl;  // Outputs 0 1 3 4 (skips 2)
  }
  ```

