

### C++14 most important feature over C++11


1. **Binary Literals:** C++14 introduced the ability to use binary literals, similar to hexadecimal (0x) and octal (0) literals. For example, you can write 0b1101 to represent the binary number 1101.

```
int binaryValue =0b1101; // Binary literal representing the value 13
```

2. **Return Type Deduction for Functions**: Functions can use `auto` as their return type for type deduction.

```
auto add(inta,intb) { return a + b; }
```

3. **Generic Lambdas**: Lambdas can use the `auto` keyword in their parameter list for generic lambda functions.

```
auto add =[](auto a,auto b) { return a + b; };
```

4. **Variable Templates:** You can create variable templates, which are similar to function templates but for variables.

```
template <typename T>
constexpr T pi =T(3.1415926535897932385);
```

5. **Relaxation of `constexpr` Restrictions**: C++14 relaxed some of the restrictions on `constexpr` functions, allowing for more complex computations and data manipulations.
6. **Aggregates with Member Initializers**: Non-static data members of an aggregate class can be initialized with braces.

```
struct Point {
  int x =0;
  int y =0;
};

Point p = {1, 2}; // C++14 allows this form of initialization
Point p1; // x and y are initialized to 0
```


7. **Extended `sizeof`**: You can use `sizeof` with non-static data members of a class to determine the size of that member.

```
struct Example { 
  int x;
  double y; 
}; 
size_t size = sizeof(Example::x); // Gets the size of 'x'
```


8. **Standard Library Enhancements**: The C++14 standard library introduced several new functions and improvements, including `std::make_unique`, `std::index_sequence`, and more.

```
 #include <memory>

 auto ptr = std::make_unique<int>(42);
```


10. **User-Defined Literals for Standard Library Types**: User-defined literals can be defined for standard library types like `std::chrono` durations.

```
#include <chrono>
usingnamespace std::chrono_literals;

auto five_seconds =5s;
```


10. **Polymorphic `std::allocator`: `std::allocator` now supports polymorphic memory resources.**

```
std::allocator<int> alloc;
int* ptr = alloc.allocate(1);
alloc.deallocate(ptr,1);
```


11. **Heterogeneous Lookup for Associative Containers**: Associative containers (e.g., `std::map`, `std::set`) support heterogeneous lookup, allowing you to find elements using a different type than the container's key type.

```
std::map<std::string,int> map;
auto it = map.find("key"); // Find using a different type (const char*)
```


12. **Sized Deallocation**: You can use `operator delete` with an additional size argument to deallocate memory allocated with `operator new`.

```
 void* mem =operator new(10); 
 operator delete(mem, 10); // Deallocate with size information
```


13. **[[deprecated]] Attribute**: You can mark functions and types as deprecated using the `[[deprecated]]` attribute.

```
[[deprecated("Use newFunction() instead.")]]
void oldFunction() {
// Deprecated function code
}
```


14. **[[deprecated]] Message Attribute**: You can provide a custom message when using the `[[deprecated]]` attribute to indicate why something is deprecated.

```
[[deprecated("This class is deprecated. Use NewClass instead.")]]
class OldClass {
// Class definition
};
```


15. **Inline Namespaces**: You can nest namespaces within inline namespaces, allowing for better control over symbol visibility.

```
inline namespace MyNamespace {
   void someFunction() {
      // Function definition
   }
}
```


16. **Variable-Size Arrays**: Variable-size arrays (VLA) are now part of the standard but are only available in certain contexts.

```
int n =5;
int array[n];
```


17. **Improved Type Deduction for `auto`:** Type deduction for `auto` in C++14 is more consistent and accurate.
18. **`constexpr if`**: Introduced the `constexpr if` feature for more powerful compile-time branching.

```
template typename<T> 
void process (T value) {
  if constexpr (std::is_integral<T>::value) {
    // Integer-specific code
    value = value *2; 
  } else {
    // Non-integer code
    value = value /2.0; 
  }
}
```


19. **Digit Separators**: You can use single quotes as digit separators in numeric literals for better readability (e.g., `1'000'000`).

`long long bigNumber = 1'000'000'000;`

20. **Relaxation of `decltype(auto)`**: The use of `decltype(auto)` is more flexible and allows for better type deduction in C++14.
21. **Extended `sizeof` for Member Pointers**: You can use `sizeof` with member pointers.

```
struct Example { 
  int x;
  double y;
};

size_t size = sizeof(&Example::x); // Gets the size of a member pointer
```

22. **Library Additions**: Various new library functions and features were introduced, including improvements to `<tuple>`, `<utility>`, and `<iostream>`.

These are the major features and changes introduced in C++14 compared to C++11. C++14 focused on improving developer productivity, code readability, and runtime performance while maintaining backward compatibility with C++11.
