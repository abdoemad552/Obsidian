Pointers are variables that stores the address of another variable.

The data type of the pointer should be the same as the variable that it points to (Strongly typed).

Pointers is strongly typed as we they are not just used for referencing variables, they are also used for dereferencing them. And hence the information needed for dereferencing an `int` variable is different from the information needed for dereferencing any other variable.

The get the value of the variable that the pointer points to, we use `*` which is called dereferencing operator.
```c++
int a = 5;
int *p = &a; // Referencing
cout << *p << "\n"; // Referencing 
// 5
```

Arithmetic operations can be done on pointers include addition, subtraction, increment, and decrement. `+, -, +=, -=, ++, --`

When you increment a pointer one unit, it moves number of bytes equals to the number of bytes that any variable of its data type.
```c++
int *p = 0x00;
p++;
// Now p 0x4, because int can hold 4 bytes.
```

In the following example, we see that `x` is an `int` variable. This means that `x` is 4 bytes size.
Now, we created an `int` pointer variable `u` that points to `x` and another pointer variable `v` that points to the same position by casting `u`.
```c++
int x = 0x0000010f;
// x = 00000000 00000000 00000001 11111111
  
int *u = &x;  
char *v = (char*) u;  
  
cout << x << ' ' << *u << ' ' << int(*v) << ' ' << int(*(v + 1)) << '\n';
```

Any increment to the variable `u` will make the pointer moves 4 bytes in the memory, but in case of `v` and increment will make the variable only move one byte in the memory.
Hence the the value of `int(*(v + 1))` is `1`.

In order to create a generic pointer that can points to variables of any data type, we can use `void*` pointers. These pointers can only hold addresses but can't be dereferenced or put on arithmetic operations.

# Pointer to pointer
A pointer to a pointer means that we need a variable to store the address of the a pointer variable.

This can be done by adding another asterisk. This can be shown in the following:
```c++
int a = 5;
int *b = &a;
int **c = &b;
int ***d = &c;
// and so on...
```

Since any pointer is 8 bytes of size, any increment of a pointer variable moves the pointer 8 bytes in the memory.

The argument in the calling function is called the **actual argument**.
The argument in the called function is called the **formal argument**.

The stack is a memory portion where the information about the functions and their local variables are stored.

To know the number of elements in an array:
```c++
int A[] = {1, 2, 3, 4, 5, 6};

const int SIZE = sizeof(A) / sizeof(int);
```

When we use arrays as function arguments and then pass an actual array to the function, we don't create a new array, instead we are creating a pointer that points to the first address of that array. Hence the size of the new created pointer is only 8 bytes which is usually different from the size of the actual array.

# Character arrays and pointers
Character arrays are similar to usual arrays, but it stores characters.
There is a difference in character arras which is that there is an additional value added to it which is the last character in the array.
If we need to store `"John"` in a character array, you may think that we need an array of type `char` and of size 4. In fact we need a size of 5, because the `\0` is stored in the 5th position implicitly. String in C has to be `null` terminated.
![[Pasted image 20240220234448.png]]

In C, if you declare an array without initializing it explicitly, its elements will contain garbage values. However, in your case, you've initialized `s[0]` with the character `'x'`, so `s[0]` contains `'x'` and the rest of the elements are automatically initialized to the null character `'\0'`.

In C, arrays are not modifiable l-values, meaning you cannot directly change the value of an array to point to another memory location. When you use the array name in an expression, it decays to a pointer to its first element. However, you cannot directly increment the array itself:
```c
int arr[5];

arr++; // This is invalid and will result in a compilation error
```
This is because **the name of an array in C acts as a constant pointer to its first element**, and you cannot modify this pointer directly. It's essentially a pointer constant, not a variable.

**Pointer Decay**: When you use the array name `arr` in an expression where a pointer is expected, such as passing it to a function that expects a pointer argument, it decays into a pointer to its first element. This pointer behaves like any other pointer and can be manipulated.

A `const` pointer in C is a pointer whose value (the memory address it holds) cannot be changed. However, it does not necessarily mean that the data it points to is constant. There are two common uses of `const` with pointers:

1. **Pointer to constant data**: This means the data pointed to by the pointer cannot be modified through that pointer, but the pointer itself can be modified to point to different data.

    ```c
    int x = 5;
    const int *ptr = &x;
    *ptr = 10;  // This is not allowed because ptr is a pointer to constant data
    ```

    In this example, `ptr` is a pointer to a constant integer, so you cannot modify the integer value it points to through `ptr`. However, you can modify `x` directly.

2. **Constant pointer**: This means the pointer itself cannot be changed to point to a different memory location, but the data it points to can be modified.

    ```c
    int y = 10;
    int *const ptr2 = &y;
    ptr2 = &x;  // This is not allowed because ptr2 is a constant pointer
    ```

    In this example, `ptr2` is a constant pointer to an integer, so you cannot change where `ptr2` points to. However, you can modify the integer value it points to.


In C, when you declare a string literal like `"HElo"`, it's actually stored in read-only memory, typically in a section of memory known as the "text segment" or "code segment". When you declare a pointer like `char *a = "HElo";`, you're pointing `a` to the memory location where the string literal `"HElo"` is stored.

```c
char *a = "HElo";
```

Here, `a` is a pointer to the first character of the string literal `"HElo"`. The pointer `a` itself is mutable; you can change where it points to. However, the string literal it points to is immutable; you cannot modify its contents.

For example:

```c
a = "World"; // Valid: Changes the pointer 'a' to point to the string "World"
```

This operation is allowed because it changes the pointer `a` to point to a different memory location where the string `"World"` is stored. However, trying to modify the contents of the string literal through `a` like `a[0] = 'h';` will result in undefined behavior because you're trying to modify a read-only memory location.

If you need a mutable string, you should declare an array instead:

```c
char a[] = "HElo";
```

This will create a mutable character array `a` initialized with the contents of the string literal `"HElo"`. In this case, you can modify the contents of `a` as it's stored in writable memory.

# Dynamic memory
The amount of memory allocated for some function is called **stack frame**.
Allocation of stack is done during run time.

Unlike stack, application heap size is not fixed. its size can vary during the time of execution or during the life time of the application.
There is no set rule for allocation and deallocation of memory. A programmer can totally control how much memory to use from the heap till what time to keep the data in the memory. The heap can grow as long you don't run out of memory on the system itself.

Heap is also called free-store or dynamic memory.

To use dynamic memory in C, we need to know four functions:
```c
malloc
calloc
realloc
free
```

To store an integer in the heap, we use `malloc`. We call malloc function to reserve or get some space allocated in the heap.
```c
int *x = (int*) malloc(sizeof(int));
```

malloc returns a `void` pointer to the first byte allocated in the heap (starting address of this block).

**The only way to use memory on heap is to use reference.**

All what`malloc`does is that it looks for some free space in the heap, reserves (allocates) it, and returns the address of the allocated block.

At any point in our program, if we are done using some block of the memory which is dynamically allocated using `malloc`, we also need to clear it.

To free or clear the reserved memory space we use `free` function:
```c
free(x);
x = NULL;
```

If we want to allocate an array of size `n` we use the following:
```c
int *arr = (int*) malloc(n * sizeof(n));
```

This statement allocates an array of size `n` and returns first address in this array (Base address).

If `malloc` is not able to allocate any space in the memory it returns `null`.

This can be done in `C++` as following:
```c++
int *A = new int;
delete A;

A = new int[n];
delete[] A;
```

`calloc` is also used to allocate some memory in the heap and has the following signature:
```C
void *calloc(size_t NumOfElements, size_t SizeOfElements);
```

The difference here is that `calloc` allocates and gives initial value to the allocated space.

If we want to modify the size of a memory block of size n into size of m, we can use `realloc`.
```c
void *realloc(void *ptr, size_t size);
```

`realloc` deallocates the old object pointer by `ptr` and returns a pointer to a new object that has the size of specified by `size`.
The point to note is that **`realloc()` should only be used for dynamically allocated memory**. If the memory is not dynamically allocated, then behavior is undefined.

After calling `realloc`, the pointer passed to it is still valid. However, it's important to note that the memory block might have been moved to a different location if the reallocation couldn't be done in place. In such cases, the pointer returned by `realloc` will point to the new memory block, and the old pointer becomes invalid. It's crucial to assign the new pointer returned by `realloc` back to the original pointer to avoid losing track of the memory and potentially causing memory leaks or undefined behavior.
```c
#include <stdio.h>  
#include <string.h>  
#include <stdlib.h>  
  
int main() {  
    int *a = (int*) malloc(5 * sizeof(int));  
  
    for (int i = 0; i < 5; i++) {  
        a[i] = i;  
    }  
  
    int *b = realloc(a, 10 * sizeof(int));  
  
    for (int i = 0; i < 10; i++) {  
	    printf("%d ", b[i]);  
    }
    
    free(a);
    free(b);
    return 0;  
}
```

```c
int *A = (int*) realloc(A, 0); // Equivalent to free(A)
int *A = (int*) realloc(NULL, n * sizeof(int)); // Equivalent to malloc
```

# Function pointers
Function pointers are pointers that points to functions.

In most modern operating systems, including those that run C and C++ programs, executable code, including functions, is typically stored in a section of memory known as the code segment or text segment. This segment is typically read-only and contains the compiled machine code instructions of the program.

Here are some common segments found in the memory layout of a process:
1. **Code Segment (Text Segment)**: This segment holds the executable code of the program. It is typically read-only to prevent accidental modification of the program's instructions during execution.
2. **Data Segment**: This segment contains initialized global and static variables. It is further divided into:
   - **Initialized Data**: This part contains global and static variables that are explicitly initialized with a value. These variables are typically stored in writable memory.
   - **Uninitialized Data (BSS)**: This part contains global and static variables that are not explicitly initialized by the program. These variables are typically initialized to zero or null pointers. Unlike initialized data, this memory segment doesn't need to store the actual initialized values, so it's more efficient to store it in a separate segment.
3. **Heap**: This segment is used for dynamic memory allocation. Functions like `malloc()` and `realloc()` allocate memory from this segment. It's a region of memory where the size and lifetime of objects can be managed at runtime.
4. **Stack**: This segment is used for local variables and function call management. Each time a function is called, space is allocated on the stack for its parameters and local variables. The stack also stores the return addresses of function calls and other control information necessary for function invocation.
5. **Other segments**: Depending on the operating system and the specific requirements of the program, there may be additional segments for special purposes, such as the thread-local storage segment or segments for memory-mapped files.

The code segment, where the executable code resides, is typically loaded into memory when the program is loaded and remains fixed in size throughout the program's execution. The exact memory layout may vary depending on the compiler, operating system, and linker options used.

We use pointers to functions to dereference and execute the function.
The address of a function is the address of the first instruction in the function.

The following is a general syntax of function pointer:
```c
return_type (*pointer_name) (type1, type2, ...)
```

`type1, type2, ...` are the data types of function arguments.
```c
int funPointer(int x, int y) {  
    return 0;  
}  
  
int main() {  
    int (*func) (int, int) = funPointer;  
}
```

Function pointers can be passed as arguments to functions.

Memory leaks occurs due to the allocation of some space in the heap, and not freeing this space. This results in an allocated unused space which is known as memory leak.