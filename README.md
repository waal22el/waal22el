
#include <stdio.h>
#include <stdlib.h>
#include <string.h>

#ifndef LAB_LISTS_H /* Include guard */
#define LAB_LISTS_H
/*
* A structure implementing a linked list node for the phone directory
* Every linked list node shall contain:
* - A phone number, e.g. as a string of digits.
* The phone no. also functions as the ID of a record.
* - The name of a person having this phone number.
* (it can be first name, last name or both names)
* - A pointer to the next node of a list.
*/
struct node;
{
    int phone_number;
    char name[50];
    struct node *next;
}
/*
* Displays all records in the telephone directory.
* Input:
* - the pointer to the start node of the list
* Otput for each record:
* - the ordinal number of the record in the directory
* - the phone no.
* - the name
*/
void display(struct node *start)
{
    int ordinal = 1;
    while(start != NULL)
    {
        printf("%d. Number: %d, Name: %s\n", ordinal, start->phone_number, start->name);
        start = start->next;
        ordinal++;
    }
}
/*
* Inserts a new record at the beginning of the directory.
* Fist checks that the record already exists -
* duplicates are not allowed.
* Input:
* - the pointer to the pointer to the first list node
* Returns:
* 0 if the insertion is successful,
* -1 if the node already exists in the directory
*/
int insert_record(struct node **start);
{
    int new_phone;
    char new_name[50];
    printf("Enter phone number: ");
    scanf("%d, &new_phone");
}
/*
* Deletes a record with the given phone no.
* If the record does not exist, the deletion is unsuccessful.
* Inputs:
* - the pointer to the pointer to the first list node
* - the phone no.
* Returns:
* 0 if successful,
* -1 otherwise.
*/
int delete_record(struct node **start, int num);
/*
* Queries the directory by phone no. or name
* Inputs:
* - the pointer to the first list node
* - option flag that is set to 1 to search by phone
* or 2 to search by name
* - the phone no. or name
* Returns
* - the pointer to the found record or NULL if not found
*/
struct node *query_directory(struct node *start, int num, char *name, int option);
/*
* Deletes all records in the telephone directory
* and sets the start pointer to NULL.
* It is supposed to be called before exiting.
* Input:
* - the pointer to the pointer to the first list node
*/
void delete_directory(struct node **start);
#endif // LAB_LISTS_H
