##Compound Literals

f(double[]) {20.38, a_value, 9.8}); // OK

	- Automatically allocated, neither malloc nor free needed.

-#include <math.h> // NAN
-#include <stdio.h>
-
-double sum(double in[]) {
-	double out = 0;
-	for (int i = 0;  !isnan(in[i]);  ++i) out += in[i];
-	return out;
-}

int main() {

	printf("sum: %g\n", sum((double[]) {1.1, 2.2, 3.3, NAN}));
}

double *list = (double[]) { 1.1, 2.2, 3.3, NAN});

sizeof(list) == sizeof(double*)


##Variadic Macros

-#define forloop(i, loopmax, ...) for (int i=0; i < loopmax; ++i) \
											{__VA_ARGS__}

-int main() {

	int sum = 0;
	forloop(i, 10,
			sum += i;
			printf("sum to %i:\n", i, sum);
	)
}


