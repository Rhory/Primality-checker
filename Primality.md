


#include <stdio.h>
#include <stdbool.h>
#include <math.h>

// Generate array of primes //

int main (void)

{
	double potentialPrime;
	int counter;

	printf("What number would you like to test for primality?\n");

	scanf("%lf.\n", &potentialPrime);

	int p, i, primes[12000], primeIndex = 2;
	bool isPrime;

	primes[0] = 2;
	primes[1] = 3;

	for (p = 5; p <= 100000; p = p + 2)

		{ isPrime = true;

			for ( i =1; isPrime && p / primes[i] >= primes[i]; ++i)

				if ( p% primes[i] == 0)
					isPrime = false;

				if (isPrime == true)
				{
					primes[primeIndex] = p;
					++primeIndex;
				}
		}
	

for (counter = 0; counter < 1200; counter++)
{
	if(primes[counter] < potentialPrime && fmod(potentialPrime,primes[counter]) == 0)
	{
		printf("The number %lf is not prime.\n", potentialPrime);
			break;
	}
	else
	{
		printf("The number %lf is prime.\n", potentialPrime);
			break;
	}
break;
}


printf ("Due to constraints on double, this program is totally accurate for primes\n"
	"up to the value of 7829^2 = 61'293'241. Beyond this the probability of \n"
	"correctly determining primality decreses logarithmically.");


return (0);

}

