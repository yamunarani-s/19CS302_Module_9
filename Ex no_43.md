# EX 43 C program to Write a function to display queue elements using array.
## DATE:19/05/25
## AIM:
To Write a function to display queue elements using array.

## Algorithm
1. Analyze the question
2. Follow the algorithm
3. Try the code
4.  Check for error
5. Run & Display the output

## Program:
```
/*
C program to write a function to display queue elements using array.
Developed by: 
RegisterNumber:  
*/
```
#include <stdio.h>
#define MAX 100

typedef struct {
    int arr[MAX];
    int front, rear;
} Queue;

// Initialize queue
void init(Queue *q) {
    q->front = -1;
    q->rear = -1;
}

// Function to display queue elements
void display(Queue *q) {
    if (q->front == -1) {
        printf("Queue is empty\n");
        return;
    }
    printf("Queue elements: ");
    for (int i = q->front; i <= q->rear; i++) {
        printf("%d ", q->arr[i]);
    }
    printf("\n");
}

// Sample enqueue function to help testing
void enqueue(Queue *q, int value) {
    if (q->rear == MAX - 1) {
        printf("Queue Overflow\n");
        return;
    }
    if (q->front == -1) q->front = 0;
    q->arr[++(q->rear)] = value;
}

int main() {
    Queue q;
    init(&q);

    enqueue(&q, 10);
    enqueue(&q, 20);
    enqueue(&q, 30);

    display(&q);

    return 0;
}

## Output:


Queue elements: 10 20 30 

## Result:
Thus the program was executed and the output was verified successfully.
