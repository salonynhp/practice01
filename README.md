# practice01
/*Q1: Write a menu driven program to perform insert, delete, and traverse operation on a queue implemented using an array.
	->for insert
	->for delete
	->for traverse
	->for quit*/
#include <stdio.h>
#define MAX 20
void LQinsert();
void LQdelete();
void LQdisplay();

int n,rear = - 1, front = - 1, Lqueue[];
int main()
{   printf("enter size of queue:");
    scanf("%d",&n);
    int CHOICE;
      printf("1.INSERT\n2.DELETE\n3.TRAVERSE\n4.QUIT\n");
    while(CHOICE!=4)
    {

        printf("\nEnter your choice:");
        scanf("%d",&CHOICE);
        printf("\n");
        switch(CHOICE)
        {
            case 1:

                  LQinsert();
                  break;
            case 2:
                  LQdelete();
                  break;
            case 3:
                  LQdisplay();
                  break;
            case 4:
                 break;
            default:
                 printf("\n INVALID CHOICE \n");
        }
    }
}
void LQinsert(){
    int add;
    if (rear == n - 1)
    printf("Queue Overflow\n");
    else
    {
        if (front == - 1)
        front=0;

          printf("Enter the element you want to insert: ");
          scanf("%d",&add);
          rear=rear+1;
          Lqueue[rear]=add;

    }
}
void LQdelete()
{
    if(rear == - 1)
        {
        printf("Queue Underflow\n\n");
        return;
        }
     else
        {
            printf("Element deleted from queue is:%d\n\n",Lqueue[front]);
            if(front==rear)
             {
              front=-1;
              rear=-1;
             }
           else
              front=front+1;

        }
}
void LQdisplay(){
    int i;
    if(rear== -1)
        printf("Queue is empty\n");
    else
        {
        printf("Queue is:\n");
        for(i=front;i<=rear;i++)
            printf("%d\t",Lqueue[i]);
        }
    printf("\n\n");
}
