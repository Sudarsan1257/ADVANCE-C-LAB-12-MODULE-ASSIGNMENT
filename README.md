# ADVANCE-C-LAB-12-MODULE-ASSIGNMENT
## EXP NO 26: C PROGRAM TO DISPLAY STACK ELEMENTS USING LINKED LIST.
## Aim:
To write a C program to display stack elements using linked list.

## Algorithm:
1.	Define a structure Node with two members: data to store the integer value and next to point to the next node in the linked list.
2.	Declare a global variable head representing the starting node of the linked list.
3.	Define a function display to print the elements of the linked list.
4.	Declare a pointer p and initialize it with the head of the linked list.
5.	Use a while loop to traverse the linked list:
6.	Print the data of the current node.
7.	Move to the next node using the next pointer.
 
## Program:
```
#include <stdio.h>
#include <stdlib.h>

// Step 1: Define structure Node
struct Node {
    int data;
    struct Node *next;
};

// Step 2: Declare global variable head
struct Node *head = NULL;

// Function to push elements into stack
void push(int value) {
    struct Node *newNode = (struct Node *)malloc(sizeof(struct Node));
    newNode->data = value;
    newNode->next = head;
    head = newNode;
}

// Step 3: Define display function
void display() {
    struct Node *p;        // Step 4: Declare pointer p
    p = head;              // Initialize with head

    // Step 5: Traverse using while loop
    if (p == NULL) {
        printf("Stack is empty.\n");
        return;
    }

    printf("Stack elements are: ");
    while (p != NULL) {
        // Step 6: Print current node data
        printf("%d ", p->data);
        // Step 7: Move to next node
        p = p->next;
    }
    printf("\n");
}

int main() {
    // Example usage
    push(10);
    push(20);
    push(30);
    push(40);

    display();  // Output: 40 30 20 10

    return 0;
}

```

## Output:

<img width="435" height="169" alt="image" src="https://github.com/user-attachments/assets/b3a45559-ec67-42be-a7e6-9480d0fe798d" />



## Result:
Thus, the program to display stack elements using linked list is verified successfully. 



## EXP.NO 27: C PROGRAM TO POP AN ELEMENT FROM THE GIVEN STACK USING LINKED LIST.
## Aim:
To write a C program to pop an element from the given stack using liked list.

## Algorithm:
1.	Check for Empty Stack
2.	If head is equal to NULL, Print "Stack is empty."
3.	Else Proceed to the next step.
4.	Set head to point to the next node in the stack.
 
## Program:
```
#include <stdio.h>
#include <stdlib.h>

// Define structure Node
struct Node {
    int data;
    struct Node *next;
};

// Global variable head (top of stack)
struct Node *head = NULL;

// Function to push element into stack
void push(int value) {
    struct Node *newNode = (struct Node *)malloc(sizeof(struct Node));
    newNode->data = value;
    newNode->next = head;
    head = newNode;
}

// Function to pop element from stack
void pop() {
    // Step 1 & 2: Check for empty stack
    if (head == NULL) {
        printf("Stack is empty.\n");
        return;
    }

    // Step 3 & 4: Remove top element
    struct Node *temp = head;
    printf("Popped element: %d\n", temp->data);
    head = head->next;   // Move head to next node
    free(temp);          // Free memory of removed node
}

// Function to display stack elements
void display() {
    struct Node *p = head;
    if (p == NULL) {
        printf("Stack is empty.\n");
        return;
    }
    printf("Stack elements: ");
    while (p != NULL) {
        printf("%d ", p->data);
        p = p->next;
    }
    printf("\n");
}

int main() {
    // Example usage
    push(10);
    push(20);
    push(30);
    push(40);

    display();   // Output: 40 30 20 10

    pop();       // Removes 40
    display();   // Output: 30 20 10

    pop();       // Removes 30
    display();   // Output: 20 10

    return 0;
}

```

## Output:

<img width="446" height="288" alt="image" src="https://github.com/user-attachments/assets/10199313-2df9-4be9-ba97-f2aaabadd02c" />




## Result:
Thus, the program to pop an element from the given stack using liked list is verified successfully.

 
## EXP NO:28 C PROGRAM TO DISPLAY QUEUE ELEMENTS USING LINKED LIST.
## Aim:
To write a C program to display queue elements using linked list.
## Algorithm:
1.	Check if Queue is Empty
2.	Display Queue Elements
3.	Print the data of the current node pointed to by front
4.	Update front to point to the next node.
5.	End the display function.
 
## Program:
```
#include <stdio.h>
#include <stdlib.h>

// Define structure Node
struct Node {
    int data;
    struct Node *next;
};

// Global variables for front and rear of the queue
struct Node *front = NULL;
struct Node *rear = NULL;

// Function to enqueue (insert) elements into queue
void enqueue(int value) {
    struct Node *newNode = (struct Node *)malloc(sizeof(struct Node));
    newNode->data = value;
    newNode->next = NULL;

    if (rear == NULL) {
        // First element
        front = rear = newNode;
    } else {
        rear->next = newNode;
        rear = newNode;
    }
}

// Function to display queue elements
void display() {
    // Step 1: Check if Queue is Empty
    if (front == NULL) {
        printf("Queue is empty.\n");
        return;
    }

    // Step 2: Display Queue Elements
    struct Node *temp = front;
    printf("Queue elements: ");
    while (temp != NULL) {
        // Step 3: Print data of current node
        printf("%d ", temp->data);
        // Step 4: Update temp to point to next node
        temp = temp->next;
    }
    // Step 5: End display function
    printf("\n");
}

int main() {
    // Example usage
    enqueue(10);
    enqueue(20);
    enqueue(30);
    enqueue(40);

    display();  // Output: 10 20 30 40

    return 0;
}
```

## Output:
<img width="490" height="219" alt="image" src="https://github.com/user-attachments/assets/c1d20591-02b9-4505-a85f-cb62923ed51e" />

## Result:
Thus, the program to display queue elements using linked list is verified successfully.


 
## EXP NO:29 C PROGRAM TO INSERT ELEMENTS IN QUEUE USING LINKED LIST

## Aim:
To write a C program to insert elements in queue using linked list

## Algorithm:
1.	Allocate Memory for New Node
2.	Set Data and Next Pointer
3.	Check if Queue is Empty
4.	Set both front and rear to point to the new node p.
5.	Set the next pointer of the current rear to point to the new node p.
6.	End of Enqueue Operation
 
## Program:
```
#include <stdio.h>
#include <stdlib.h>

// Define structure Node
struct Node {
    int data;
    struct Node *next;
};

// Global pointers for front and rear
struct Node *front = NULL;
struct Node *rear = NULL;

// Function to insert (enqueue) element into queue
void enqueue(int value) {
    // Step 1: Allocate memory for new node
    struct Node *p = (struct Node *)malloc(sizeof(struct Node));
    if (p == NULL) {
        printf("Memory allocation failed!\n");
        return;
    }

    // Step 2: Set data and next pointer
    p->data = value;
    p->next = NULL;

    // Step 3: Check if queue is empty
    if (front == NULL && rear == NULL) {
        // Step 4: Set both front and rear to point to new node
        front = rear = p;
    } else {
        // Step 5: Set next pointer of current rear to new node
        rear->next = p;
        rear = p;
    }

    // Step 6: End of enqueue operation
    printf("Inserted %d into queue.\n", value);
}

// Function to display queue elements
void display() {
    if (front == NULL) {
        printf("Queue is empty.\n");
        return;
    }
    struct Node *temp = front;
    printf("Queue elements: ");
    while (temp != NULL) {
        printf("%d ", temp->data);
        temp = temp->next;
    }
    printf("\n");
}

int main() {
    // Example usage
    enqueue(10);
    enqueue(20);
    enqueue(30);
    enqueue(40);

    display();  // Output: Queue elements: 10 20 30 40

    return 0;
}

```

## Output:
<img width="443" height="275" alt="image" src="https://github.com/user-attachments/assets/e6273ef3-0423-4f44-99c3-c4c5e3299157" />


## Result:
Thus, the program to insert elements in queue using linked list is verified successfully.



## EXP NO:30 C FUNCTION TO FIND THE PEEK OF QUEUE USING LINKED LIST.


## Aim:

The aim of this function is to retrieve the "peek" (the front element) of a queue implemented using a linked list

## Algorithm:

1.	Check if the queue is empty:
o	If the queue is empty (i.e., the front pointer is NULL), return an error or a message indicating that the queue is empty.
2.	Access the front element:
o	If the queue is not empty, return the data stored in the front node of the linked list (i.e., the element at the head of the queue).

## Program:
```
#include <stdio.h>
#include <stdlib.h>

// Define structure Node
struct Node {
    int data;
    struct Node *next;
};

// Global pointers for front and rear
struct Node *front = NULL;
struct Node *rear = NULL;

// Function to enqueue (insert) element into queue
void enqueue(int value) {
    struct Node *newNode = (struct Node *)malloc(sizeof(struct Node));
    newNode->data = value;
    newNode->next = NULL;

    if (front == NULL && rear == NULL) {
        front = rear = newNode;
    } else {
        rear->next = newNode;
        rear = newNode;
    }
}

// Function to peek (front element of queue)
int peek() {
    // Step 1: Check if queue is empty
    if (front == NULL) {
        printf("Queue is empty.\n");
        return -1;  // return error value
    }

    // Step 2: Access front element
    return front->data;
}

// Function to display queue elements
void display() {
    if (front == NULL) {
        printf("Queue is empty.\n");
        return;
    }
    struct Node *temp = front;
    printf("Queue elements: ");
    while (temp != NULL) {
        printf("%d ", temp->data);
        temp = temp->next;
    }
    printf("\n");
}

int main() {
    // Example usage
    enqueue(10);
    enqueue(20);
    enqueue(30);

    display();   // Output: Queue elements: 10 20 30

    int frontElement = peek();
    if (frontElement != -1) {
        printf("Peek element: %d\n", frontElement);  // Output: Peek element: 10
    }

    return 0;
}

```

## Output:
<img width="444" height="195" alt="image" src="https://github.com/user-attachments/assets/75fbe671-f180-48a1-9593-2a326bc4f4d1" />




## Result:

Thus, the program to retrieve the "peek" (the front element) of a queue implemented using a linked list is verified successfully.

