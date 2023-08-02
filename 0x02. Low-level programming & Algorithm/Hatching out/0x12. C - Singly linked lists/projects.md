# task 0
```c
// Online C compiler to run C program online
#include <stdio.h>
#include <stdlib.h>
#include <string.h>

/**
 * struct list_s - singly linked list
 * @str: string - (malloc'ed string)
 * @len: length of the string
 * @next: points to the next node
 *
 * Description: singly linked list node structure
 */
typedef struct list_s
{
    char *str;
    unsigned int len;
    struct list_s *next;
} list_t;

// typedef struct node
// {
//     char *str;
//     unsigned int len;
//     struct node *next;
// } node;

size_t print_list(const list_t *h);

/**
 * main - check the code
 *
 * Return: Always 0.
 */
int main(void)
{
    list_t *head;
    list_t *new;
    list_t hello = {"World", 5, NULL};
    size_t n;

    head = &hello;
    new = malloc(sizeof(list_t));
    if (new == NULL)
    {
        printf("Error\n");
        return (1);
    }
    new->str = strdup("Hello");
    new->len = 5;
    new->next = head;
    head = new;
    n = print_list(head);
    printf("-> %lu elements\n", n);

    printf("\n");
    free(new->str);
    new->str = NULL;
    n = print_list(head);
    printf("-> %lu elements\n", n);

    free(new);
    return (0);
}

// int main() {
//     /**
//      * CREATING A SINGLY LINKED LIST
//      * 1. allocate memory to each node
//      * 2. set the datas
//      * 3. set the pointer to point to the next node
//      * 4. manually set a variable to point to head
//      * 5. free memory
//      */
    
//     list_t *head;
//     size_t num;
//     /** allocate memory for each node */
//     list_t *node_one = malloc(sizeof(list_t));
//     list_t *node_two = malloc(sizeof(list_t));
//     list_t *node_three = malloc(sizeof(list_t));
    
//     /** 2. set datas & 3 set pointers to next nodes*/
//     node_one -> str = NULL;
//     node_one -> next = node_two;
    
//     node_two -> str = "two";
//     node_two -> next = node_three;
    
//     node_three -> str = "three";
//     node_three -> next = NULL;
    
//     /** manually set a head pointer to point to the first one */
//     head = node_one;
    
//     num = print_list(head);
//     printf(" %d", num);
    
    
//     free(node_one);
//     free(node_two);
//     free(node_three);

//     return 0;
// }


/**
 * function returns unsigned int which is the number of nodes
 * function takes a node as parameter
 * 
 * REQUIREMENTS
 * 1. str == NULL, print [0](nil)
 * 2. allowed to use printf
 */
size_t print_list(const list_t *h)
{
    size_t num_of_nodes = 0;
    list_t *current;
    
    current = h;
    while (current != NULL)
    {
        if (current -> str == NULL)
            printf("[0] (nil)\n");
        else
            printf("[%d] %s \n", current -> len, current -> str);
        current = current -> next;
        num_of_nodes++;
    }
    
    return (num_of_nodes);
}


// node1 ---> node2 ---> node3 ---> NULL
//   ^          
//   |
//  head
//   |
//   h
//   |
// current
```


#task 1
```c
// Online C compiler to run C program online
#include <stdio.h>
#include <stdlib.h>
#include <string.h>

/**
 * struct list_s - singly linked list
 * @str: string - (malloc'ed string)
 * @len: length of the string
 * @next: points to the next node
 *
 * Description: singly linked list node structure
 */
typedef struct list_s
{
    char *str;
    unsigned int len;
    struct list_s *next;
} list_t;

// typedef struct node
// {
//     char *str;
//     unsigned int len;
//     struct node *next;
// } node;

size_t print_list(const list_t *h);
size_t list_len(const list_t *h);
list_t *add_node(list_t **head, const char *str);


/** TASK 0 MAIN */
/**
 * main - check the code
 *
 * Return: Always 0.
 */
// int main(void)
// {
//     list_t *head;
//     list_t *new;
//     list_t hello = {"World", 5, NULL};
//     size_t n;

//     head = &hello;
//     new = malloc(sizeof(list_t));
//     if (new == NULL)
//     {
//         printf("Error\n");
//         return (1);
//     }
//     new->str = strdup("Hello");
//     new->len = 5;
//     new->next = head;
//     head = new;
//     n = print_list(head);
//     printf("-> %lu elements\n", n);

//     printf("\n");
//     free(new->str);
//     new->str = NULL;
//     n = print_list(head);
//     printf("-> %lu elements\n", n);

//     free(new);
//     return (0);
// }

/** MY MAIN */
// int main() {
//     /**
//      * CREATING A SINGLY LINKED LIST
//      * 1. allocate memory to each node
//      * 2. set the datas
//      * 3. set the pointer to point to the next node
//      * 4. manually set a variable to point to head
//      * 5. free memory
//      */
    
//     list_t *head;
//     size_t num;
//     /** allocate memory for each node */
//     list_t *node_one = malloc(sizeof(list_t));
//     list_t *node_two = malloc(sizeof(list_t));
//     list_t *node_three = malloc(sizeof(list_t));
    
//     /** 2. set datas & 3 set pointers to next nodes*/
//     node_one -> str = NULL;
//     node_one -> next = node_two;
    
//     node_two -> str = "two";
//     node_two -> next = node_three;
    
//     node_three -> str = "three";
//     node_three -> next = NULL;
    
//     /** manually set a head pointer to point to the first one */
//     head = node_one;
    
//     num = print_list(head);
//     printf(" %d", num);
    
    
//     free(node_one);
//     free(node_two);
//     free(node_three);

//     return 0;
// }


/** TASK 0 SOLUTION */
/**
 * function returns unsigned int which is the number of nodes
 * function takes a node as parameter
 * 
 * REQUIREMENTS
 * 1. str == NULL, print [0](nil)
 * 2. allowed to use printf
 */
size_t print_list(const list_t *h)
{
    size_t num_of_nodes = 0;
    const list_t *current;
    
    current = h;
    while (current != NULL)
    {
        if (current -> str == NULL)
            printf("[%d] %s\n", 0, "(nil)");
        else
            printf("[%d] %s\n", current -> len, current -> str);
        current = current -> next;
        num_of_nodes++;
    }
    
    return (num_of_nodes);
}


// node1 ---> node2 ---> node3 ---> NULL
//   ^          
//   |
//  head
//   |
//   h
//   |
// current
/** TASK 0 ENDS */






/** TASK 1 STARTS */
/** TASK 1 MAIN */
// int main(void)
// {
//     list_t *head;
//     list_t *new;
//     list_t hello = {"World", 5, NULL};
//     size_t n;

//     head = &hello;
//     new = malloc(sizeof(list_t));
//     if (new == NULL)
//     {
//         printf("Error\n");
//         return (1);
//     }
//     new->str = strdup("Hello");
//     new->len = 5;
//     new->next = head;
//     head = new;
//     n = list_len(head);
//     printf("-> %lu elements\n", n);
//     free(new->str);
//     free(new);
//     return (0);
// }

/**
 * TASK 1
 * 1. prototype: size_t list_len(const list_t *h);
 * 2. function returns variable of type size_t (unsigned int)
 * 3. function takes constant node as parameter (only a constant variable can be assigned to it)
 * 
 * INSTRUCTIONS
 * functions that returns the number of elements in a linked list
 */
size_t list_len(const list_t *h)
{
    size_t num_of_elements = 0;
    const list_t *current = h;
    
    while (current != NULL)
    {
        current = current -> next;
        num_of_elements++;
    }
    
    return (num_of_elements);
}


/** TASK 2 STARTS */
/** TASK 2 MAIN FUNCTION */
// int main(void)
// {
//     list_t *head;

//     head = NULL;
//     add_node(&head, "Alexandro");
//     add_node(&head, "Asaia");
//     add_node(&head, "Augustin");
//     add_node(&head, "Bennett");
//     add_node(&head, "Bilal");
//     add_node(&head, "Chandler");
//     add_node(&head, "Damian");
//     add_node(&head, "Daniel");
//     add_node(&head, "Dora");
//     add_node(&head, "Electra");
//     add_node(&head, "Gloria");
//     add_node(&head, "Joe");
//     add_node(&head, "John");
//     add_node(&head, "John");
//     add_node(&head, "Josquin");
//     add_node(&head, "Kris");
//     add_node(&head, "Marine");
//     add_node(&head, "Mason");
//     add_node(&head, "Praylin");
//     add_node(&head, "Rick");
//     add_node(&head, "Rick");
//     add_node(&head, "Rona");
//     add_node(&head, "Siphan");
//     add_node(&head, "Sravanthi");
//     add_node(&head, "Steven");
//     add_node(&head, "Tasneem");
//     add_node(&head, "William");
//     add_node(&head, "Zee");
//     print_list(head);
//     return (0);
// }

/**
 * TASK 2
 * 
 * DEDUCTION FROM PROTOTYPE
 * 1. prototype: list_t *add_node(list_t **head, const char *str);
 * 2. function should return a pointer
 * 3. the pointer is a pointer to a list_t node
 * 4. function takes 2 parameters
 *      i. double pointer, head
 *      ii. constant string
 * 
 * REQUIREMENTS
 * 1. if failed, return NULL
 * 2. return the address of the new element
 * 3. constant needs to be duplicated
 * 4. we are allowed to use strdup - string
 * 
 * what is strdup?
 * function that duplicates a string
 * prototype: char *strdup(const char *str);
 */
 
list_t *add_node(list_t **head, const char *str)
{
    char *new_str = strdup(str);
    list_t *new_node ;
    
    new_node = malloc(sizeof(list_t));
    if (new_node == NULL) //if memory allocation fails, return NULL
        return (NULL);

    
    new_node -> str = new_str;
    if (new_node -> str == NULL)
    {
        free(new_node);
        return (NULL);
    }
    
    new_node -> len = strlen(str);
    new_node -> next = *head;
    *head = new_node;

    
    return (new_node);
    
    /** if malloc fails, we have to free something
     * if strdup fails, we have to free something.
     */
}


//              head
//               ^
//               |
// new_node -> node1 ---> node2 ---> node3 ---> NULL
//     |
//     v
//   head
/** TASK 2 ENDS */




/** TASK 3 STARTS */

/* TASK 3 MAIN */
int main(void)
{
    list_t *head;

    head = NULL;
    add_node_end(&head, "Anne");
    add_node_end(&head, "Colton");
    add_node_end(&head, "Corbin");
    add_node_end(&head, "Daniel");
    add_node_end(&head, "Danton");
    add_node_end(&head, "David");
    add_node_end(&head, "Gary");
    add_node_end(&head, "Holden");
    add_node_end(&head, "Ian");
    add_node_end(&head, "Ian");
    add_node_end(&head, "Jay");
    add_node_end(&head, "Jennie");
    add_node_end(&head, "Jimmy");
    add_node_end(&head, "Justin");
    add_node_end(&head, "Kalson");
    add_node_end(&head, "Kina");
    add_node_end(&head, "Matthew");
    add_node_end(&head, "Max");
    add_node_end(&head, "Michael");
    add_node_end(&head, "Ntuj");
    add_node_end(&head, "Philip");
    add_node_end(&head, "Richard");
    add_node_end(&head, "Samantha");
    add_node_end(&head, "Stuart");
    add_node_end(&head, "Swati");
    add_node_end(&head, "Timothy");
    add_node_end(&head, "Victor");
    add_node_end(&head, "Walton");
    print_list(head);
    return (0);
}


/**
 * TASK 3
 * 
 * DEDUCTIONS FROM PROTOTYPE
 * 1. prototype: list_t *add_node_end(list_t **head, const char *str);
 * 2. function returns a pointer to a list_t node
 * 3. function takes 2 parameters:
 *      i. head - double pointer
 *      ii. string - constant string
 * 
 * REQUIREMENTS
 * 1. function that adds a new node at the end of a list_t list
 */
 
list_t *add_node_end(list_t **head, const char *str)
{
    
}
```
