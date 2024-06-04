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