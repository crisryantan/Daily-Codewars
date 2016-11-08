# Exercise 1

## Description:

In this kata you will create a function that takes a list of non-negative integers and strings and returns a new list with the strings filtered out.

## Example

```
filter_list([1,2,'a','b']) == [1,2]
filter_list([1,'a','b',0,15]) == [1,0,15]
filter_list([1,2,'aasf','1','123',123]) == [1,2,123]
```

## Solution

```
function filter_list(l) {
  // Return a new array with the strings filtered out
  return l.filter( item => typeof item === 'number' )
}

console.log( filter_list([1,2,'a','b'])) // returns 1,2
```


# Exercise 2


## Description:

Write a function that takes in a string of one or more words, and returns the same string, but with all five or more letter words reversed (Just like the name of this Kata). Strings passed in will consist of only letters and spaces. Spaces will be included only when more than one word is present.

## Example

```
spinWords( "Hey fellow warriors" ) => returns "Hey wollef sroirraw" 
spinWords( "This is a test") => returns "This is a test" 
spinWords( "This is another test" )=> returns "This is rehtona test"
```

## Solution
```
function spinWords( s ){
  return s.split( ' ' ).map( function ( word ) {
  	return ( word.length > 4 ) ? word.split( '' ).reverse().join( '' ) : word;
  } ).join( ' ' );
}
```

# Exercise 3

## Description:

You are given an array strarr of strings and an integer k. Your task is to return the first longest string consisting of k consecutive strings taken in the array.

## Example:
```
longest_consec(["zone", "abigail", "theta", "form", "libe", "zas", "theta", "abigail"], 2) --> "abigailtheta"

n being the length of the string array, if n = 0 or k > n or k <= 0 return "".
```

## Solution
```
function longestConsec(strarr, k) {
  if ( strarr.length === 0 || k > strarr.length || k <1 ) return '';
  let lens = strarr.map( ( _, i, arr ) => arr.slice( i, i+k ).join( '' ).length ),
      i = lens.indexOf( Math.max( ...lens ) );
  return strarr.slice( i, i+k ).join( '' )
}
```