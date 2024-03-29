---
layout: post
title: Time Complexity & Big O Notation
subtitle: Featuring Asymptotics and other big words
description: Some notes I wrote for myself, doubling as a cheat sheet :)
tags: [Notes]
readtime: true
---

a little cheat sheet i made for myself

<img src="/img/big-o-running-time-complexity.png"/>

*Note: This isn't neccesarily for teaching, but for my own use.*

CREDIT:

[1] “How You Can Change the World by Learning Data Structures and Algorithms” Adrian Mejia Blog, [Blog Link](https://adrianmejia.com/how-you-can-change-the-world-learning-data-structures-algorithms-free-online-course-tutorial)

[2] “8 time complexities that every programmer should know” Adrian Mejia Blog, [Blog Link](https://adrianmejia.com/most-popular-algorithms-time-complexity-every-programmer-should-know-free-online-tutorial-course)

[3] "Time Complexity Big O Notation Data Structures & Algorithms" JomaClass, [Youtube Link](https://www.youtube.com/watch?v=v1SYihb4rcw)

## What is Time Complexity?

Time Complexity (running time) is a way of measuring how long an algorithm takes to run, and does so accurately despite the system used to test the code (ie, slow vs fast computer). It does not measure in a unit of time, such as seconds, but rather as a function of the input and describes the worse-case scenario.

Update (7/13): (better answer?) its a measure of how the whole algorithm scales up as the input size increases

Take the following code, which returns the smallest value in an array (no specific langauge):

{% highlight javascript linenos %}
function getMinValue(nums) {
  let min
  if (nums.length > 0):
    min = numbers[0]

  for x in nums:
    if (x < min):
      min = x
      
  return min
}
{% endhighlight %}

We can count the number of operations to determine it's time complexity:

- Lines 2-4 use 1 operation each **total: 3**

- Line 6 uses nums.length operations. This depends on the length of the array passed **total: n**

- 7-8 use 1 operation each, but because they are in the loop they happen n times. **total: 2**
  
So because we have a loop with 2 operations, and 3 operations outside the loop, we can say the time complexity of this method is 2(n) + 3

However, that is too specific.

We need to use *Asymptotic analysis* to simplify this, which is a way of describing limiting behavior.

Consider the following table, which shows how the output grows as n grows. Note the effect that the +3 has on the ouput.

| Equation | n | Output |
| :------ |:--- | :--- |
| 2(n) + 3 | 10 | 23 |
| 2(n) + 3 | 100 | 203 |
| 2(n) + 3 | 1000 | 2003 |
| 2(n) + 3 | 10000 | 20003 |

You can see the +3 really doesn't make a difference as n approaches infinity. As n grows, the constant is less significant. The 2 also has little significance as we approach infinity, so according to asymptotics we simplify **2(n) + 3** to **n**

Therefore we conclude that the time complexity of the getMinValue() method is **O(n)** (We use Big O Notation to describe time complexity.)

Likewise, take the expression **7n^3 + 4n + 9** as a time complexity. We could simplify it down to **O(n^3)**, since that has the highest order, and therefore highest impact. **7n^3 + 4n + 9** is said to be "asymptotically equivalent" to **n^3**, as n → ∞

Lets take a more complex method:

{% highlight javascript linenos %}
function checkDuplicates(nums) {
  
  let output = false
  
  for (i = 0; i < nums.length; i++) {
    for (j = 0; j < nums.length; j++) {
    
      if(i == j):
        continue

      if(n[i] == n[j]):
        output = true
      
    }
  }
  
  return output
}
{% endhighlight %}

There are 2 nested for loops here, which each run n times. (**n^2**) Within these loops are about 2 operations (**2n^2**) (I supposed the continue and return true don't really count)

Theres also line 3, which counts as 1 operation

So we can give this method a time complexity of O(2n^2 + 1)

However we wanna describe this as it approaches infinity, so we can remove the +1 and the coefficent of 2 to get a time complexity of **O(n^2)**, which is much slower than a time complexity of **O(n)**

A method with 3 nested loops would have a time complexity of **O(n^3)**

## Other Big O Notations

**O(1)** describes algorithms that take the same amount of time to compute regardless of the input size.

**O(n)** Linear time complexity means that the algorithms take proportionally longer to complete as the input grows. These algorithms imply that the program visits every element from the input.

**O(n^c)** Polynomial running, when c > 1. 2 nested loops will have c = 2 (quadratic), and 3 will have c = 3 (cubed), and so on.

**O(log n)** Logarithmic time complexities usually apply to algorithms that divide problems in half every time.

**O(n log n)** Linearithmic time complexity is slightly slower than a linear algorithm. However, it’s still much better than a polynomial algorithm.

**O(2^n)** Exponential running time means that the calculations performed by an algorithm double every time as the input grows.

**O(n!)** Factorial runtime are terrible, just terrible. (ex. Permutations of a string)

## Master Thereom

When dealing with recursion, theres a Master Thereom that can be used to calculate the time complexity of an algorithm.

