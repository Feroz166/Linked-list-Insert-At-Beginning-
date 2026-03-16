# Linked-list-Insert-At-Beginning-

<blr>
  Author ~Mohammed Feroz
<blr>
  
This C program implements a singly linked list with insertion at the beginning. It dynamically creates nodes using malloc, stores user input values, and links them together. Finally, it displays the list in the format data -> data -> ... -> NULL, demonstrating basic linked list operations in C.

code 
#include<stdio.h>
#include<stdlib.h>
struct node
{
    int data;
    struct node* next;
};
void insertAtBeg(struct node** head,int val)
{
    struct node* newnode = (struct node*)malloc(sizeof(struct node));
    newnode->data=val;
    newnode->next=*head;
    *head = newnode;
}  
void display(struct node* head)
{
    struct node* temp=head;
    while(temp!=NULL) //last node we want as null
    {
        printf("%d->",temp->data);
        temp=temp->next;
    }
    printf("NULL");
}
int main()
{
    struct node*head=NULL;
    int n,val;
    scanf("%d",&n);
    for(int i=0;i<n;i++)
    {
        scanf("%d",&val);
        insertAtBeg(&head,val);
    }
    display(head);
}  
   
