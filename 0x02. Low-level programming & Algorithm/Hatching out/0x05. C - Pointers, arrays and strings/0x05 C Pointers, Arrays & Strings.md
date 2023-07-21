# Pointers
## what is a pointer?
+ variable which holds the memory address of a variable.
+ when we declare a variable, the computer reserves the right amount of space for the variable in the memory (depending on its type). 
+ the space reserved for the variable is its address. 
+ when we assign a value to this variable, the computer will store this value at its address.
+ size of pointers is *8 bytes*
+ **can access the address of a variable by using the "address-of unary operator, `&`**
  
*For example*
`int \*ptr`  
+ the `*` tells us that the variable ptr is a pointer
+ `ptr` is a variable/ container that stores the address of a certain value or a variable of type **int**
+ `int` refers to the type of the variable that the ponter points to.

## why pointers?
+ only C has pointers
+ memory allocation : manage your memory very well. 
+ 


## storing an address
+ a pointer is a variable that stores the address of another variable 
+ if we can get the address of a variable by using `&`, then we can store that in another variable, and that variable becomes the pointer.  
*EXAMPLE*  
```c
int v;
int *ptr;

v = 89;
ptr = &variable;
```
  
**LET' UNDERSTAND**
+ `v` is a container which will hold an integer
+ `ptr` is also a variable, and `*` indicates it as a pointer.
+ `ptr` is pointing to the memory address of the variable `v` which contains an integer `89`
+ the type of `int` carried by `ptr` is actually the datatype of the value contained in the memory address `ptr` is pointing to, that is the memory address of the variable `v`.

  
**REMEMBER: A pointer can only point to the address of a variable it has the same datatype with**


## deferencing in pointers
+ the power of a pointer to manipulate or make changes to values stored in a memory address.

### what happens during dereferencing 
+ the dereferncing operator, `\*` tells the compiler to retrieve the value stored at the memory address that a pointer variable contains.  

*For Example*  
```c
int main(void)
{
   int n;
   int *p;

   n = 98;
   p = &n;
   printf("Value of 'n': %d\n", n);
   printf("Address of 'n': %p\n", &n);
   printf("Value of 'p': %p\n", p);
   *p = 402;
   printf("Value of 'n': %d\n", n);
   return (0);
}
```

*output*
```c
Value of 'n': 98
Address of 'n': 0x7ffd9c1969a4
Value of 'p': 0x7ffd9c1969a4
Value of 'n': 402
```
+ the pointer variable, `\*p` points to the memory location of `n`.
+ this memory location contains the value stored in n which is 98.
+ now in order to access that value stored in that memory location, we use the dereference operator, `\*`


### ASK YOURSELF!
At the sight of `*p = 402` in this:  
```c
int n;
int *p;

int n = 98;
p = &n;

*p = 402
printf("Value of n is: %d\n", n);
```
  
+ what variable's memory address is `p` holding? **ANS:** `p` is holding the memory address of the variable `n`
+ now, the `*` tells the compiler to fetch the value stored in that memory address.
+ what is the value of that memory address? **ANS:** the value there is 98
+ so, `*p` is access 98, and the program is assigning it to a new value which is 402
+ also be conscious of the fact that, it is the variable `n` that is storing the value at that memory address, so a pointer can be used to modify that value by this mechanism of pointers.
+ the output of the program above will be : Value of n is: 402

## Call by reference with pointers
+ consider this code below,

```c
#include <stdio.h>

void call_by_value_PRINT_NUMBER (int n)
{
	n = 100;
	printf("during call by value function, number 'which is now n' is  %d\n", n);
}

void call_by_reference_PRINT_NUMBER (int *n)
{
	*n = 100;
	printf("during call by reference function, number 'which is now n' is  %d\n", *n);
}

int main(void){
	int number = 2;
	
	printf("before call by value function, number is  %d\n", number);
	call_by_value_PRINT_NUMBER (number);
	printf("after call by value function, number is  %d\n\n", number);
	
	printf("after call by reference function, number is  %d\n", number);
	call_by_reference_PRINT_NUMBER (&number);
	printf("after call by reference function, number is  %d\n", number);
	
}
```
  
**OUTPUT**  
![output code](https://ibb.co/9bTDbs1)

+ explain the codes


# Arrays
+ [Notes on arrays](https://glorry88.github.io/AMI-TEACHES-C-ARRAYS/)
+ ![Further notes](https://ibb.co/XWV3LGg)


# Arrays Vs Pointers
+ arrays and pointers are not the same.
+ even though, the value of the name of an array gives a memory location
+ this memory location is the memory location of the first element of the array
+ but that does not make the array a pointer, this is as a result of a context called **Array type decay**

For `int arr[5]`, printing of `arr` will return a memory address.
