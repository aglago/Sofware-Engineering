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
### What is a dimension? 
In the context of arrays, the term "dimension" refers to the number of indices required to access an individual element within the array. It represents the size or extent of the array in a particular direction. Let's explore the concept of dimension in more detail:

1. One-Dimensional Array:
   - A one-dimensional array, also known as a single-dimensional array, has one dimension.
   - It can be thought of as a list of elements, where each element is identified by a single index.
   - Example: `int numbers[5];` represents a one-dimensional array with 5 elements.

2. Two-Dimensional Array:
   - A two-dimensional array has two dimensions: rows and columns.
   - It can be visualized as a grid or table structure, where elements are organized into rows and columns.
   - Elements within a two-dimensional array are accessed using two indices: one for the row and one for the column.
   - Example: `int matrix[3][4];` represents a two-dimensional array with 3 rows and 4 columns.

3. Three-Dimensional Array:
   - A three-dimensional array has three dimensions: rows, columns, and depth.
   - It extends the concept of a two-dimensional array into a three-dimensional space.
   - Elements within a three-dimensional array are accessed using three indices: one for the row, one for the column, and one for the depth.
   - Example: `int cube[2][3][4];` represents a three-dimensional array with 2 layers, 3 rows, and 4 columns.

In general, the dimension of an array corresponds to the number of indices required to access an individual element. Each index represents a specific level or direction within the array.

It's important to note that the dimension of an array is determined at the time of declaration and cannot be changed dynamically during the execution of the program.

### Multidimensional Array
Multidimensional arrays in C are arrays with more than one dimension. They can be thought of as arrays of arrays, forming a grid or matrix-like structure.

### Declaring a Multidimensional Array
To declare a multidimensional array in C, you specify the number of dimensions and the size of each dimension. The general syntax for declaring a multidimensional array is as follows:

```c
data_type array_name[size1][size2]...[sizeN];
```

Here's a breakdown of the components involved:

- `data_type`: The data type of the elements in the array, such as `int`, `char`, `float`, etc.
- `array_name`: The name you give to the multidimensional array. Choose a meaningful name to represent the data it will store.
- `size1`, `size2`, ..., `sizeN`: The sizes of each dimension of the array. Replace `size1`, `size2`, etc. with the desired integer values for each dimension.

Here are a few examples to illustrate the declaration of multidimensional arrays:

1. Declaration of a 2D array:
```c
int matrix[3][4];
```
This declares a 2-dimensional array named `matrix` with 3 rows and 4 columns. It can hold a total of 12 elements.

2. Declaration of a 3D array:
```c
float cube[2][3][4];
```
This declares a 3-dimensional array named `cube` with 2 layers, 3 rows, and 4 columns. It can hold a total of 24 elements.

3. Declaration of a 4D array:
```c
char hypercube[2][3][4][5];
```
This declares a 4-dimensional array named `hypercube` with 2 layers, 3 rows, 4 columns, and 5 elements in each column. It can hold a total of 120 elements.

You can extend this pattern to create arrays with more dimensions by adding additional size values within the brackets.

Remember that the declaration only sets aside memory for the array, and you'll need to initialize the array separately to assign values to its elements.

### Initialization of Multidimensional Arrays
To initialize a multidimensional array in C, you can use nested curly braces to specify the values for each element of the array. The initialization syntax for multidimensional arrays follows the same pattern as the declaration syntax. Here's an example:

```c
int matrix[2][3] = {
  {1, 2, 3},   // First row
  {4, 5, 6}    // Second row
};
```

In this example, we have initialized a 2D array named `matrix` with 2 rows and 3 columns. The values for each element are specified within the nested curly braces. The first row contains the values `{1, 2, 3}`, and the second row contains the values `{4, 5, 6}`.

You can extend this pattern for arrays with more dimensions:

```c
float cube[2][3][4] = {
  {
    {1.0, 2.0, 3.0, 4.0},     // First row of first layer
    {5.0, 6.0, 7.0, 8.0},     // Second row of first layer
    {9.0, 10.0, 11.0, 12.0}   // Third row of first layer
  },
  {
    {13.0, 14.0, 15.0, 16.0},  // First row of second layer
    {17.0, 18.0, 19.0, 20.0},  // Second row of second layer
    {21.0, 22.0, 23.0, 24.0}   // Third row of second layer
  }
};
```

In this example, we have initialized a 3D array named `cube` with 2 layers, 3 rows, and 4 columns. The values for each element are specified within the nested curly braces. Each layer contains rows, and each row contains columns.

It's important to ensure that the number of values provided during initialization matches the size of the array. In the above examples, we provided the correct number of values based on the dimensions specified in the declaration.

If you don't provide enough values during initialization, the remaining elements will be implicitly initialized to zero for numeric types. For character arrays, the remaining elements will be initialized to the null character ('\0').

You can also initialize a multidimensional array partially. In that case, the unspecified elements will be implicitly initialized to zero or null character, depending on the type.

### Accessing Elements from Multidimensional Arrays
To access elements in a multidimensional array in C, you use multiple indices corresponding to each dimension. The indices indicate the specific position of the element within the array. Here's the general syntax for accessing elements in a multidimensional array:

```c
array_name[index1][index2]...[indexN]
```

Let's break down the process of accessing elements in a multidimensional array with an example:

```c
int matrix[3][4] = {
  {1, 2, 3, 4},
  {5, 6, 7, 8},
  {9, 10, 11, 12}
};
```

In this example, we have a 2D array named `matrix` with 3 rows and 4 columns. To access individual elements, we specify the row index followed by the column index:

```c
int element = matrix[row_index][column_index];
```

Here's an example of accessing elements from the `matrix` array:

```c
int element_0_2 = matrix[0][2];   // Accesses element at row 0, column 2 (value: 3)
int element_2_3 = matrix[2][3];   // Accesses element at row 2, column 3 (value: 12)
```

You can also use variables or expressions as indices:

```c
int row_index = 1;
int column_index = 3;
int element = matrix[row_index][column_index];   // Accesses element at row 1, column 3 (value: 8)
```

Keep in mind that array indices in C are zero-based, meaning the first element is at index 0. So, the valid index range for rows is from 0 to `num_rows - 1`, and for columns, it is from 0 to `num_columns - 1`.

For arrays with more dimensions, you simply extend the indexing pattern by adding more indices for each dimension:

```c
float cube[2][3][4] = { /* Initialization code */ };
float element = cube[layer_index][row_index][column_index];
```

Make sure to provide valid indices within the appropriate range for each dimension of the array.


### Iterating over Multidimensional Arrays
To iterate over a multidimensional array in C, you can use nested loops, with each loop corresponding to a dimension of the array. By incrementing the loop variables from the minimum index to the maximum index, you can access each element of the array systematically. Here's an example of how to iterate over a 2D array:

```c
int matrix[3][4] = {
  {1, 2, 3, 4},
  {5, 6, 7, 8},
  {9, 10, 11, 12}
};

for (int i = 0; i < 3; i++) {
  for (int j = 0; j < 4; j++) {
    printf("matrix[%d][%d] = %d\n", i, j, matrix[i][j]);
  }
}
```

In this example, we have a 2D array `matrix` with 3 rows and 4 columns. To iterate over all elements, we use two nested loops. The outer loop controls the row index `i`, and the inner loop controls the column index `j`. By varying the values of `i` and `j`, we can access each element of the array.

The output of the above code will be:

```
matrix[0][0] = 1
matrix[0][1] = 2
matrix[0][2] = 3
matrix[0][3] = 4
matrix[1][0] = 5
matrix[1][1] = 6
matrix[1][2] = 7
matrix[1][3] = 8
matrix[2][0] = 9
matrix[2][1] = 10
matrix[2][2] = 11
matrix[2][3] = 12
```

Similarly, for multidimensional arrays with more dimensions, you can add more nested loops to iterate over each dimension. For example, a 3D array requires three nested loops, and a 4D array requires four nested loops.

Here's an example of iterating over a 3D array:

```c
float cube[2][3][4] = { /* Initialization code */ };

for (int i = 0; i < 2; i++) {
  for (int j = 0; j < 3; j++) {
    for (int k = 0; k < 4; k++) {
      printf("cube[%d][%d][%d] = %f\n", i, j, k, cube[i][j][k]);
    }
  }
}
```

Remember to adjust the loop conditions and indices based on the size of each dimension in your specific multidimensional array.

By using nested loops, you can systematically access and process each element of a multidimensional array.


### Passing Multidimensional Arrays to Functions
To pass a multidimensional array to a function in C, you need to specify the dimensions of the array in the function parameter. Since C does not directly support passing arrays as function arguments, you can achieve this by declaring the parameter as a pointer to an array of appropriate dimensions. Here's the general syntax for passing a multidimensional array to a function:

```c
return_type function_name(data_type (*array_name)[size1][size2]...[sizeN])
{
  // Function body
}
```

Let's break down the components involved:

- `return_type`: The data type of the value that the function returns, such as `void`, `int`, `float`, etc.
- `function_name`: The name you give to the function. Choose a meaningful name that represents the functionality it performs.
- `data_type`: The data type of the elements in the multidimensional array, such as `int`, `char`, `float`, etc.
- `array_name`: The name you give to the multidimensional array parameter in the function.
- `size1`, `size2`, ..., `sizeN`: The sizes of each dimension of the array.

Here's an example of a function that takes a 2D array as a parameter:

```c
void processMatrix(int (*matrix)[3][4])
{
  // Function body
}
```

Inside the function, you can access and manipulate the elements of the multidimensional array using the same indexing syntax as before.

To call the function and pass a multidimensional array as an argument, you can provide the array with the appropriate dimensions:

```c
int myMatrix[3][4] = { /* Initialization code */ };
processMatrix(&myMatrix);
```

In this example, `&myMatrix` is the address of the `myMatrix` array, which is passed as an argument to the `processMatrix` function.

You can extend this pattern for arrays with more dimensions by adding more dimensions to the function parameter.

It's important to note that when passing multidimensional arrays to functions, you need to ensure that the dimensions specified in the function parameter match the dimensions of the array being passed.


...
