#include<stdio.h>
#include<stdlib.h>
#define size 10
void insert(int value,int key);
struct node *searchval(int item,int key);
void deletenode(int item,int key);
void display();
int hashcode(int key);
struct node {
	int info;
	int key;
	struct node *link;
};
struct node *array[size];
struct node *delitem, *sptr;
int key,item,option;

int main()
{
do
{
printf("1.\nCreate a Hash Table for separate chaining\n");
printf("2.Searching an item from the Hash Table\n");
printf("3.Delete an item from Hash Table\n");
printf("4.Display the Hash Table\n");
printf("5.Exit from the program\n");
printf("\nEnter your choice");
scanf("%d", &option);
switch(option)
{
    case 1:
       printf("Enter -1 to terminate");
       printf("Enter the data item");
       scanf("%d",&item);
       printf("Enter the key value");
       scanf("%d",&key);
       while(item!=-1||key!=-1)
       {
       insert(item,key);
       printf("Enter the data item");
       scanf("%d",&item);
       printf("Enter the key value");
       scanf("%d",&key);
       }
       printf("Hash Table is created");
       break;
    case 2:
       printf("Enter the data item you want to search");
       scanf("%d",&item);
       printf("Enter the key value of the data");
       scanf("%d",&key);
       sptr=(struct node *)malloc(sizeof(struct node));
       sptr=searchval(item,key);
       if(sptr==NULL)
          printf("Item %d with key value %d is not present",item,key);
       else
          printf("Item %d with key value %d is found at location %d",item,key,sptr);
       break;
    case 3:
       printf("Enter the data item you want to delete");
       scanf("%d",&item);
       printf("Enter the key value of the data");
       scanf("%d",&key);
       deletenode(item,key);
       break;
     case 4:
       display();
       break;
}
   }while(option<=4);
  return 0;
}

int hashcode(int key)
{
	return key%size;
}

void insert(int value,int key)
{
	struct node *new=(struct node*)malloc(sizeof(struct node));
    new->info=value;
    new->key=key;
    new->link=NULL;
    int index=hashcode(key);
    while(array[index]!=NULL && array[index]->key!=-1)
    {
    	++index;
    	index%=size;
    }
    array[index]=new;
}

struct node *searchval(int item,int key)
{
	int index=hashcode(key);
	while(array[index]!=NULL)
	{
		if(array[index]->key==key)
		{
			return array[index];
		}
       ++index;
       index%=size;
	}
	return NULL;
}

void deletenode(int item,int key)
{
	int index=hashcode(key);
	while(array[index]!=NULL)
	{
		if(array[index]->key==key)
		{
			struct node *temp=array[index];
			array[index]=delitem;
		//	return temp;
		}
		++index;
		index%=size;
	}
}

void display()
{
	int i=0;
	for(i=0;i<size;i++)
	{
		if(array[i]!=NULL)
		{
			printf("(%d,%d)",array[i]->key,array[i]->info);
		}
		else
			printf("(NULL)");
	}
	printf("\n");
}
