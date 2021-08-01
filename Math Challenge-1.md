Math Challenge

Have the function MathChallenge(num) read the num parameter being passed which will be a combination of 1 or more single digits, and determine if it's possible to separate the digits with either a plus or minus sign to get the final expression to equal zero. For example: if num is 35132 then it's possible to separate the digits the following way, 3 - 5 + 1 + 3 - 2, and this expression equals zero. Your program should return a string of the signs you used, so for this example your program should return -++-. If it's not possible to get the digit expression to equal zero, return the string not possible.

If there are multiple ways to get the final expression to equal zero, choose the one that contains more minus characters. For example: if num is 26712 your program should return -+-- and not +-+-.

Examples
```
Input: 199
Output: not possible
```
```
Input: 26712
Output: -+--
```

Solution
```
function MathChallenge(num) { 
  var arrnum = num.toString().split('').map(x => parseInt(x))
  var posibilities = []

  const traverse = ([d, ...rest], comb, sum) => {
    if(rest.length == 0) {
      if (sum + d == 0) posibilities.push(comb + "+")
      if (sum - d == 0) posibilities.push(comb + "-")
    } else {
      traverse(rest, comb + "+", sum + d)
      traverse(rest, comb + "-", sum - d)
    }
  }

  const maxMin = (comb) => {
    return comb.reduce((acc, curr) => [...acc].filter(c => c == '-' ).length > [...curr].filter(c => c == '-').length ? acc : curr)
  }
  // code goes here  
  traverse(arrnum.slice(1), '', arrnum[0])

  return posibilities.length ? maxMin(posibilities) : 'not possible'

}
   
// keep this function call here 
console.log(MathChallenge(readline()));
```
