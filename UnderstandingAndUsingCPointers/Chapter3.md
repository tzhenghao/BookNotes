Function pointers :

Cons : slower running program.

Using a function pointer:

Int  (*fptr1)(int);

Int square(int num) {
	Return num * num;
}


Int n = 5;
Fptr1 = square;
Printf("%d squared is %d\n",  n, fptr1(n));

Fptr1 = &square; // This is redundant - no need for address of operator

Typedef int (*funcptr)(int);
…
Funcptr fptr2;
Fptr2 = square;
……
