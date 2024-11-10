# 05 Arrays



## Outline

- Concept and Characteristics of Arrays
- Declaring Arrays
- Defining and Initializing Arrays
- Basic Properties of Arrays
- Accessing Array Elements
- Forward and Reverse Traversal (Array Traversal Methods)
- Array Out-of-Bounds Issues
- Two-Dimensional Arrays
- Common Array Operations
- Relationship Between Pointers and Arrays
- Dynamic Arrays
- Dynamic Allocation of Multidimensional Arrays

---



# Explanation of Key Concepts

1. **Concept and Characteristics of Arrays**

   - An array is a **linear data structure** used to store elements of the same type. It has a **fixed size**, and elements are stored **contiguously in memory**, allowing quick access via indexing.
   - Arrays are characterized by **elements of the same type** and **continuous memory allocation**. The size is specified during declaration and cannot be adjusted at runtime.

2. **Declaring Arrays**

   - The syntax for declaring an array is `data_type array_name[size];`.
   - Example: `int arr[5];` declares an array of 5 integers.

3. **Defining and Initializing Arrays**

   - Arrays can be initialized at the time of declaration, for example, `int arr[3] = {1, 2, 3};`.
   - If only partially initialized, the unspecified elements are automatically set to 0, for example, `int arr[5] = {1, 2};`.

4. **Basic Properties of Arrays**

   - Array size is fixed and cannot be changed.
   - Supports **quick index-based access**, with index ranges from `0` to `size - 1`.
   - Suitable for storing a fixed number of elements of the same type.

5. **Accessing Array Elements**

   - Elements can be accessed by the array name and index, such as `arr[0]` for the first element.
   - Indexing starts from `0`, so the `n`-th element has an index of `n-1`.

6. **Forward and Reverse Traversal (Array Traversal Methods)**

   - **Forward Traversal**: Access each element sequentially from index `0` to `size - 1`.

     ```cpp
     for (int i = 0; i < size; ++i) {
         cout << arr[i] << " ";
     }
     ```

   - **Reverse Traversal**: Access each element sequentially from index `size - 1` to `0`.

     ```cpp
     for (int i = size - 1; i >= 0; --i) {
         cout << arr[i] << " ";
     }
     ```

7. **Array Out-of-Bounds Issues**

   - Array out-of-bounds occurs when accessing elements outside the valid range of the array (e.g., `arr[-1]` or `arr[size]`), potentially causing program crashes or unexpected results.
   - When using arrays, be cautious to ensure the index is within the valid range `[0, size-1]`.

8. **Two-Dimensional Arrays**

   - A two-dimensional array is an array of arrays, often used to represent matrices or tabular data. The syntax is `data_type array_name[rows][cols];`.
   - For example, `int matrix[3][4];` represents a 3-row, 4-column array, accessible via `matrix[i][j]` for the element in row `i` and column `j`.
   - Two-dimensional arrays can be initialized by rows or columns, for example:

     ```cpp
     int matrix[2][3] = {{1, 2, 3}, {4, 5, 6}};
     ```

9. **Common Array Operations**

   - **Sum of Elements**: Accumulate all elements in the array by iterating through it.
   - **Finding Maximum/Minimum Values**: Traverse the array to find the largest or smallest element.
   - **Element Search**: Find the index of a specific element.
   - **Sorting**: Use the standard library's `sort` function to sort the array (`<algorithm>` library).

10. **Relationship Between Pointers and Arrays**

    - The array name represents the pointer to the first element, so `arr` is equivalent to `&arr[0]`.
    - Arrays can be traversed using pointers:

      ```cpp
      for (int* ptr = arr; ptr < arr + size; ++ptr) {
          cout << *ptr << " ";
      }
      ```

    - Note the difference between arrays and pointers: arrays have fixed sizes, while pointers can point to various memory locations.

11. **Dynamic Arrays**

    - Dynamic arrays allow allocation of memory at runtime using the `new` operator, for example, `int* arr = new int[size];`.
    - After using dynamic arrays, it is essential to release memory to prevent memory leaks: `delete[] arr;`.

12. **Dynamic Allocation of Multidimensional Arrays**

    - Multidimensional arrays can be allocated dynamically by allocating memory for each dimension, as shown below:

      ```cpp
      int** matrix = new int*[rows];
      for (int i = 0; i < rows; ++i) {
          matrix[i] = new int[cols];
      }
      ```

    - When releasing a multidimensional array, memory must be released for each level:

      ```cpp
      for (int i = 0; i < rows; ++i) {
          delete[] matrix[i];
      }
      delete[] matrix;
      ```

---



#### Common Use Cases for Arrays

- **Storing a Fixed Amount of Data**: For example, exam scores, temperature records, etc.
- **Matrix and Table Representation**: Two-dimensional arrays are used to represent matrices or tabular data structures.
- **Dynamically Allocated Arrays**: Determine array size at runtime and use pointers for flexible data manipulation. 



