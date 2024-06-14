## Javascript Array and string notes 

Javascript arrays are dynamic, they are mutable and can be altered after being created. 

Javascript Strings are immutable. You cannot reference and alter a component of a String without reassigning it to a new variable. 

You can do this:
```
s = "abc";
s += 'd';
print(s)
#outputs abcd
```

You can't do stuff like:
```
s = "abd";
a[2]= 'c';
```

This happens because, += creates a new string with the additional data and reassigns it to the original variable, however in the second snippet you try to change a specific character of a string, which can't be done, because strings are immutable.

### Complexities of Array and String operations

| Operation        |  Array/List   | String(Immutable)  |
| ---------------- |:-------------:| ---------------:|
| Appending to end     | O(1) | O(n) |
| Popping from end | O(1) | O(n) |
| Insertion, not from end | O(n) | O(n) |
| Deletion, not from end | O(n) | O(n) |
| Modifying an element | O(1) | O(n) |
| Random access | O(1) | O(1) |
| Checking if element exists | O(n) | O(n) |

### Two Pointers 
Two pointers are a common technique in solving array and string problems. It involves having two integer variables that we use to both move along an iterable. This means we have two integers like "left" and "right" which represent an index of the array or string. _We start at the edges of the input and move them towards each other until they meet._

Taking this idea into instruction: 
1. Start one pointer at the first index 0 and the other pointer at the last index `input.length-1`. 
2. Use a while loop until the pointers are equal to each other. 
3. At each iteration of the loop move the pointers towards each other. This means either increment the pointer that started at the first index, decrement the pointer that started at the last index, or both. 

```
function fn(arr):
    left = 0
    right = arr.length - 1

    while left < right:
        Do some logic here depending on the problem
        Do some more logic here to decide on one of the following:
            1. left++
            2. right--
            3. Both left++ and right--
```

The strength here is that we will never have more than O(n) iterations. 

You can use this method of thinking for example to:
- Check if a string is a palindrome.
- Given a sorted array of unique integers and a target integer, return true if there exists a pair of numbers that sum to target, false otherwise.

Palindrome check in javascript:
```
const palindromeCheck = function(word) {
   let left = 0; 
   let right = word.length-1;

   while (left < right) {
        if (word[left] !== word[right]) {
            return false;
        }
        left++;
        right--;
   }

   return true;
}

const wordToCheck = "racecar";
palindromeCheck(wordToCheck);
```

Target number check (sorted array): 
```
const checkTargetSum = function(sortedNumArray, target) {
    let left = 0;
    let right = nums.length - 1;
    let current = 0; 

    for (let x = 0; x < nums.length; x++) {
        current = nums[left] + nums[right];
        console.log(current);

        if (current === target) {
            return true;
        } else if (current > target) {
            right--;
        } else {
            left++;
        }
    }

    return false;
}

const nums = [1, 2, 4, 6, 8, 9, 14, 15];
const target = 13;

checkTargetSum(nums, target);
```

Check is subsequence exists in string: 
```
const mainString = "abcde";
const subseq = "ace";

// for every character in subseq, we need to find a match in mainString
const hasSubseq = function(main, sub) {
    let a = b = 0; 

    for (let x = 0; x < main.length -1; x++) {
        
    }
}
```