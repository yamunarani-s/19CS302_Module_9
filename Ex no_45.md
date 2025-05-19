# EX 45 C program that implements a queue using an array, and performs insertion (enqueue) and display operations.
## DATE: 19/05/25
## AIM:
To write a C program that implements a queue using an array, and performs insertion (enqueue) and display operations. 

## Algorithm
1. Analyze the question
2. Follow the algorithm
3. Try the code
4.  Check for error
5. Run & Display the output
## Program:
```
/*
C program that implements a queue using an array, and performs insertion (enqueue) and display operations.
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

void init(Queue *q) {
    q->front = -1;
    q->rear = -1;
}

int isFull(Queue *q) {
    return (q->rear == MAX - 1);
}

int isEmpty(Queue *q) {
    return (q->front == -1);
}

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

    enqueue(&q, 5);
    enqueue(&q, 10);
    enqueue(&q, 15);

    display(&q);

    return 0;
}


## Output:

Enqueued 5
Enqueued 10
Enqueued 15
Queue elements: 5 10 15 

## Result:
Thus the program was executed and the output was verified successfully.
