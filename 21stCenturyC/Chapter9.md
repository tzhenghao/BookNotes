##Security

sprintf is effectively deprecated in favor of snprintf, which limits the amount of data written.

Solution: use asprintf.

asprintf returns -1 if memory is exceeded.

We can use a Stopif macro.

Stopif(asprintf(&str, "%s", user_input) == -1, return -1, "asprintf failed.")

NOTE: Always check that strings from untrusted inputs are of sane length.

printf_s, snprintf_s, fprintf_s - intended to be ore secure than no-_s versions.


int main() {

	char *s1 = "Thread";

	char *s2;
	asprintf(&s2, "Floss");
	
	printf("%s\n", s1);
	printf("%s\n", s2);
	
	s2[0] = 'f' // Switch floss to lowercase.
	s1[0] = 't' // Seg fault.
	
	free(s2); // Clean up.
	free(s1); // seg faults
}

char *s3 = strdup("Thread");

The string Thread is still hardcoded into the program, but s3 is a copy of that constant blob, and so can be freely modified as you wish.

If using Autotools:

AC_CHECK_FUNCS([asprintf strdup])

into configure.ac 

Extend strings with asprintf


PROGRAM:int col_number = 3, person_number = 27;

char *q = strdup("select ");
asprintf(&q, "%scol%i \ n", q, col_number);
asprintf(&q, "%sfrom tab \n", q);
asprintf(&q, "%swhere person_id = %i", q, person_number);


OUTPUT:
select col3
from tab
where person_id = 27

Macro to cleanly extend strings (sasprintf.c)

#define Sasprintf(write_to, ...) {

	char *temp_string_for_extend = (write_to);
	asprintf(&(write_to), __VA_ARGS__);
	free(temp_string_for_extend);
}

glitch:

you may forget to initialize q to NULL. freeing this will cause a seg fault.

Unicode
-----------------

code points written in the form U+0000.

UTF-32 (UTF - UCS Transformation Format)
	(UCS - Universal Character Set)
This specifies 4 bytes (32 bits) as the basic unit.
Each character is encoded in a single unit, at the cost of large amounts of padding.
Naive English can be represented with only 7 bits!

UTF-16 - uses 2 bytes; requires some chars to be written down to using 2 bytes only.

The Encoding for C Code
-----------------

	1. The UTF-8 unit is 8 bits == a char. Valid to write a UTF-8 string to a char *string, with naive English text.
	2. first 128 Unicode code points exactly match ASCII. A is 41 (hexadecimal) in ASCII == Unicode code point U+0041.
	3. U+0000 is a valid code point, which C programmers like to write as '\0'
	4. UTF-16 and UTF-32 - for naive English, very good chance a lot of zero paddings.

Partial list of standard library funcitons that are UTF-8 safe:
	1. strdup and strndup
	2. strcat and strncat
	3. strcpy and strncpy
	4. POSIX basename and dirname

Unicode Libraries
-----------------

	- Convert from whatever the rest of the world dumped on us to UTF-8
	- Need gatekeeper functions that encode incoming strings to UTF-8.
	- Decode outgoing strings from UTF-8.

libxml and cURL - well-formed XMl document states its encoding at the header
