# **C++ Basics Repository 📘**

🚀 欢迎来到我的 C++ 基础学习笔记仓库！

这个仓库用于记录我学习 C++ 基础的过程。在这里，我会整理和分享学习 C++ 的代码示例、重要概念、常用 STL 容器、内存管理、面向对象编程、操作符重载等知识点。这个仓库的目标是系统化地掌握 C++ 基础，为深入理解和应用 C++ 打下坚实的基础。

------



## **📌 目录结构**

本仓库按照 C++ 基础知识模块进行分类，每个 `.md` 文件对应一个主题，以下是各个文件的详细说明：

### **1️⃣ C++ 语言基础**

- `01 C++ Basics.md`

  本文件介绍 C++ 语言的基础，包括：

  - C++ 语言概述（特点、应用场景）
  - 变量和数据类型（`int`、`double`、`char`、`bool`）
  - 基本输入输出（`cin`、`cout`）
  - 作用域和命名空间（`std::`）

### **2️⃣ 流程控制**

- **`02 Loop.md`**
   介绍 C++ 中的循环结构：
  - `for`、`while`、`do-while` 语句
  - 终止循环 (`break`) 和跳过循环 (`continue`)
  - 循环的嵌套与常见错误
- **`03 Basic Control Structures.md`**
   讲解 C++ 里的条件判断结构：
  - `if-else` 语句
  - `switch-case` 语句
  - 三元运算符 (`? :`)

### **3️⃣ 算术运算与格式化**

- `04 Basic Arithmetic and Output Formatting.md`

  介绍 C++ 的基本运算符和格式化输出：

  - 算术运算符（`+`、`-`、`*`、`/`、`%`）
  - 关系运算符与逻辑运算符
  - `iostream` 控制符（`setw`、`setprecision`）

### **4️⃣ 常见数据结构**

- **`05 Array.md`**
   介绍 C++ **数组（Array）**：
  - 数组的定义与初始化
  - 一维数组与多维数组
  - 指针与数组的关系
- **`06 Vector-en.md`**
   介绍 C++ STL **`vector` 容器**：
  - `vector` 的基本用法
  - 插入、删除元素
  - 遍历方式（`for`、`iterator`）
- **`07 String.md`**
   介绍 C++ **字符串（`std::string`）**：
  - 字符串的基本操作（拼接、查找、截取）
  - `getline()` 读取整行输入
  - C 风格字符串 (`char[]`) 和 `std::string` 的区别

### **5️⃣ 链表、哈希表、集合**

- **`08 Linked List.md`**
   介绍 **链表（Linked List）** 的实现：
  - 单链表、双向链表
  - 插入、删除节点
  - `struct` 结构体与指针的结合使用
- **`09 Hash Table.md`**
   介绍 **哈希表（Hash Table）**：
  - 哈希函数的原理
  - C++ STL `unordered_map`
  - 解决哈希冲突的方法（拉链法、开放地址法）
- **`10 Set-zh.md`**
   介绍 **集合（Set）**：
  - `std::set` 和 `std::unordered_set` 的区别
  - 插入、删除、查找元素的时间复杂度
  - 用 `set` 解决去重问题

------



## **📌 使用方法**

1. 克隆仓库

   ```bash
   git clone https://github.com/your-repo/cpp-basics.git
   cd cpp-basics
   ```

2. 阅读笔记

   - 直接在 `Markdown` 文件中查看学习内容。
   - 推荐使用 Markdown 编辑器（VS Code, Typora, Obsidian）。

3. 编写测试代码

   - 建议根据笔记内容编写 C++ 代码进行练习。

   - 运行 C++ 代码：

     ```bash
     g++ your_code.cpp -o output
     ./output
     ```

------



## **📌 适合人群**

✅ **C++ 初学者**：想要系统学习 C++ 语法
 ✅ **希望巩固基础的开发者**：回顾 C++ 语言核心知识
 ✅ **刷 LeetCode/算法竞赛的用户**：复习数据结构基础（数组、链表、哈希表等）

------



## **📌 未来计划**

📌 **优化现有笔记**，添加更多示例代码
 📌 **扩展进阶主题**（如 **智能指针、多线程、STL 深入解析**）
 📌 **加入练习题**，帮助加深理解

