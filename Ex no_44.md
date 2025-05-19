# EX 44 C functions to perform enqueue, dequeue, display, peek in Queue using Array.
## DATE:19/05/25
## AIM:
To write a C Write a functions to perform enqueue, dequeue, display, peek in Queue using Array.

## Algorithm
1. Analyze the question
2. Follow the algorithm
3. Try the code
4.  Check for error
5. Run & Display the output

## Program:
```
/*
C functions to perform enqueue, dequeue, display, peek in Queue using Array.
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

// Initialize the queue
void init(Queue *q) {
    q->front = -1;
    q->rear = -1;
}

// Check if queue is empty
int isEmpty(Queue *q) {
    return (q->front == -1);
}

// Check if queue is full
int isFull(Queue *q) {
    return (q->rear == MAX - 1);
}

// Enqueue operation
void enqueue(Queue *q, int value) {
    if (isFull(q)) {
        printf("Queue Overflow\n");
        return;
    }
    if (isEmpty(q)) {
        q->front = 0;
    }
    q->arr[++(q->rear)] = value;
    printf("Enqueued %d\n", value);
}

// Dequeue operation
int dequeue(Queue *q) {
    if (isEmpty(q)) {
        printf("Queue Underflow\n");
        return -1;  // Error code
    }
    int val = q->arr[q->front];
    if (q->front == q->rear) {
        // Queue has only one element, reset after dequeue
        q->front = -1;
        q->rear = -1;
    } else {
        q->front++;
    }
    printf("Dequeued %d\n", val);
    return val;
}

// Peek operation (view front element)
int peek(Queue *q) {
    if (isEmpty(q)) {
        printf("Queue is empty\n");
        return -1;  // Error code
    }
    return q->arr[q->front];
}

// Display queue elements
void display(Queue *q) {
    if (isEmpty(q)) {
        printf("Queue is empty\n");
        return;
    }
    printf("Queue elements: ");
    for (int i = q->front; i <= q->rear; i++) {
        printf("%d ", q->arr[i]);
    }
    printf("\n");
}

int main() {
    Queue q;
    init(&q);

    enqueue(&q, 10);
    enqueue(&q, 20);
    enqueue(&q, 30);

    display(&q);

    printf("Peek element: %d\n", peek(&q));

    dequeue(&q);
    display(&q);

    dequeue(&q);
    dequeue(&q);
    dequeue(&q);  // Attempt to dequeue from empty queue

    return 0;
}


## Output:
Enqueued 10
Enqueued 20
Enqueued 30
Queue elements: 10 20 30 
Peek element: 10
Dequeued 10
Queue elements: 20 30 
Dequeued 20
Dequeued 30
Queue Underflow



## Result:
Thus the program was executed and the output was verified successfully.
