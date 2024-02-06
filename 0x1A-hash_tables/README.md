0x1A-hash_tables

In C programming, a hash table is a data structure that stores key-value pairs. It uses a hash function to map keys to their corresponding values in the table, allowing for efficient retrieval of data.

The implementation of a hash table in C typically involves the following components:
1. Array: A fixed-size array is used to store the elements of the hash table.
2. Hash function: This function takes a key as input and produces an index in the array where the corresponding value will be stored.
3. Collision handling: Since different keys may hash to the same index (collision), a collision resolution method such as chaining (using linked lists at each array index) or open addressing (probing for alternative locations) is used to handle collisions.

Here's a simple example of how a hash table can be implemented in C using chaining for collision resolution:

```c
#include <stdio.h>
#include <stdlib.h>
#include <string.h>

#define TABLE_SIZE 10

struct Node {
    int key;
    int value;
    struct Node* next;
};

struct Node* hashTable[TABLE_SIZE];

int hashFunction(int key) {
    return key % TABLE_SIZE;
}

void insert(int key, int value) {
    int index = hashFunction(key);
    struct Node* newNode = (struct Node*)malloc(sizeof(struct Node));
    newNode->key = key;
    newNode->value = value;
    newNode->next = NULL;

    if (hashTable[index] == NULL) {
        hashTable[index] = newNode;
    } else {
        struct Node* current = hashTable[index];
        while (current->next != NULL) {
            current = current->next;
        }
        current->next = newNode;
    }
}

int search(int key) {
    int index = hashFunction(key);
    struct Node* current = hashTable[index];
    while (current != NULL) {
        if (current->key == key) {
            return current->value;
        }
        current = current->next;
    }
    return -1; // Key not found
}

int main() {
    // Inserting key-value pairs into the hash table
    insert(10, 100);
    insert(25, 250);
    
    // Searching for a value based on a key
    int result = search(25);
    if (result != -1) {
        printf("Value found: %d\n", result);
    } else {
        printf("Key not found\n");
    }

    return 0;
}
```

In this example, the hash table is implemented using an array of linked lists to handle collisions. The `insert` function adds a new key-value pair to the hash table, and the `search` function retrieves the value associated with a given key. The `hashFunction` calculates the index for storing and retrieving values based on the key.

This is a basic implementation to demonstrate the concept. In practice, more robust error handling and memory management would be necessary.


Requirements
General
Allowed editors: vi, vim, emacs
All your files will be compiled on Ubuntu 20.04 LTS using gcc, using the options -Wall -Werror -Wextra -pedantic -std=gnu89
All your files should end with a new line
A README.md file, at the root of the folder of the project is mandatory
Your code should use the Betty style. It will be checked using betty-style.pl and betty-doc.pl
You are not allowed to use global variables
No more than 5 functions per file
You are allowed to use the C standard library
The prototypes of all your functions should be included in your header file called hash_tables.h
Don’t forget to push your header file
All your header files should be include guarded
