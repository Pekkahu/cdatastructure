# c codes for DSA
> stack
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
	int ch, val; //ch varaible is used to choice the function which we have to perform on stack according to the switch case
	int n; // n is used in case 1 of switch for calling push function muiltple times for muiltple push operation
	int i; // i is the variable used in for loop 
	int stack[MAX]; // array size max
	clrscr();
	do
	{
		printf("\n Menu \n 1.Push \n 2.Display \n 3.Pop \n 4.Peek \n 5.Stackempty");
		printf("\n 6.Stackfull \n 7.Exit \n Enter your choice");
		scanf("%d", &ch); // "%d" is used in scanf for taking a input which is of integer type and the &ch is the address 
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
	// getch() function is used to open the terminal after the program is excuted 
	// if getch() is not used it will just open the terminal and close it once the programed is compiled and runned 
	getch();
	return 0;
	// these main function returns a instance of int data type
}
```
