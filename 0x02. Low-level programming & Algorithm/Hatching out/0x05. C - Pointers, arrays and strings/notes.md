# Arrays
An array in programming is a way to store multiple values of the same type under a single variable name. It allows you to group related data together.

Imagine you have a collection of numbers, such as [10, 20, 30, 40, 50]. Instead of creating separate variables for each number, you can use an array to store them all together under one variable.

An array provides a convenient way to access and manipulate these values. Each value in the array is assigned a unique position called an index, starting from 0. So, in the example above, the number 10 would be at index 0, 20 at index 1, 30 at index 2, and so on.

Arrays are beneficial because they allow you to efficiently perform operations on a large set of data without needing to create individual variables for each value. They are widely used for tasks like storing lists of names, organizing data, working with tables of information, and more.

An array is like a container that holds multiple values of the same type, allowing you to access and manipulate them using their respective indices.

## Table of content
+ [Declaration and Initialization](#declaration-and-initialization-of-arrays)
	+ [Size of Array](#size-of-array)
+ [Accessing Array Elements]()
+ [Array size and memory Management]()
+ [Array Initialization Methods]()
+ [Multidimensional Arrays]()
+ [String Arrays]()
+ [Array as Function Parameters]()
+ [Array Manipulation]()


## Declaration and Initialization of Arrays
### Declaration of Arrays
In C, arrays are declared by specifying the data type of the elements followed by the array name and the size in square brackets. The general syntax is as follows:

```
data_type array_name[size];
```

Here, `data_type` represents the type of elements in the array, `array_name` is the name given to the array, and `size` specifies the number of elements in the array. For example:

```c
int numbers[5]; // Declaration of an integer array with size 5
float prices[10]; // Declaration of a float array with size 10
char characters[50]; // Declaration of a character array with size 50
```

Note that the size of the array must be a positive integer.  

  
#### Size of Array
In C, when declaring an array, it is not compulsory to state the size if you provide an initializer list. In that case, the size of the array will be automatically determined based on the number of elements in the initializer list.

For example:

```c
int numbers[] = {1, 2, 3, 4, 5}; // The size of the array is automatically determined as 5
```

In the example above, we have declared an integer array called `numbers` without specifying the size. Since we provided an initializer list with five elements, the size of the array is automatically determined as 5.

However, if you declare an array without an initializer list, it is necessary to specify the size explicitly. For example:

```c
int numbers[5]; // Declaration of an integer array with size 5
```

In this case, the size of the array is explicitly mentioned as 5, and the elements of the array will be uninitialized. It will be your responsibility to assign values to the elements later in the program.

It's important to note that if you provide an initializer list, you cannot leave the size blank in the declaration. If you don't know the size of the array in advance and need a dynamic size, you should consider using dynamic memory allocation with functions like `malloc` and `free`. *Will be discussed further in next lesson (dynamic memory allocation)*

### Initialization of Arrays:
Arrays can be initialized at the time of declaration using an initializer list enclosed in curly braces `{}`. The values in the initializer list are assigned to the corresponding elements of the array in order. The general syntax for array initialization is:

```
data_type array_name[size] = {value1, value2, ..., valueN};
```

Here's an example:

```c
int numbers[5] = {10, 20, 30, 40, 50}; // Initialization of an integer array
float prices[3] = {9.99, 5.49, 2.99}; // Initialization of a float array
char characters[5] = {'H', 'e', 'l', 'l', 'o'}; // Initialization of a character array
```

In the example above, we initialize the `numbers` array with five integers, the `prices` array with three floating-point values, and the `characters` array with the characters 'H', 'e', 'l', 'l', and 'o'. The number of elements in the initializer list should match the size of the array. If the initializer list is shorter than the size of the array, the remaining elements are automatically initialized to zero for numeric types or a null character (`'\0'`) for `char` arrays.

You can also partially initialize an array by providing fewer values in the initializer list:

```c
int numbers[5] = {10, 20}; // Partial initialization, remaining elements will be initialized to 0
```

In this case, the first two elements of the `numbers` array are initialized to 10 and 20, while the remaining three elements are automatically initialized to zero.

It's important to note that if the size of the array is not explicitly specified during declaration, the size is determined automatically based on the number of elements in the initializer list:

```c
int numbers[] = {1, 2, 3, 4, 5}; // The size of the array is automatically determined as 5
```

By understanding the declaration and initialization of arrays, you can create arrays of different data types and sizes with the initial values you require.

#### Size of an Array.
The formula to calculate the number of elements in an array is:

```
total_size_of_array / size_of_single_element
```

Let's break down the formula:

- `total_size_of_array`: This represents the total size of the array in bytes. It can be obtained using the `sizeof` operator applied to the entire array, like `sizeof(array)`. The `sizeof` operator returns the size of its operand in bytes.

- `size_of_single_element`: This represents the size of a single element in the array. It can be obtained using the `sizeof` operator applied to a single element of the array, like `sizeof(array[0])`. By dividing the total size of the array by the size of a single element, we obtain the number of elements in the array.

Here's an example usage of the formula:

```c
int numbers[] = {10, 20, 30, 40, 50};
int numElements = sizeof(numbers) / sizeof(numbers[0]);
```

In this example, `sizeof(numbers)` returns the total size of the `numbers` array in bytes, and `sizeof(numbers[0])` returns the size of a single element in the array (in this case, the size of an `int`). Dividing the total size by the size of a single element gives us the number of elements in the array.

Please note that this formula assumes that the array is not a pointer or dynamically allocated. It works for arrays with a known size at compile-time. If the array is dynamically allocated or is a pointer to an array, the formula will not work, and you'll need to keep track of the number of elements using another method.


### EXERCISE
Try your hands on these. If you have any issues, you can [Contact Me]() for more explanation or answer review.

Here are a few practice exercises to help you reinforce your understanding of array declaration and initialization:

Exercise 1:
Declare an integer array named `ages` with a size of 4. Initialize it with the values 18, 25, 32, and 40. Print the elements of the array.

Exercise 2:
Declare a character array named `name` with a size of 10. Initialize it with your name as a string. Print the characters of the array one by one.

Exercise 3:
Declare a float array named `grades` with a size of 6. Initialize it with random floating-point values of your choice. Print the elements of the array.

Exercise 4:
Declare a string array named `fruits` with a size of 5. Initialize it with the names of five different fruits. Print the elements of the array.

Exercise 5:
Declare a multidimensional integer array named `matrix` with dimensions 3x3. Initialize it with values of your choice. Print the elements of the matrix row by row.

Exercise 6:
Declare a character array named `sentence` with a size of 50. Prompt the user to enter a sentence. Store the sentence in the array and then print it.

These exercises should give you a good opportunity to practice declaring and initializing arrays in various scenarios. Feel free to give them a try and don't hesitate to ask if you have any questions or need further assistance!

## Accessing Array Elements
Accessing array elements in C is done by using the array name followed by the index of the element in square brackets `[]`. The index specifies the position of the element within the array, starting from 0 for the first element.

Here's an example:

```c
int numbers[5] = {10, 20, 30, 40, 50};

// Accessing array elements
int firstElement = numbers[0];  // Accessing the first element (index 0)
int secondElement = numbers[1]; // Accessing the second element (index 1)
int thirdElement = numbers[2];  // Accessing the third element (index 2)
```

In this example, we have an integer array `numbers` with 5 elements. To access specific elements, we use the array name followed by the index in square brackets. For instance, `numbers[0]` accesses the first element, `numbers[1]` accesses the second element, and so on.

You can also use variables or expressions as the index value. For example:

```c
int index = 3;
int element = numbers[index]; // Accessing the element at index 3
```

In this case, the variable `index` holds the value 3, and `numbers[index]` retrieves the element at that index.

It's important to note that array indices must be within the valid range of the array, which is from 0 to the size of the array minus 1. Attempting to access an element outside this range can result in undefined behavior or runtime errors.

Keep in mind that arrays are zero-indexed in C, meaning the first element is at index 0, the second element is at index 1, and so on. Make sure to use the correct index values when accessing array elements.

## Array Initialization Methods
1. Initializing at Declaration:
   - You can set the initial values of an array when declaring it using curly braces `{}` with the values separated by commas.
   - The number of values determines the size of the array.
   - Example: 
     ```c
     int numbers[] = {1, 2, 3, 4, 5};
     // The 'numbers' array has 5 elements with values 1, 2, 3, 4, 5
     ```

2. Initializing with a Loop:
   - You can use a loop to assign values to the elements of an array.
   - This is helpful when you want to initialize the array elements dynamically or perform calculations.
   - Example:
     ```c
     int numbers[5];
     for (int i = 0; i < 5; i++) {
         numbers[i] = i + 1;
     }
     // The 'numbers' array has 5 elements with values 1, 2, 3, 4, 5
     ```

3. Partial Initialization:
   - You can initialize only some elements of an array while leaving others uninitialized.
   - Uninitialized elements will contain random/garbage values.
   - Example:
     ```c
     int numbers[5] = {1, 2};
     // The 'numbers' array has 5 elements with values 1, 2, 0, 0, 0
     ```

4. Zero Initialization:
   - You can set all elements of an array to zero using `{0}` in the initializer list.
   - Example:
     ```c
     int numbers[5] = {0};
     // The 'numbers' array has 5 elements with values 0, 0, 0, 0, 0
     ```

5. Character Array Initialization:
   - Character arrays, which store strings, can be initialized with a string literal.
   - The compiler automatically adds a null terminator `\0` at the end of the string.
   - Example:
     ```c
     char name[] = "John";
     // The 'name' array has 5 elements with values 'J', 'o', 'h', 'n', '\0'
     ```

6. Compound Literal Initialization (C99 and later):
   - Using compound literals, you can initialize arrays directly without declaring them separately.
   - Compound literals are enclosed in parentheses and have the form `(type) { /* initializer list */ }`.
   - Example:
     ```c
     int numbers[] = (int[]) {1, 2, 3, 4, 5};
     // The 'numbers' array has 5 elements with values 1, 2, 3, 4, 5
     ```

These methods provide different ways to initialize arrays in C. Choose the method that suits your needs and ensures the array is correctly initialized.

Remember to ensure that the array is large enough to hold the initializer values and avoid going beyond the bounds of the array during initialization.

If you have any further questions or need more clarification, feel free to [ask]()!

## Multidimensional arrays

