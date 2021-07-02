# Pow(x, n)

Implement pow(x, n), which calculates x raised to the power n (i.e., x^n).

 

_Example 1:_

`
Input: x = 2.00000, n = 10
`

`
Output: 1024.00000
`


_Example 2:_

`
Input: x = 2.10000, n = 3
`

`
Output: 9.26100
`


_Example 3:_

`
Input: x = 2.00000, n = -2
`

`
Output: 0.25000
`

`
Explanation: 2^(-2) = 1/2^2 = 1/4 = 0.25
`
 

_Constraints:_

`
-100.0 < x < 100.0
`

`
-2^31 <= n <= 2^31-1
`

`
-10^4 <= x^n <= 10^4
`


# Solution in JavaScript
```
var myPow = function(x, n) {
    let result = 1, isReady = true;
    if (n === 0 || x === 1) return 1;
    
    if (x === -1 && n % 2 === 0) return 1;
    
    if (x === -1 && n % 2 === 1) return -1;
    
    if (n < 0) {
        n = -n;
        isReady = false;
    }
    
    while (n > 0) {
        result *= x;
        n--;
    }
    
    return isReady ? result : (1 / result);
};
```
