# EX 41 C program to write a function to find the peek of stack using array.
## DATE: 19/05/25
## AIM:
To write a function to find the peek of stack using array.

## Algorithm
1. Analyze the question
2. Follow the algorithm
3. Try the code
4.  Check for error
5. Run & Display the output

## Program:
```
/*
C program to write a function to find the peek of stack using array.
Developed by: 
RegisterNumber:  
*/
```
#include <stdio.h>
#define MAX 100

// Stack structure
typedef struct {
    int arr[MAX];
    int top;
} Stack;

// Initialize stack
void init(Stack *s) {
    s->top = -1;
}

// Push element into stack
void push(Stack *s, int value) {
    if (s->top == MAX - 1) {
        printf("Stack Overflow\n");
        return;
    }
    s->arr[++(s->top)] = value;
}

// Peek function to return the top element of the stack
int peek(Stack *s) {
    if (s->top == -1) {
        printf("Stack is empty\n");
        return -1;  // or some error code
    }
    return s->arr[s->top];
}

int main() {
    Stack s;
    init(&s);
    push(&s, 10);
    push(&s, 20);
    push(&s, 30);
    int topElement = peek(&s);
    if (topElement != -1) {
        printf("Top element is %d\n", topElement);
    }
    return 0;
}

## Output:


Top element is 30

## Result:
Thus the program was executed and the output was verified successfully.
