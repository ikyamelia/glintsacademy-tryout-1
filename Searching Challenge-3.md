Searching Challenge\

Have the function `SearchingChallenge(str)` take the str parameter being passed and return the first word with the greatest number of repeated letters. For example: "Today, is the greatest day ever!" should return greatest because it has 2 e's (and 2 t's) and it comes before ever which also has 2 e's. If there are no words with repeating letters return -1. Words will be separated by spaces.

Examples
```
Input: "Hello apple pie"
Output: Hello
```
```
Input: "No words"
Output: -1
```

Solution
```
function SearchingChallenge(str) { 
  var arrstr = str.split(' ')
  var result = -1

  for(i = 0; i < arrstr.length ; i++ ) {
    if (checkString(arrstr[i] , 0)) {
      result = arrstr[i]
      break
    }
  }

  // code goes here  
  return result; 

}

function checkString(text, index) {
  if ((text.length - index) == 0) return false
  else {
    return checkString(text, index + 1) 
    || text.substr(0, index).indexOf(text[index]) != -1
  }
}
   
// keep this function call here 
console.log(SearchingChallenge(readline()));
```
