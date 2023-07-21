# Try your hands on these
Here are a few practical test questions that you can try to test your understanding of C programming:


1. Write a program that defines a struct called `Book` to store information about books, including the title, author, and year of publication. Implement the following functions:
   - `void printBook(const struct Book* book)`: Prints the details of a book.
   - `void updateYear(struct Book* book, int newYear)`: Updates the year of publication of a book.
   - `int main()`: Creates a book object, initializes its values, and tests the above functions.

2. 












# Solutions
## Exercise 1
```c
// Online C compiler to run C program online
#include <stdio.h>

/** 
 * creating a struct to 
 * store book details
 */
struct Book 
{
    char *title;
    char *author;
    int year_of_publication;
};

/**
 * printBook - prints details
 * of the book
 * 
 * @book: book whose details are
 * going to be printed.
 */
void printBook(const struct Book* book)
{
    printf("The title of the book is \"%s\"\n", (*book).title);
    printf("\"%s\" was written by %s\n", (*book).title, (*book).author);
    printf("\"%s\" was published in the year %d\n", (*book).title, (*book).year_of_publication);
}

/**
 * updateYear - updates the year
 * of publication of a book
 * 
 * @book: the book
 * @newYear: new year of publication
 */
 void updateYear(struct Book* book, int newYear)
 {
     (*book).year_of_publication = newYear;
 }

int main() {
    /** creating a book object */
    struct Book book;
    book.title = "In the middle of nowhere";
    book.author = "Dzifa Prof";
    book.year_of_publication = 2012;
    
    printBook(&book);
    updateYear(&book, 2016);
    printf("New year of publication of the book is: %d\n", book.year_of_publication);

    return 0;
}
```


## Exercise 2
```c
// Online C compiler to run C program online
#include <stdio.h>

/**
 * Book - struct for book1
 */
struct Book
{
    char title[100];
    char author[100];
    int publication_year;
    float price;
};

int main() {
    /** declaring variables needed */
    int count, i, j;

    /**
     * taking number of books
     * to be recorded
     */
    printf("Enter the number of books: ");
    scanf("%d", &count);
    printf("\n");

    /** initializing book object (array)*/
    struct Book books[count];
    
    /** looping through to take details */
    for (i = 0; i < count; i++)
    {
        printf("Book %d:\n", i + 1);
        printf("Title: ");
        scanf(" %[^\n]", books[i].title);
        printf("Author: ");
        scanf(" %[^\n]", books[i].author);
        printf("Publication Year: ");
        scanf("%d", &books[i].publication_year);
        printf("Price: ");
        scanf("%f", &books[i].price);
    }
    
    /**
     * prints details collected
     */
    printf("Book Details:\n");
    printf("-----------------\n");
    for (j = 0; j < count; j++)
    {
        printf("Book %d:\n", j + 1);
        printf("Title: %s\n", books[j].title);
        printf("Author: %s\n", books[j].author);
        printf("Publication Year: %d\n", books[j].publication_year);
        printf("Price: $%.2f", books[j].price);
        printf("\n");
        printf("\n");
    }

    /** return 0 (integer) when successful */
    return 0;
}
```
