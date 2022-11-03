# Compute Minimum Number of Coins to Equal a Certain Amount of Money

## Description

You are given an amount of money M and an integer array C[] which contains n-number of coins of different denominations.

Write a program to return the minumum number of coins needed to equal M.

Assume an infinite supply of each kind of coin. 

If any combination of coins cannot make up the required amount, return -1.

Examples:

Input coin[] = [25, 10, 5], M = 30, Output: 2 (One 25 and one 5)

Input coin[] = [9, 6, 5, 1], M = 13, Output: 3 (Two 6 and one 1)

Input coin[] = [1, 3, 5, 7], M = 18, Output: 4 Multiple solutions: (Two 7, one 3, and one 5), (Three 5 and one 3), (One 7, two 5, and one 1)

## Algorithms

### Recursive Solution

```
coins[] = array of coin denominations to choose from
m = amount of money
k = length of coins[]
minCount = MAXINT

if m = 0 return 0 (no coins needed)
for I = 1 .. k-1
	if coin[i] <= m
		current count =  minCoin(coin, k, m – count[i])
		if current count != MAXINT and current count + 1 < minCount
			minCount = current count + 1 
```

Time complexity: O(k^m) = exponential



### Dynamic Programming Solution

```coins[] = array of coin denominations to choose from
m = amount of money
k = length of coins[]
change[] = len m+1, stores min coins for each value i

change[0] = 0
initialize change[1..m] = MAXINT
for i = 1..m
    for j = 0..k-1
        if coins[j] <= I
            int sub-result = change[i – coins[j]
            if (sub-result != MAZINT && sub-result + 1 < change[i]
                change[i] = sub-result + 1
return change[m]
```

Time complexity: O(km) = linear



# Dynamic Programming


# Project Templates

See solutions in different languages in the "Templates" directory. Once you decide which language you'd like to use,
simply open that directory in your favorite IDE, and you should be able to run the included unit tests "out of the box".

The recommended IDEs are as follows, but feel free to use whatever IDE you are comfortable with.

-   [C#](Templates/C#) - [Microsoft Visual Studio](https://visualstudio.microsoft.com/vs/community/)
-   [Java](Templates/Java) - [IntelliJ Idea](https://www.jetbrains.com/idea/download) (Community Edition is fine)
-   [JavaScript](Templates/JavaScript) - [Microsoft Visual Studio Code](https://code.visualstudio.com/)
-   [Kotlin](Templates/Kotlin) - [IntelliJ Idea](https://www.jetbrains.com/idea/download) (Community Edition is fine)
-   [TypeScript](Templates/TypeScript) - [Microsoft Visual Studio Code](https://code.visualstudio.com/)
