C Macro rules:

Parens:
#define double(x) (2*(x))

Avoid double usage:

Curly braces for blocks:
#define doubleIncrement(a, b) \
	(a)++; \
	(b)++;

Can be wrong by putting it in an if statement:
If (x > y)
	DoubleIncrement(x, y);

NOTE: Variables declared inside a block can conflict with variables declared outside the block.
Solution: Put curly braces around your define block.

Example:
#define sum(max, out) { \
				\
	Int total = 0;           \
	…….                         \
}

To check macros, use -E flag in gcc to only run the preprocessor, printing the expanded version of everything to stdout.

The Preprocessor
