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


## Exercise II

Strategy to minimize number of eggs broken:
    1- Go to floor 0.
    2- Select an egg at random.
    3- Drop egg from current floor.
    4- If it breaks, return current floor number.
    5- Retrieve egg and return to collection (it's not broken!).
    6- Go up one floor.
    7- If no floors or eggs remain, raise an exception
    8- Repeat from step 2.

The algorithm will run in linear time, O(n), but the number of eggs broken will
be minimized, as specified.

A more time efficient algorithm (think of all the stairs climbed!) follows:
    1- Go to the "middle" floor.
    2- Select an egg at random
    3- Drop egg from current floor.
    4- If it breaks, select a floor midway between the first and current floors
    5- If it doesn't, select a floor midway between the current and top floors
    6- Continue this process until floors or eggs are exhausted (but swapping
        the lowest and highest floors tested for the top and bottom of the
        building, i.e. a binary search).
    7- Return the lowest floor at which the egg cracked, or raise an exception.