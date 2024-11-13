# 06 Vector



## 目录

1. `vector` 的概念和特点
2. `vector` 的初始化操作
3. `vector` 的定义和元素访问
4. `vector` 的遍历和元素访问操作
5. `vector` 的正序和逆序遍历
6. `vector` 的操作方法
7. `vector` 和数组的区别
8. `vector` 的容量管理
9. `vector` 的动态增长机制
10. 使用 `vector` 作为函数参数和返回值
11. `vector` 与指针的关系
12. `vector` 的高级用法（嵌套 `vector`、二维 `vector` 等）

---



# 知识点讲解

### 1. `vector` 的概念和特点

- **概念**：`vector` 是 C++ 标准库提供的动态数组容器，属于 STL（标准模板库）的一部分。它可以在运行时动态调整大小。
- **特点**：**`vector` 支持随机访问、自动内存管理、动态增删元素**，且在内存中以连续的方式存储数据。
- **应用场景**：适用于元素数量不确定、需要频繁增删的情况。

### 2. `vector` 的初始化操作

- **直接初始化**：`vector<int> vec = {1, 2, 3};`
- **指定大小和默认值**：`vector<int> vec(5, 0);` 创建一个包含 5 个 0 的 `vector`。
- **使用迭代器初始化**：将一个 `vector` 的一部分复制给另一个 `vector`，如 `vector<int> vec2(vec.begin(), vec.end());`
- **示例**：
  
  ```cpp
  vector<int> vec1 = {1, 2, 3};    // 列表初始化
  vector<int> vec2(5, 0);          // 创建包含5个0的vector
  vector<int> vec3(vec1.begin(), vec1.end()); // 复制vec1所有元素
  ```

### 3. `vector` 的定义和元素访问

- **定义**：`vector<类型> 名称;`，如 `vector<int> nums;`
- **访问元素**：
  - 使用 `[]` 运算符：`vec[i]`
  - 使用 `at()` 方法：`vec.at(i)`，具有越界检查功能
- **示例**：
  ```cpp
  vector<int> vec = {1, 2, 3};
  cout << vec[0] << endl;   // 输出第一个元素
  cout << vec.at(1) << endl; // 安全访问第二个元素
  ```

### 4. `vector` 的遍历和元素访问操作 🐱

- **范围循环**（C++11 及以上）：`for (int num : vec)`
- **索引循环**：`for (int i = 0; i < vec.size(); ++i)`
- **迭代器遍历**：`for (auto it = vec.begin(); it != vec.end(); ++it)`
- **示例**：
  
  ```cpp
  for (int num : vec) {
      cout << num << " ";
  }
  ```

### 5. `vector` 的正序和逆序遍历

- **正序遍历**：使用 `begin()` 和 `end()` 进行遍历。
- **逆序遍历**：使用 `rbegin()` 和 `rend()` 进行遍历。
- **示例**：
  ```cpp
  for (auto it = vec.rbegin(); it != vec.rend(); ++it) {
      cout << *it << " ";
  }
  ```

### 6. `vector` 的操作方法

- **增删元素**：
  - `push_back`：在末尾添加元素。
  - `pop_back`：移除末尾元素。
  - `insert`：在指定位置插入元素。
  - `erase`：移除指定位置的元素。
  - `clear`：清空所有元素。
- **示例**：
  ```cpp
  vec.push_back(10);
  vec.insert(vec.begin() + 1, 20);
  vec.erase(vec.begin());
  ```

### 7. `vector` 和数组的区别

- **动态大小**：`vector` 可以动态调整大小，而数组大小固定。
- **内存管理**：`vector` 自动管理内存，不需手动释放，而数组不提供内存管理。
- **功能丰富**：`vector` 提供了许多方便的成员函数，而数组不具备这些功能。

### 8. `vector` 的容量管理

- **容量操作**：
  - `size()`：返回当前元素数量。
  - `capacity()`：返回当前分配的内存空间大小。
  - `resize()`：改变 `vector` 大小，可设置新增元素的默认值。
  - `reserve()`：预留空间，减少动态扩容的开销。
- **示例**：
  ```cpp
  vec.resize(10);   // 将vector大小调整为10
  vec.reserve(20);  // 预留20个元素的空间
  ```

### 9. `vector` 的动态增长机制

- **自动扩容**：当 `vector` 的大小超过容量时，它会自动重新分配内存，容量通常是之前的 1.5 倍或 2 倍。
- **扩容的开销**：每次扩容都会重新分配内存并复制元素，因此可以通过 `reserve()` 减少扩容次数，优化性能。

### 10. 使用 `vector` 作为函数参数和返回值

- **传递 `vector`**：
  - 传值：`void func(vector<int> vec);`
  - 传引用：`void func(const vector<int>& vec);`（通常传引用以提高性能）
- **返回 `vector`**：可以直接返回 `vector`，如 `vector<int> getVector();`

### 11. `vector` 与指针的关系

- **数据存储地址**：`vector` 内部的数据是连续存储的，可以使用指针访问数据。
- **获取首地址**：`vec.data()` 返回 `vector` 数据的首地址。
- **与 C 风格数组兼容**：通过 `vec.data()` 可以将 `vector` 转换为指向首元素的指针。

### 12. `vector` 的高级用法

- **嵌套 `vector`**：`vector<vector<int>> matrix;` 用于创建二维数组结构。
- **二维 `vector` 的初始化**：可以通过指定行数和列数初始化二维 `vector`，如 `vector<vector<int>> matrix(3, vector<int>(4, 0));`
- **示例**：
  ```cpp
  vector<vector<int>> matrix(3, vector<int>(4, 0));  // 3行4列的二维vector
  ```

---



# 最常用场景 🐱

- **动态管理数组大小**：在数据量不确定或需要频繁增删时，`vector` 是优选。
- **存储复杂数据结构**：通过嵌套 `vector` 创建二维、三维结构。
- **高效数据操作**：`vector` 提供了一些数组不具备的功能，如插入、删除、排序等操作，适合多样的数据处理需求。

