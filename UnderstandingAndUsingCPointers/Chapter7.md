Address Space Layout Randomization (ASLR)
Data Execution Prevention

Funny bug - int * ptr1, ptr2; // WRONG! Ptr1 is an int pointer; ptr2 is an int.
FIX: int *ptr1, *ptr2;

#define PINT int*
PINT ptr1, ptr2; // SAME PROBLEM AS BEFORE!

#typedef int* PINT;
PINT ptr1, ptr2; // OK!
