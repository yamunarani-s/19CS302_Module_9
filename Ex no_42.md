# EX 42 C program to write a fuctions to perform push,pop,display,peek in stack using array.
## DATE:19/05/25
## AIM:
To write a fuctions to perform push,pop,display,peek in stack using array.

## Algorithm
  
1.Analyze the question
2. Follow the algorithm
3. Try the code
4.  Check for error
5. Run & Display the output
## Program:
```
/*
C program to write a fuctions to perform push,pop,display,peek in stack using array.
Developed by: 
RegisterNumber:  
*/
```
#include <stdio.h>
#define MAX 100

typedef struct {
    int arr[MAX];
    int top;
} Stack;

// Initialize stack
void init(Stack *s) {
    s->top = -1;
}

// Push element onto stack
void push(Stack *s, int value) {
    if (s->top == MAX - 1) {
        printf("Stack Overflow\n");
        return;
    }
    s->arr[++(s->top)] = value;
    printf("Pushed %d\n", value);
}

// Pop element from stack
int pop(Stack *s) {
    if (s->top == -1) {
        printf("Stack Underflow\n");
        return -1;  // error code
    }
    int val = s->arr[s->top--];
    printf("Popped %d\n", val);
    return val;
}

// Peek top element of stack
int peek(Stack *s) {
    if (s->top == -1) {
        printf("Stack is empty\n");
        return -1;  // error code
    }
    return s->arr[s->top];
}

// Display all elements of stack
void display(Stack *s) {
    if (s->top == -1) {
        printf("Stack is empty\n");
        return;
    }
    printf("Stack elements (top to bottom): ");
    for (int i = s->top; i >= 0; i--) {
        printf("%d ", s->arr[i]);
    }
    printf("\n");
}

int main() {
    Stack s;
    init(&s);

    push(&s, 10);
    push(&s, 20);
    push(&s, 30);

    display(&s);

    printf("Peek element is %d\n", peek(&s));

    pop(&s);
    display(&s);

    pop(&s);
    pop(&s);
    pop(&s);  // trying to pop from empty stack

    return 0;
}

## Output:
Pushed 10
Pushed 20
Pushed 30
Stack elements (top to bottom): 30 20 10 
Peek element is 30
Popped 30
Stack elements (top to bottom): 20 10 
Popped 20
Popped 10
Stack Underflow



## Result:
Thus the program was executed and the output was verified successfully.
