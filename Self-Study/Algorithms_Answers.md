Add your answers to the Algorithms exercises here.

## Exercise I

a) O(n)
Factoring out n*n from the loop condition, we see that the loop must run 'n'
number of times.

b) O(n*(log(n)**2)*10) => O(n log2(n))
Nesting loops means multiplied complexity. These loops have the complexities of
O(n), O(log n), O(log n), and O(10). Multiplying them and dropping the constant
gives: n*log(n)*log(n), or O(n log2(n))

c) O(n)
Each iteration of bunnyEars only ever calls bunnieEars once with a decreasing
value for the argument 'bunnies'. The result is that the function will
terminate after O(bunnies) amount of time. A more realistic function might be:

def bunny_population(bunnies):
    if bunnies <= 1:
        return bunnies
    return bunny_population(bunnies+1)