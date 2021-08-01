String Challenge

Have the function StringChallenge(str) take the str parameter being passed and capitalize the first letter of each word. Words will be separated by only one space.

Examples

```
Input: "hello world"
Output: Hello World
```
```
Input: "i ran there"
Output: I Ran There
```

Solution

```
function StringChallenge(str) { 
  var arrstr = str.split(" ");
  for(i = 0 ; i < arrstr.length; i++) {
    arrstr[i] = arrstr[i][0].toUpperCase() + arrstr[i].slice(1)
  }

  // code goes here  
  return arrstr.join(' '); 

}
   
// keep this function call here 
console.log(StringChallenge(readline()));
```
