# Bitwise OR (|) Operator:
The bitwise OR operator (|) performs a bitwise OR operation between corresponding bits of two integers. The result will have a 1 in any position where at least one of the input bits is 1.

The truth table for the OR operator is as follows:
```
0 | 0 = 0
0 | 1 = 1
1 | 0 = 1
1 | 1 = 1
```

## Example: Using Bitwise OR Operator

Let's consider an example where we have some flags to represent options:

1. Option A: 0001 (binary) - Represented as 1 in decimal.
2. Option B: 0010 (binary) - Represented as 2 in decimal.
3. Option C: 0100 (binary) - Represented as 4 in decimal.
4. Option D: 1000 (binary) - Represented as 8 in decimal.

Suppose we want to combine options A and C. We can use the OR operator to do this:

```
0001 (Option A) | 0100 (Option C) = 0101 (binary) = 5 (decimal)
```

The combined flags would be represented as 5 (decimal).


## Example: Setting the 2nd bit (0-based index) of the number 8 (1000 in binary) to 1

Step 1: Create a bitmask with a 1 at the position of the bit you want to set and 0s elsewhere.
+ **WHY ?** any operand bit ORed with 1 will give you 1. (1 | 1 == 1) and (0 | 1 == 1) this will set anything to 1
```
Bitmask:   0010
```

Step 2: Perform the bitwise OR operation between the number (8) and the bitmask.
```
   1000  (Number: 8)
 | 0010 (Bitmask)
---------
   1010  (Result: 10)
```

In this example, the 2nd bit of the number 8 (1000) is not set (equals 0). When you perform the OR operation with the bitmask (0010), you set the 2nd bit to 1, resulting in the number 10 (1010 in binary).

Now the number 10 has the 2nd bit set to 1:
```
Number:  1010
           ^
           |
          2nd bit (set to 1)
```

## Test Question
Suppose we have the number 18 (10010 in binary). Set the 3rd bit (0-based index) to 1 using the OR operator.


## Use Cses of |
The bitwise OR operator (|) is a fundamental bit manipulation operation that has several use cases in programming. Here are some common scenarios where the bitwise OR operator is employed:

1. **Setting Specific Bits:** As we've discussed earlier, the OR operator is used to set specific bits to 1 in an integer. By ORing the integer with a bitmask that has a 1 at the desired bit position, you can efficiently set that bit without affecting other bits.

2. **Combining Flags and Options:** The OR operator is commonly used to combine individual flags or options to represent a combined configuration or state. Each flag is represented by a different bit in an integer, and ORing multiple flags allows you to represent complex combinations.

3. **Adding Values in Bit Form:** When you want to perform addition or merging operations on two numbers represented in their binary form, you can use the OR operator. This can be useful in certain bitwise arithmetic operations.

4. **Bitmasking and Filtering:** In bitmasking, you can use the OR operator to create a mask with multiple bits set to 1, representing specific data patterns. This mask can then be used to filter out relevant data or perform bitwise operations selectively.

5. **Setting Multiple Bits at Once:** The OR operator allows you to set multiple bits to 1 in a single operation. This can be particularly useful when initializing certain data structures or configurations.

6. **Data Encoding and Compression:** In some data encoding or compression techniques, the OR operator is used to combine multiple values or flags into a compact representation. This can be advantageous in scenarios where space efficiency is critical.

7. **Permissions and Access Control:** In security systems and access control mechanisms, bitwise OR is used to define and combine different permissions for different user roles or groups.

8. **Creating Bit Patterns and Masks:** The OR operator is useful for creating custom bit patterns or masks to perform various bitwise operations.

Overall, the bitwise OR operator is an essential tool for manipulating individual bits and performing bitwise operations efficiently. Its usage extends across various domains, including systems programming, networking, security, and optimization tasks.

By understanding the applications of the OR operator, you can develop more efficient and elegant solutions to various programming problems. Remember to always be mindful of the bit positions and the impact of bitwise operations on your data.
