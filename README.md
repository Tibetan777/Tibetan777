#include <stdio.h>
#include <stdlib.h>
#include <conio.h>

#define true 1
#define false 0

typedef int boolean;

// โครงสร้างข้อมูล node
struct node {
int item;
struct node* next;
};

// ประกาศตัวแปร global
static struct node *newNode;
static struct node *head;
static struct node *curr;
static struct node *prev;

// ฟังก์ชันสร้าง node
struct node* createNode(int item, struct node* next) {
struct node* newNode = (struct node*)malloc(sizeof(struct node));
newNode->item = item;
newNode->next = next;
return newNode;
}

int getItem(struct node* node) {
return node->item;
}

struct node* getNext(struct node* node) {
return node->next;
}

void setNext(struct node* node, struct node* next) {
node->next = next;
}

// ฟังก์ชันเพิ่มข้อมูลเข้าไปใน Linked List
void add(int newItem) {
if(head == NULL) {
newNode = createNode(newItem, NULL);
head = newNode;
}
else {
newNode = createNode(newItem, head);
head = newNode;
}
}

boolean searchItem(int item) {
curr = head;
prev = NULL;
boolean status = false;
while(curr != NULL) {
if(getItem(curr) == item) {
status = true;
break;
}
else {
prev = curr;
curr = getNext(curr);
}
}
return status;
}

void deleteNode(int item) {
if(searchItem(item)) {
if(prev == NULL) {
head = getNext(head);
}
else {
setNext(prev, getNext(curr));
}
}
else {
printf("Not found item.\n");
}
}

void insertNode(int iteminsert, int newitem) {
newNode = createNode(newitem, NULL);
if(searchItem(iteminsert)) {
if(prev == NULL) {
setNext(newNode, head);
head = newNode;
}
else {
setNext(newNode, curr);
setNext(prev, newNode);
}
}
else {
if(head == NULL) {
setNext(newNode, NULL);
head = newNode;
}
else if(curr == NULL) {
setNext(prev, newNode);
}
}
}

void showdata(void) {
curr = head;
while(curr != NULL) {
printf("%d ", getItem(curr)); // แสดงข้อมูลใน Linked List
curr = getNext(curr);
}
printf("\n");
}

int main(void) {
head = NULL; // กำหนดค่าเริ่มต้นของ head

add(8);
printf("Add 8 : ");
showdata();

add(9);
printf("Add 9 : ");
showdata();

add(10);
printf("Add 10 : ");
showdata();

add(11);
printf("Add 11 : ");
showdata();

add(12);
printf("Add 12 : ");
showdata();

deleteNode(9);
printf("Delete 9 : ");
showdata();

deleteNode(11);
printf("Delete 11 : ");
showdata();

insertNode(12, 13);
printf("Insert 13 before 12 : ");
showdata();

insertNode(10, 11);
printf("Insert 11 before 10 : ");
showdata();

insertNode(8, 9);
printf("Insert 9 before 8 : ");
showdata();

insertNode(18, 5);
printf("Insert 5 at last Link List: ");
showdata();

printf("\nPress any key to continue...");
getch();
return 0;
}

