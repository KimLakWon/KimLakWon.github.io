---
title: "C++ 스택 구현"

date: 2019-05-24 17:15:28 -0400

categories: jekyll update

---

# STACK 구현

```c
#include<iostream>

using namespace std;

typedef struct Node* pNode;

typedef struct Node{
	int data;
	pNode next;
}Node;

typedef struct Stack{
	int cnt;
	pNode top;
}Stack;

Stack* InitStack(){
	Stack* stack = new Stack[1];
	stack->cnt = 0;
	stack->top = NULL;
	
	return stack;
}
void DeleteStack(Stack* stack){
	for(;(stack->top)!=NULL;){
		pNode tmpNode = stack->top;
		stack->top = tmpNode->next;
		cout<<"aa"<<endl;
		delete tmpNode;
	}
	delete stack;
}

void Push(Stack* stack, int data){
	pNode tmpNode = new Node[1];
	tmpNode->data = data;
	tmpNode->next = stack->top;
	stack->top = tmpNode;
	stack->cnt++;
}
int IsEmpty(Stack stack){
	return stack.cnt == 0;
}
int Pop(Stack* stack){
	if(IsEmpty(*stack)){
		cout<< "Stack is empty."<<endl;
		return -1;
	}
	pNode tmpNode = stack->top;
	stack->top = tmpNode->next;
	stack->cnt--;
	int data = tmpNode->data;
	delete tmpNode;
	
	return data;
}
int Top(Stack stack){
	if(IsEmpty(stack)){
		cout<< "Stack is empty."<<endl;
		return -1;
	}
	return stack.top->data;
}


int main(){
	
	Stack* myStack = InitStack();
	cout << IsEmpty(*myStack)<<endl;
	Push(myStack, 10);
	Push(myStack, 5);
	cout << IsEmpty(*myStack)<<endl;
	cout << Top(*myStack)<<endl;
	cout << Pop(myStack)<<endl;
	cout << IsEmpty(*myStack)<<endl;
	cout << Top(*myStack)<<endl;
	cout << Pop(myStack)<<endl;
	cout << IsEmpty(*myStack)<<endl;
	cout << Top(*myStack)<<endl;
	cout << Pop(myStack)<<endl;
	DeleteStack(myStack);
	return 0;
}
```
