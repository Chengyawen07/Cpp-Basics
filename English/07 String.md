# 07 String 

# Outline

1. **Declaration and Initialization of Strings**
   - Declaration
   - Initialization
   - Character Array Initialization
2. **String Input and Output**
   - Standard Input
   - Whole Line Input
3. **String Concatenation**
   - String Concatenation
   - Append Character or String
4. **String Length**
   - Get Length
5. **String Access**
   - Access Character
   - Modify Character
6. **String Traversal**
   - Range-based Loop
   - Index-based Loop
7. **String Search and Replace**
   - Search for Character or Substring
   - Replace Substring
8. **Substring Extraction**
   - Get Substring
9. **String Comparison**
   - Direct Comparison
   - `compare` Method
10. **String Conversion**
    - Convert Number to String
    - Convert String to Number
11. **Formatted Output**
    - `printf` Formatting
12. **Other Common Methods**
    - Clear String
    - Check if String is Empty
    - Insert String



### Detailed Explanation:

1. **Declaration and Initialization of Strings**
   - **Declaration**: `std::string` is the C++ standard library string type, declared as `std::string str;`.
   - **Initialization**: Strings can be initialized by assignment, e.g., `std::string str = "hello";`.
   - **Character Array Initialization**: Strings can also be represented by character arrays, e.g., `char str[] = "hello";`.
2. **String Input and Output**
   - **Standard Input**: Using `std::cin` reads a string but stops at spaces, e.g., `std::cin >> str;` reads only the first word.
   - **Whole Line Input**: Use `std::getline` to read an entire line, e.g., `std::getline(std::cin, str);`.
3. **String Concatenation**
   - **String Concatenation**: The `+` operator is used to concatenate two strings, e.g., `str1 + str2`.
   - **Append Character or String**: Use `str.append("abc")` or `str += "abc"` to append to a string.
4. **String Length**
   - **Get Length**: Use `.length()` or `.size()` to get the length of a string, e.g., `str.length()` returns the number of characters.
5. **String Access**
   - **Access Character**: Access individual characters by index, e.g., `str[i]` or `.at(i)`.
   - **Modify Character**: Modify characters in a string by index, e.g., `str[i] = 'c';`.
6. **String Traversal**
   - **Range-based Loop**: `for (char c : str)` to access each character.
   - **Index-based Loop**: `for (int i = 0; i < str.length(); i++)` to access characters by index.
7. **String Search and Replace**
   - **Search for Character or Substring**: Use `find` to locate characters or substrings, e.g., `str.find("abc")`.
   - **Replace Substring**: Use `str.replace(position, length, new_str)` to replace a specific part of a string.
8. **Substring Extraction**
   - **Get Substring**: Use `substr` to extract a substring, e.g., `str.substr(start, length)` returns a substring starting at `start` with a specified length.
9. **String Comparison**
   - **Direct Comparison**: Use `==`, `!=`, `<`, `>` operators to directly compare strings.
   - **compare Method**: `str.compare(other_str)` returns `0` if equal, negative if less than, positive if greater.
10. **String Conversion**
    - **Convert Number to String**: Use `std::to_string(int)` to convert an integer to a string.
    - **Convert String to Number**: Use `std::stoi`, `std::stod`, etc., to convert strings to integers or floating-point numbers.
11. **Formatted Output**
    - **`printf` Formatting**: Use `printf` to control string formatting, e.g., `printf("%.2f", value);` for precise decimal output.
12. **Other Common Methods**
    - **Clear String**: `str.clear()` to remove all contents from a string.
    - **Check if String is Empty**: Use `str.empty()` to check if a string is empty.
    - **Insert String**: `str.insert(pos, "abc")` inserts a string at a specified position.


