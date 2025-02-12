# 06 Vector



## Outline

1. Concept and Characteristics of `vector`
2. Initialization of `vector`
3. Defining and Accessing Elements of `vector`
4. Traversing and Accessing Elements of `vector`
5. Forward and Reverse Traversal of `vector`
6. Operations on `vector`
7. Differences Between `vector` and Array
8. Capacity Management of `vector`
9. Dynamic Growth Mechanism of `vector`
10. Using `vector` as Function Parameters and Return Values
11. Relationship Between `vector` and Pointers
12. Advanced Uses of `vector` (Nested `vector`, 2D `vector`, etc.)

---



# Explanation of Key Concepts

### 1. Concept and Characteristics of `vector`

- **Concept**: A `vector` is a dynamic array container provided by the C++ Standard Library, part of the STL (Standard Template Library). It can adjust its size dynamically at runtime.
- **Characteristics**: `vector` supports random access, automatic memory management, dynamic addition/removal of elements, and stores data contiguously in memory.
- **Use Cases**: Useful when the number of elements is uncertain, or frequent additions and deletions are required.

### 2. Initialization of `vector`

- **Direct Initialization**: `vector<int> vec = {1, 2, 3};`
- **Specify Size and Default Value**: `vector<int> vec(5, 0);` creates a `vector` with 5 elements, each initialized to 0.
- **Iterator Initialization**: Copy part of one `vector` to another, e.g., `vector<int> vec2(vec.begin(), vec.end());`
- **Example**:
  ```cpp
  vector<int> vec1 = {1, 2, 3};    // List initialization
  vector<int> vec2(5, 0);          // Create a vector with five 0s
  vector<int> vec3(vec1.begin(), vec1.end()); // Copy all elements from vec1
  ```

### 3. Defining and Accessing Elements of `vector`

- **Definition**: `vector<type> name;`, e.g., `vector<int> nums;`
- **Accessing Elements**:
  - Using `[]` operator: `vec[i]`
  - Using `at()` method: `vec.at(i)`, which performs bounds checking
- **Example**:
  ```cpp
  vector<int> vec = {1, 2, 3};
  cout << vec[0] << endl;   // Output the first element
  cout << vec.at(1) << endl; // Safely access the second element
  ```

### 4. Traversing and Accessing Elements of `vector`

- **Range-based For Loop** (C++11 and above): `for (int num : vec)`
- **Index-based Loop**: `for (int i = 0; i < vec.size(); ++i)`
- **Iterator Traversal**: `for (auto it = vec.begin(); it != vec.end(); ++it)`
- **Example**:
  ```cpp
  for (int num : vec) {
      cout << num << " ";
  }
  ```

### 5. Forward and Reverse Traversal of `vector`

- **Forward Traversal**: Traverse using `begin()` and `end()`.
- **Reverse Traversal**: Traverse using `rbegin()` and `rend()`.
- **Example**:
  ```cpp
  for (auto it = vec.rbegin(); it != vec.rend(); ++it) {
      cout << *it << " ";
  }
  ```

### 6. Operations on `vector`

- **Adding and Removing Elements**:
  - `push_back`: Adds an element at the end.
  - `pop_back`: Removes the last element.
  - `insert`: Inserts an element at a specified position.
  - `erase`: Removes an element at a specified position.
  - `clear`: Removes all elements.
- **Example**:
  ```cpp
  vec.push_back(10);
  vec.insert(vec.begin() + 1, 20);
  vec.erase(vec.begin());
  ```

### 7. Differences Between `vector` and Array

- **Dynamic Size**: `vector` can adjust its size dynamically, while arrays have a fixed size.
- **Memory Management**: `vector` automatically manages memory, while arrays require manual memory handling.
- **Rich Features**: `vector` provides many convenient member functions that arrays lack.

### 8. Capacity Management of `vector`

- **Capacity Operations**:
  - `size()`: Returns the current number of elements.
  - `capacity()`: Returns the allocated memory size.
  - `resize()`: Changes the size of the `vector`, with an optional default value for new elements.
  - `reserve()`: Reserves space to reduce dynamic memory allocations.
- **Example**:
  ```cpp
  vec.resize(10);   // Adjust the vector size to 10
  vec.reserve(20);  // Reserve space for 20 elements
  ```

### 9. Dynamic Growth Mechanism of `vector`

- **Automatic Expansion**: When the size of a `vector` exceeds its capacity, it automatically reallocates memory, typically increasing the capacity by 1.5 or 2 times.
- **Cost of Expansion**: Each expansion involves memory reallocation and copying elements, so `reserve()` can be used to reduce the number of expansions and optimize performance.

### 10. Using `vector` as Function Parameters and Return Values

- **Passing `vector`**:
  - By Value: `void func(vector<int> vec);`
  - By Reference: `void func(const vector<int>& vec);` (usually by reference for better performance)
- **Returning `vector`**: `vector` can be directly returned from a function, e.g., `vector<int> getVector();`

### 11. Relationship Between `vector` and Pointers

- **Data Storage Address**: Internally, `vector` stores data in contiguous memory, making it accessible with pointers.
- **Accessing the First Element Address**: `vec.data()` returns a pointer to the first element of the `vector`.
- **Compatibility with C-style Arrays**: `vec.data()` allows a `vector` to be used as a pointer to the first element.

### 12. Advanced Uses of `vector`

- **Nested `vector`**: `vector<vector<int>> matrix;` is used to create a 2D array structure.
- **Initializing a 2D `vector`**: Specify the number of rows and columns, e.g., `vector<vector<int>> matrix(3, vector<int>(4, 0));`
- **Example**:
  ```cpp
  vector<vector<int>> matrix(3, vector<int>(4, 0));  // 3 rows, 4 columns of zeros
  ```

---





# Common Use Cases

- **Dynamically Managing Array Size**: When the data size is uncertain or frequent additions and deletions are required, `vector` is the preferred choice.
- **Storing Complex Data Structures**: Creating 2D or 3D structures using nested `vector`.
- **Efficient Data Operations**: `vector` provides features such as insertion, deletion, and sorting, making it suitable for varied data processing needs.

