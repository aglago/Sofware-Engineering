# Structues
In programming, a struct (short for "structure") is a user-defined data type that allows you to group together different variables of different types into a single unit. It is a way to create a composite data type in many programming languages.

## Table of Content
+ [C structures](#c-struct)
+ []()
+ []()

# C struct
In C programming specifically, the `struct` keyword is used to define a structure. Here's the general syntax for defining a struct in C:

```c
struct StructName {
    // Member variables or fields
    data_type1 member1;
    data_type2 member2;
    // ...
};
```

Here's an example of a struct named `Person` that stores information about a person:

```c
struct Person {
    char name[50];
    int age;
    float height;
};
```

In the above example, the `Person` struct has three members: `name`, `age`, and `height`. The `name` member is an array of characters (string) with a maximum length of 50 characters. The `age` member is an integer, and the `height` member is a floating-point number.

To declare variables of the `Person` struct type, you can do the following:

```c
struct Person person1;
struct Person person2;
```

You can access and modify the members of a struct using the dot operator (`.`). For example:

```c
strcpy(person1.name, "John Doe");
person1.age = 30;
person1.height = 175.5;
```

Structs are useful for organizing related data into a single entity, allowing you to pass around or manipulate multiple values at once. They are commonly used in C programming for tasks such as representing records, creating complex data structures, or defining custom data types.
