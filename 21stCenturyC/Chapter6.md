Keep scope of variables as small as possible

Another benefit: declaration-in-loop form will be easier to parallelize with OpenMP.

Will this new syntax slow my program? Answer: NO

Compiler's first step is to parse the code into a language-independent internal representation.

Pthread_t *threads;
Int thread_count;
Thread_count = atoi(argv[1]);
Threads = malloc(thread_count *sizeof(pthread_t));
…
…
Free(threads);

We can write this instead:

Int thread_count = atoi(argv[1]);
Pthread_t threads[thread_count];
…

No need to free!!!

Cast Less
----------------

Don't bother casting toomuch as malloc returns a void * type.

We can safely do: param_struct *params = params_in; // params_in is a void * type.

If it's valid to assign an item of one type to an item of another type, then C will do it for you without needing you to explicitly cast it.

NOTE: This is not true for C++, which depends more on types and therefore requires casts to be explicit.

Gotos do not allow a return in the middle of a parallelized block.
In order to stop execution, you need either a lot of if statements, or a goto at the end of the block.

Goto - useful for cleaning up on the way out of a single function.

Three go-to-the-exit functions:
	1. Exit
	2. Quick_exit
	3. _exit

At_exit and at_quick_exit functions - able to register cleanup operations.

At_quick_exit - does not close streams or flush buffers.

_Exit function leaves as quickly as possible - no registered function calls, no buffers flushed.

_Noreturn keyword - tells compiler no need to prepare return information for the function.


Deprecated Float
----------------

	- Use higher level prevision for intermediate variables - avoid incremental roundoff problems.
	- C will force signed type to an unsigned during comparison.

Safely Parse Strings to Numbers

Atoi and atof -  no error-checking - Example: twelve = "XII"; atoi(twelve) will return 0!

Safer to use strtol and strtod.

Making Exceptional Numeric Values with NaNs
----------------

NaN - indicates math error like 0/0 or log(-1)

NaN test for equality ALWAYS FAILS!, even x==x
Solution: Use isnan(x) to test whether x is NaN.
