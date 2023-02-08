# display-student-information-c
getting student info from user and displaying score above a cretin value.
#include <stdio.h>
#include <stdlib.h>
struct student
{
    char name[20];
    int rollno;
    char branch[20];
    float marks;
};
void main()
{
    struct student *ptr;
    int i;
    int n;
    printf("Enter the Number of Students:\n");
    scanf("%d", &n);
    ptr = (struct student *)malloc(n * sizeof(struct student));
    
    for (i = 0; i < n; ++i)
    {
        printf("\nEnter name: ");
        scanf("%s", (ptr+i)->name);
        printf("\nEnter Roll Number:");
        scanf("%d", &(ptr+i)->rollno);
        printf("\nEnter branch: ");
        scanf("%s", (ptr+i)->branch);
        printf("\nEnter the marks: ");
        scanf("%f", &(ptr+i)->marks);
    }
    printf("\n");
    printf("\nDisplaying Information");
    for (i = 0; i < n ; ++i)
    {
        if ((ptr+i)->marks > 60.0)
        {
            printf("\nName\t: %s", (ptr+i)->name);
            printf("\nRoll no: %d", (ptr+i)->rollno);
            printf("\nBranch: %s", (ptr+i)->branch);
            printf("\nMarks: %.1f", (ptr+i)->marks);
        }
    }
}
