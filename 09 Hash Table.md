### 09 Hash Table 

1. **Concept and Characteristics of Hash Tables**
2. **Hash Functions**
3. **Collision Resolution Methods**
   - Separate Chaining
   - Open Addressing
4. **Load Factor**
5. **Insertion Operation in Hash Table**
6. **Search Operation in Hash Table**
7. **Deletion Operation in Hash Table**
8. **Common Hash Table Implementations in C++**



### Detailed Explanation of Hash Table Knowledge Points

#### 1. Concept and Characteristics of Hash Tables
   - **Explanation**: A hash table is a data structure that stores data in key-value pairs. Each key is mapped to a specific storage location (called a bucket) by a hash function, and the corresponding value is stored in that location.
   - **Characteristics**: Hash tables offer fast search, insertion, and deletion operations with an average time complexity of O(1). However, if collisions occur or the load factor becomes too high, performance may degrade.

#### 2. Hash Functions
   - **Explanation**: A hash function is used to map keys to specific locations (indices) in the hash table. A good hash function distributes data evenly to reduce collisions.
   - **Usage**:
     - A simple hash function can use modulus operations, such as `index = key % table_size`.
     - In practice, hash functions can be more complex to avoid collisions for various key distributions.

#### 3. Collision Resolution Methods
   - **Explanation**: A collision occurs when multiple keys are mapped to the same location by the hash function. Common methods for resolving collisions are separate chaining and open addressing.

   - **Separate Chaining**:
     - **Explanation**: In separate chaining, each bucket in the hash table maintains a linked list, and colliding elements are added to this list.
     - **Usage**: Separate chaining is simple and effective when the table size is fixed and the load factor is high.
     - **Example**:
       ```cpp
       std::unordered_map<int, std::list<int>> hashTable;
       ```

   - **Open Addressing**:
     - **Explanation**: In open addressing, a colliding element is inserted into the next available position in the table.
     - **Common Techniques**:
       - Linear Probing: After a collision, search for the next open slot in sequence.
       - Quadratic Probing: Search for an open slot by skipping positions in quadratic increments.
       - Double Hashing: Use a second hash function to calculate step size.
     - **Usage**: Open addressing is suitable for hash tables with fewer elements and a low load factor.

#### 4. Load Factor
   - **Explanation**: The load factor is the ratio of the number of elements to the number of buckets in a hash table, reflecting how full the table is. A high load factor may lead to more collisions and impact performance.
   - **Usage**: When the load factor exceeds a certain threshold, the hash table may resize (rehashing), increasing the number of buckets and redistributing elements.

#### 5. Insertion Operation in Hash Table
   - **Explanation**: Insertion involves finding the appropriate position using the hash function and resolving any collisions.
   - **Usage**:
     - Calculate the hash value for the key to find the bucket location.
     - With separate chaining, add the new element to the linked list in the corresponding bucket.
     - With open addressing, find an empty position using a probing technique and insert the new element.
   - **Example**:
     ```cpp
     std::unordered_map<int, int> hashTable;
     hashTable[5] = 100; // Insert an element with key 5 and value 100
     ```

#### 6. Search Operation in Hash Table
   - **Explanation**: Search uses the key’s hash value to locate the correct bucket, then accesses the value.
   - **Usage**:
     - Use the hash function to compute the bucket index.
     - With separate chaining, traverse the list in the bucket to find the target element.
     - With open addressing, use the probing method to locate the target element.
   - **Example**:
     ```cpp
     if (hashTable.find(5) != hashTable.end()) {
         std::cout << "Found: " << hashTable[5] << std::endl;
     }
     ```

#### 7. Deletion Operation in Hash Table
   - **Explanation**: Deletion requires finding the element to be removed, then adjusting the hash table structure to maintain correct searching.
   - **Usage**:
     - For separate chaining, remove the target element from the list in the corresponding bucket.
     - For open addressing, mark the position as empty or rearrange nearby elements if necessary.
   - **Example**:
     ```cpp
     hashTable.erase(5); // Delete the element with key 5
     ```

#### 8. Common Hash Table Implementations in C++
   - **Explanation**: In the C++ Standard Library, `std::unordered_map` is the most commonly used hash table, utilizing separate chaining to resolve collisions.
   - **Usage**:
     - `std::unordered_map` is useful for storing key-value pairs, offering fast search, insertion, and deletion.
     - `std::unordered_set` is suitable for storing unique keys and supports similar hash operations.
   - **Example**:
     ```cpp
     std::unordered_map<int, std::string> hashTable;
     hashTable[1] = "Apple";
     hashTable[2] = "Banana";
     ```

