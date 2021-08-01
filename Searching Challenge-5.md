Searching Challenge

Have the function SearchingChallenge(str) take the str parameter being passed and return 1 #ofBrackets if the brackets are correctly matched and each one is accounted for. Otherwise return 0. For example: if str is "(hello [world])(!)", then the output should be 1 3 because all the brackets are matched and there are 3 pairs of brackets, but if str is "((hello [world])" the the output should be 0 because the brackets do not correctly match up. Only "(", ")", "[", and "]" will be used as brackets. If str contains no brackets return 1.

Examples
```
Input: "(coder)[byte)]"
Output: 0
```
```
Input: "(c([od]er)) b(yt[e])"
Output: 1 5
```

Solution
```
function SearchingChallenge(str) { 
  var squL = 0
  var squR = 0
  var curlL = 0
  var curlR = 0

  for(i = 0; i < str.length ; i++) {
    if(str[i]=="(") curlL++
    if(str[i]==")") curlR++
    if(str[i]=="[") squL++
    if(str[i]=="]") squR++
  }

  // code goes here  
  if (curlL == 0 && curlR == 0 && squR == 0 && squL == 0)
  return 1
  else if(curlL == curlR && squR == squL)
  return 1 + " " + (curlL + squR)
  else
  return 0; 

}
   
// keep this function call here 
console.log(SearchingChallenge(readline()));
```
