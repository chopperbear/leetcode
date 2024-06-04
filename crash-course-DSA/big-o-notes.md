# big O refresher 

Let's look at some example algorithms in pseudo-code and talk about their time complexities.

`
// Given an integer array "arr" with length n,
for (int num: arr) {
    print(num)
}
`

This algorithm has a time complexity of O(n). In each for loop iteration, we are performing a print, which costs O(1). The for loop iterates n times, which gives a time complexity of O(1*n) = O(n).

`
// Given an integer array "arr" with length n,
for (int num: arr) {
    for (int i = 0; i < 500,000; i++) {
        print(num)
    }
}
`

This algorithm has a time complexity of O(n). In each inner for loop iteration, we are performing a print, which costs O(1). This for loop iterates 500,000 times, which means each outer for loop iteration costs O(500000)=O(1). The outer for loop iterates n times, which gives a time complexity of O(n).

Even though the first two algorithms technically have the same time complexity, in reality the second algorithm is much slower than the first one. It's correct to say that the time complexity is O(n), but it's important to be able to discuss the differences between practicality and theory.

`
// Given an integer array "arr" with length n,
for (int num: arr) {
    for (int num2: arr) {
        print(num * num2)
    }
}
`

This algorithm has a time complexity of O(n^2). In each inner for loop iteration, we are performing a multiplication and print, which both cost O(1). The inner for loop runs n times, which means each outer for loop iteration costs O(n). The outer for loop runs O(n) times, which gives a time complexity of O(n*n)=O(n^2).

`
// Given integer arrays "arr" with length n and "arr2" with length m,

for (int num: arr) { print(num) }

for (int num: arr) { print(num) }

for (int num: arr2) { print(num) }
`

This algorithm has a time complexity of O(n+m). The first two for loops both cost O(n), whereas the final for loop costs O(m). This gives a time complexity of O(2n+m) = O(n+m).

### logarithmic time 

The time complexity O(logn) is called logarithmic time and is extremely fast. A common time complexity is O(n*logn), which is reasonably fast for most problems and also the time complexity of efficient sorting algorithms.

O(logn) means that somewhere in your algorithm, the input is being reduced by a percentage at every step. A good example of this is binary search, which is a searching algorithm that runs in O(logn) time . With binary search, we initially consider the entire input (n elements). After the first step, we only consider n / 2 elements. After the second step, we only consider n / 4 elements, and so on. At each step, we are reducing our search space by 50%, which gives us a logarithmic time complexity.

### Space complexity

When you initialize variables like arrays or strings, your algorithm is allocating memory.

`
// Given an integer array "arr" with length n
for (int num: arr) {
    print(num)
}
`

The above algorithm is not allocating any new memory thus its space complexity is O(1). 

`
// Given an integer array "arr" with length n
Array doubledNums = int[]

for (int num: arr) {
    doubledNums.add(num * 2)
}
`

The above algorithm has a space complexity of O(n). the array doubledNums is equal to ,n which is the size of the array its fed as input. 

`
// Given integer arrays "arr" with length n and "arr2" with length m,

Array grid = int[n][m]
for (int i = 0; i < arr.length; i++) {
    for (int j = 0; j < arr2.length; j++) {
        grid[i][j] = arr[i] * arr2[j]
    }
}
`
This has a space complexity of O(n*m). 