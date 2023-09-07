

### C++17 most important feature over C++14

1. **Structured Bindings:**
   C++17 allows you to create structured bindings to decompose objects into their constituent parts easily.

   ```
   std::pair<int, double> values{42, 3.14};
   auto [x, y] = values;
   std::cout << "x: " << x << ", y: " << y << std::endl;
   ```
2. **If-Init Statements:**
   You can now declare and initialize variables in the `if` statement.

   ```
   if (int i = get_value(); i > 0) {
       // i is only in scope when i > 0
       std::cout << "i is positive." << std::endl;
   }
   ```
3. **Fold Expressions:**
   Fold expressions simplify variadic template code.

   ```
   template <typename... Args>
   auto sum(Args... args) {
       return (args + ...);
   }
   ```
4. **constexpr if:**
   Conditional compilation using `if constexpr` allows you to write code that is conditionally compiled at compile-time.

   ```
   template <typename T>
   void process(T val) {
       if constexpr (std::is_integral<T>::value) {
           // This code will be included only if T is an integral type
           val++;
       }
   }
   ```
5. **Guaranteed Copy Elision:**
   C++17 guarantees copy elision in certain situations, even when the copy constructor or move constructor is deleted.

   ```
   std::string createString() {
       return "Hello, World!";
   }

   std::string str = createString();
   ```
6. **Structured Bindings for std::tuple:**
   You can use structured bindings with `std::tuple` to easily access its elements.

   ```
   std::tuple<int, double, std::string> values{42, 3.14, "Hello"};
   auto [x, y, z] = values;
   ```
7. **Inline Variables:**
   C++17 introduced the `inline` specifier for variables, allowing you to define variables in header files.

   ```
   inline int myGlobalVar = 42;
   ```
8. **Filesystem Library:**
   C++17 added the `<filesystem>` library, which provides a standard way to work with files and directories.

   ```
   #include <filesystem>
   namespace fs = std::filesystem;

   fs::path filePath = fs::current_path() / "example.txt";
   ```
