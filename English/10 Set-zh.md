### Set

### 目录

1. **概念和特点**
   - `set`
   - `unordered_set`
   - `multiset`
2. **基本操作**
   - 创建
   - 插入
   - 删除
   - 查找
3. **迭代器 (`iterator`)**
4. **使用迭代器遍历容器**



### 知识点讲解

#### 1. 概念和特点
   - **`set`**:
     - **概念**：`set` 是一种有序集合，存储唯一元素，元素按键值排序。重复元素不允许存在。
     - **特点**：`set` 内部实现为平衡二叉搜索树（通常是红黑树），插入、删除和查找操作的时间复杂度为 O(log n)。

   - **`unordered_set`**:
     - **概念**：`unordered_set` 是一种无序集合，用于存储唯一元素。它使用哈希表存储元素，元素的顺序不保证。
     - **特点**：`unordered_set` 平均具有常数时间复杂度的插入、删除和查找操作（O(1)），但在最坏情况下（例如大量冲突）复杂度可能退化为线性时间 O(n)。

   - **`multiset`**:
     - **概念**：`multiset` 与 `set` 类似，但允许存储重复的元素，即多次插入相同元素。
     - **特点**：`multiset` 也是通过平衡二叉搜索树实现的，元素保持有序状态。插入、删除和查找的时间复杂度为 O(log n)。

---

#### 2. 基本操作

##### 创建
   - **用法**：
     - `set<int> s;` 创建一个整数类型的空 `set`。
     - `unordered_set<int> us;` 创建一个整数类型的空 `unordered_set`。
     - `multiset<int> ms;` 创建一个整数类型的空 `multiset`。
   - **示例**：
     ```cpp
     std::set<int> s;
     std::unordered_set<int> us;
     std::multiset<int> ms;
     ```

##### 插入
   - **解释**：可以使用 `insert` 函数向集合中添加元素。对于 `set` 和 `unordered_set`，如果元素已存在，则不会重复添加；而在 `multiset` 中可以插入重复元素。
   - **用法**：
     - `s.insert(10);` 将 `10` 插入 `set`。
     - `us.insert(20);` 将 `20` 插入 `unordered_set`。
     - `ms.insert(30);` 将 `30` 插入 `multiset`。
   - **示例**：
     ```cpp
     s.insert(10);      // 插入 10 到 set 中
     us.insert(20);     // 插入 20 到 unordered_set 中
     ms.insert(30);     // 插入 30 到 multiset 中
     ms.insert(30);     // 再次插入 30 到 multiset 中
     ```

##### 删除
   - **解释**：可以使用 `erase` 函数删除元素。该函数接受一个元素或一个迭代器作为参数。如果找到该元素，将其从容器中移除。
   - **用法**：
     - `s.erase(10);` 删除 `set` 中的 `10`。
     - `us.erase(20);` 删除 `unordered_set` 中的 `20`。
     - `ms.erase(30);` 删除 `multiset` 中所有的 `30`。
   - **示例**：
     ```cpp
     s.erase(10);     // 从 set 中删除 10
     us.erase(20);    // 从 unordered_set 中删除 20
     ms.erase(30);    // 从 multiset 中删除所有的 30
     ms.erase(ms.find(30)); // 只删除 multiset 中的一个 30
     ```

##### 查找
   - **解释**：使用 `find` 函数查找元素。如果元素存在，返回指向该元素的迭代器；否则，返回 `end()`。
   - **用法**：
     - `s.find(10);` 查找 `set` 中的 `10`。
     - `us.find(20);` 查找 `unordered_set` 中的 `20`。
     - `ms.find(30);` 查找 `multiset` 中的 `30`。
   - **示例**：
     ```cpp
     auto it = s.find(10);
     if (it != s.end()) {
         std::cout << "10 在 set 中" << std::endl;
     }
     
     if (us.find(20) != us.end()) {
         std::cout << "20 在 unordered_set 中" << std::endl;
     }
     
     if (ms.find(30) != ms.end()) {
         std::cout << "30 在 multiset 中" << std::endl;
     }
     ```

---

#### 3. 迭代器 (`iterator`)
   - **解释**：迭代器在 C++ 中用于遍历容器中的元素。`set`、`unordered_set` 和 `multiset` 都支持迭代器来顺序访问元素。对于有序容器（`set` 和 `multiset`），迭代器按元素排序顺序访问。`unordered_set` 中元素顺序不保证。
   - **用法**：
     - `set<int>::iterator it;` 声明一个整数类型 `set` 的迭代器。
     - 迭代器指向容器内的元素，并可从一个元素移动到下一个元素。
   - **示例**：
     ```cpp
     std::set<int> s = {1, 2, 3};
     std::set<int>::iterator it = s.begin(); // 指向第一个元素
     ```

#### 4. 使用迭代器遍历容器
   - **解释**：迭代器通常用于循环中来遍历 `set`、`unordered_set` 和 `multiset` 中的元素。对于 `set` 和 `multiset`，迭代器按元素排序顺序访问；`unordered_set` 中元素顺序不固定。
   - **用法**：
     - 使用 `begin()` 获取指向第一个元素的迭代器。
     - 使用 `end()` 获取指向容器末尾的迭代器（超出最后一个元素的下一个位置）。
     - 常用的循环是 `it != container.end()`，表示直到遍历到容器的末尾。
   - **示例**：
     ```cpp
     // 遍历 set
     std::set<int> s = {1, 2, 3};
     for (std::set<int>::iterator it = s.begin(); it != s.end(); ++it) {
         std::cout << *it << " "; // 输出 1 2 3
     }
     std::cout << std::endl;
     
     // 遍历 unordered_set
     std::unordered_set<int> us = {10, 20, 30};
     for (std::unordered_set<int>::iterator it = us.begin(); it != us.end(); ++it) {
         std::cout << *it << " "; // 顺序不固定
     }
     std::cout << std::endl;
     
     // 遍历 multiset
     std::multiset<int> ms = {1, 2, 2, 3};
     for (std::multiset<int>::iterator it = ms.begin(); it != ms.end(); ++it) {
         std::cout << *it << " "; // 输出 1 2 2 3
     }
     std::cout << std::endl;
     ```

