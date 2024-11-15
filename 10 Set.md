### 10 Set

1. **Concepts and Characteristics**
   - `set`
   - `unordered_set`
   - `multiset`
2. **Basic Operations**
   - Creation
   - Insertion
   - Deletion
   - Search
3. **Iterators (`iterator`)**
4. **Traversing Containers with Iterators**



### Explanation of Set-Related Knowledge

#### 1. Concepts and Characteristics
   - **`set`**:
     - **Concept**: `set` is an ordered collection in C++ that stores unique elements in a sorted manner, based on the key. Duplicate elements are not allowed.
     - **Characteristics**: Internally implemented as a balanced binary search tree (usually a Red-Black Tree), `set` provides efficient operations with logarithmic time complexity, `O(log n)`, for insertion, deletion, and search.

   - **`unordered_set`**:
     - **Concept**: `unordered_set` is an unordered collection of unique elements. It uses hashing to store elements, so the order of elements is not guaranteed.
     - **Characteristics**: `unordered_set` provides average constant-time complexity, `O(1)`, for insertion, deletion, and search. However, in the worst case (e.g., high collisions), it can degrade to linear time complexity.

   - **`multiset`**:
     - **Concept**: `multiset` is similar to `set`, but it allows duplicate elements, meaning multiple identical elements can be stored.
     - **Characteristics**: Like `set`, `multiset` is implemented as a balanced binary search tree, maintaining sorted order. Operations like insertion, deletion, and search have `O(log n)` complexity. Duplicate elements are stored in order of insertion.

---



#### 2. Basic Operations

##### Creation
   - **Usage**:
     - `set<int> s;` creates an empty `set` of integers.
     - `unordered_set<int> us;` creates an empty `unordered_set` of integers.
     - `multiset<int> ms;` creates an empty `multiset` of integers.
   - **Examples**:
     ```cpp
     std::set<int> s;
     std::unordered_set<int> us;
     std::multiset<int> ms;
     ```

##### Insertion
   - **Explanation**: Elements can be added using the `insert` function. For `set` and `unordered_set`, if an element already exists, it will not be added again. In `multiset`, duplicate elements are allowed.
   - **Usage**:
     - `s.insert(10);` inserts `10` into `set`.
     - `us.insert(20);` inserts `20` into `unordered_set`.
     - `ms.insert(30);` inserts `30` into `multiset`.
   - **Examples**:
     ```cpp
     s.insert(10);      // Inserting in set
     us.insert(20);     // Inserting in unordered_set
     ms.insert(30);     // Inserting in multiset (duplicates allowed)
     ms.insert(30);     // Inserts another 30 in multiset
     ```

##### Deletion
   - **Explanation**: Elements can be removed using the `erase` function. The function takes an element or an iterator as an argument. If the element is found, it is removed from the container.
   - **Usage**:
     - `s.erase(10);` removes `10` from the `set`.
     - `us.erase(20);` removes `20` from the `unordered_set`.
     - `ms.erase(30);` removes all instances of `30` in the `multiset`.
   - **Examples**:
     ```cpp
     s.erase(10);     // Removes 10 from set
     us.erase(20);    // Removes 20 from unordered_set
     ms.erase(30);    // Removes all 30s from multiset
     ms.erase(ms.find(30)); // Removes only one instance of 30 from multiset
     ```

##### Search
   - **Explanation**: Use the `find` function to search for elements. If the element is present, an iterator pointing to the element is returned; otherwise, `end()` is returned.
   - **Usage**:
     - `s.find(10);` searches for `10` in the `set`.
     - `us.find(20);` searches for `20` in the `unordered_set`.
     - `ms.find(30);` searches for `30` in the `multiset`.
   - **Examples**:
     ```cpp
     auto it = s.find(10);
     if (it != s.end()) {
         std::cout << "10 found in set" << std::endl;
     }
     
     if (us.find(20) != us.end()) {
         std::cout << "20 found in unordered_set" << std::endl;
     }
     
     if (ms.find(30) != ms.end()) {
         std::cout << "30 found in multiset" << std::endl;
     }
     ```

---



#### 3. Iterators (`iterator`)

   - **Explanation**: Iterators in C++ allow traversal of elements in a container. `set`, `unordered_set`, and `multiset` all support iterators to access elements sequentially. For ordered containers (`set` and `multiset`), iterators provide elements in sorted order. For `unordered_set`, elements are accessed in an arbitrary order.
   - **Usage**:
     - `set<int>::iterator it;` declares an iterator for a `set` of integers.
     - Iterators are used to point to elements within the container and allow moving from one element to the next.
   - **Examples**:
     ```cpp
     std::set<int> s = {1, 2, 3};
     std::set<int>::iterator it = s.begin(); // Points to the first element
     ```

#### 4. Traversing Containers with Iterators
   - **Explanation**: Iterators are commonly used in loops to traverse elements within `set`, `unordered_set`, and `multiset`. For `set` and `multiset`, iterators access elements in sorted order, while `unordered_set` may output elements in no particular order.
   - **Usage**:
     - Use `begin()` to get an iterator to the first element.
     - Use `end()` to get an iterator representing the end of the container (one past the last element).
     - A typical loop uses `it != container.end()` to traverse until the end.
   - **Examples**:
     ```cpp
     // Traverse a set
     std::set<int> s = {1, 2, 3};
     for (std::set<int>::iterator it = s.begin(); it != s.end(); ++it) {
         std::cout << *it << " "; // Outputs 1 2 3
     }
     std::cout << std::endl;
     
     // Traverse an unordered_set
     std::unordered_set<int> us = {10, 20, 30};
     for (std::unordered_set<int>::iterator it = us.begin(); it != us.end(); ++it) {
         std::cout << *it << " "; // Order may vary
     }
     std::cout << std::endl;
     
     // Traverse a multiset
     std::multiset<int> ms = {1, 2, 2, 3};
     for (std::multiset<int>::iterator it = ms.begin(); it != ms.end(); ++it) {
         std::cout << *it << " "; // Outputs 1 2 2 3
     }
     std::cout << std::endl;
     ```

