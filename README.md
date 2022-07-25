- 👋 Hi, I’m @snekhakrish
- 👀 I’m interested in ...
- 🌱 I’m currently learning ...
- 💞️ I’m looking to collaborate on ...
- 📫 How to reach me ...

<!---
snekhakrish/snekhakrish is a ✨ special ✨ repository because its `README.md` (this file) appears on your GitHub profile.
You can click the Preview link to take a look at your changes.
--->
swap number using pointers
#include <stdio.h>
 void swap(int *a,int *b)
{
    int t;
     t   = *a;
    *a   = *b;
    *b   =  t;
}
 
int main()
{
    int num1,num2;
     
   printf("Enter value of num1: ");
   scanf("%d",&num1);
   printf("Enter value of num2: ");
   scanf("%d",&num2);
     
   printf("Before Swapping: num1=%d, num2=%d\n",num1,num2);
   swap(&num1,&num2);
     
   printf("After  Swapping: num1=%d, num2=%d\n",num1,num2);    
     
   return 0;
}
//datastructure
#include<stdio.h>
#include<stdlib.h>
void display();
void delete();
struct node
{
int data;
struct node*next;
}*newnode,*head,*temp,*prev;
void main()
{
    insert();
    display();
    delete();
    display();
}
void insert()
{
    int choice=1;
    do{
        newnode=malloc(sizeof(struct node));
        printf("enter the data");
        scanf("%d",&newnode->data);
        newnode->next=0;
        if(head==0)
        {
            head=newnode;
        }
        else
        {
            temp=head;
            while(temp->next!=NULL)
            {
                temp=temp->next;
            }
            temp->next=newnode;
        }
        printf("enter the choice");
        scanf("%d",&choice);
    }while(choice);
}
void display()
{
    temp=head;
    while(temp->next!=NULL)
    {
        printf("%d",temp->data);
        temp=temp->next;
    }
    printf("%d",temp->data);
}
void delete()
{
    int element;
    printf("enter the element to be deleted");
    scanf("%d",&element);
    temp=head;
    while(temp->data!=element)
    {
        prev=temp;
        temp=temp->next;
    }
    prev->next=temp->next;
    free(temp);
}
  Output:
  enter data:7
  enter choice:1
  enter data:9
  enter choice:1
  enter choice:8
  enter choice:0
  7 9 8 enter the element to be deleted:9
  7 8
  
  Using malloc
#include<stdio.h>
#include<stdlib.h>
int main()
{
    int i,n;
    printf("enter the number of val");
    scanf("%d",&n);
    int *ptr=(int*)malloc(n*sizeof(int));
    if(ptr==NULL)
    {
        printf("memory is not allocated");
        exit (1);
    }
    for(i=0;i<n;i++)
    {
        printf ("enter a val");
        scanf("%d",ptr+i);
    }
    for(i=0;i<n;i++)
    {
        printf("%d ",*(ptr+i));
     }
    return 0;
    }


Dangling pointer
#include <stdio.h>
int*fun()
{
    int num=10;
    return &num;
}
int main(){
    int *ptr=NULL;
    ptr=fun();
    printf("%d",*ptr);
    return 0;

}
   


