%x - Displays the val as hexademical
%o - Displays the val as octal
%p - Displays the val in implementation-specific manner, typically as hexadecimal


Size_t size = sizeof(void *); // legal
Size_t size = sizeof(void) // illegal

Pointers stored in global and static space are initialized to NULL.

Size of pointer depends on the machine in use and the compiler.

Memory Models

Four common pointer-related types:
	1. Size_t
	2. Ptrdiff_t - handle pointer arithmetic
	3. Intptr_t and uintptr_t - storing pointer addresses

size_t:

	- Maximum size any object can be in C.
	- It is an unsigned integer.
	- Return type of sizeof
	- Max possible value for size_t is SIZE_MAX

Size_t sizet = -5
Printf("%d\n", sizet); // -5
Printf("%zu\n", sizet); // 42949…32 (some big ass number)


Size of function pointer varies!

Const int *pci; and int const * pci; are the same!

Int *const cpi = &num; - data pointed to can be modified, but not the pointer itself!

Const int * const cpci = &limit; - cannot change both data and the pointer itself!
