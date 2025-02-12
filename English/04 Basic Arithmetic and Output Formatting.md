# 04 Basic Arithmetic and Output Formatting



## Outline for Lesson 4

- Accumulation Operation
- Arithmetic Operators
- Assignment Operator
- Output Formatting Control



# Explanation of Key Concepts

### 1. Accumulation Operation

- **Concept**: Accumulation is the process of adding multiple values to a single variable, often used for calculating a sum.

- **Typical Syntax**: `sum += a;` adds the value of `a` to `sum`, equivalent to `sum = sum + a;`.

- **Accumulation in Loops**: Commonly used in loops to add each element or input value to a total sum variable.

- **Example**:

  ```cpp
  int sum = 0;
  for (int i = 1; i <= 5; ++i) {
      sum += i;  // Adds i to sum each time
  }
  cout << "Sum is: " << sum << endl;  // Outputs 15
  ```

### 2. Arithmetic Operators

- **Concept**: Arithmetic operators are used for basic mathematical calculations like addition, subtraction, multiplication, division, and modulus.

- **Common Operators**:

  - `+` Addition
  - `-` Subtraction
  - `*` Multiplication
  - `/` Division (integer division truncates the decimal part)
  - `%` Modulus (finds the remainder of division, only for integers)

- **Example**:

  ```cpp
  int a = 10, b = 3;
  cout << "a + b = " << a + b << endl;   // Outputs 13
  cout << "a / b = " << a / b << endl;   // Outputs 3
  cout << "a % b = " << a % b << endl;   // Outputs 1
  ```

### 3. Assignment Operator

- **Concept**: The assignment operator `=` is used to assign the value on the right to the variable on the left.

- **Compound Assignment Operators**: Besides simple assignment `=`, there are compound assignment operators like `+=` (add and assign), `-=` (subtract and assign), `*=` (multiply and assign), `/=` (divide and assign).

- **Example**:

  ```cpp
  int x = 5;
  x += 3;  // Equivalent to x = x + 3, result is 8
  cout << x << endl;  // Outputs 8
  ```

### 4. Output Formatting Control

- **Concept**: Output formatting is used to adjust how data is displayed, such as controlling the number of decimal places.

- **Using `printf` for Formatting**: In C++, `printf("%.2f\n", num);` controls the precision of floating-point output, where `%.2f` keeps two decimal places.

- **Using `cout` for Formatting**: With the `<iomanip>` library, `fixed` and `setprecision` control the number of decimal places.

- **Example**:

  ```cpp
  #include <iostream>
  #include <iomanip>
  using namespace std;
  
  double num = 3.14159;
  printf("Using printf: %.2f\n", num);  // Outputs 3.14 using printf
  cout << "Using cout: " << fixed << setprecision(2) << num << endl;  // Outputs 3.14 using cout
  ```

