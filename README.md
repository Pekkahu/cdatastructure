# c codes for DSA
```c
#include<stdio.h>
#include<conio.h>
#define MAX 10

int top = -1;

void push(int stack[MAX])
{
	int data;
	printf("\n Enter data:");
	scanf("%d", &data);
	if(top == MAX-1)
		printf("Stack is full");
	else
	{
		top++;
		stack[top] = data;
	}
}

void display(int stack[MAX])
{
	int i;
	if(top == -1)
		printf("\n Stack is empty");
	else
	{
		for(i=top; i>=0; i--)
		{
			printf("\n %d", stack[i]);
		}
	}
}
void pop(int stack[MAX])
{
	if(top == -1)
	{
		printf("\n Stack is empty");
	}
	else
	{
		printf("\n Popped element = %d",stack[top]);
		top--;
	}
}

void peek(int stack[MAX])
{
	if(top == -1)
	{
		printf("\n Stack is empty");
	}
	else
	{
		printf("\n Topmost element = %d",stack[top]);
	}
}

void stackempty()
{
	if(top == -1)
		printf("\n Stack is empty");
	else
		printf("\n Stack is not empty");
}

void stackfull()
{
	if(top == MAX-1)
		printf("\n Stack is full");
	else
		printf("\n Stack is not full");
}

int main()
{
	int ch, n, i, val;
	int stack[MAX];
	clrscr();
	do
	{
		printf("\n Menu \n 1.Push \n 2.Display \n 3.Pop \n 4.Peek \n 5.Stackempty");
		printf("\n 6.Stackfull \n 7.Exit \n Enter your choice");
		scanf("%d", &ch);
		switch(ch)
		{
			case 1:
				printf("\n Enter no of elements:");
				scanf("%d", &n);
				for(i=1; i<=n; i++)
					push(stack);
				break;
			case 2:
				display(stack);
				break;
			case 3:
				/*val = pop(stack);
				if(val != -1)
					printf("\n Popped element = %d", val);*/
				pop(stack);
				break;
			case 4:
				peek(stack);
				break;
			case 5:
				stackempty();
				break;
			case 6:
				stackfull();
				break;
			case 7:
				exit(0);
		}
	}while(ch!=7);
	getch();
	return 0;
}
```
