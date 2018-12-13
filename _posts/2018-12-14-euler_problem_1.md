---
layout: post
title: "Euler Project - Problem 1"
author: "Saw"
categories: euler
tags: [euler-project]
---

Restarting my journey to solve the problems in https://projecteuler.net/ This will be the very first.

### Multiples of 3 and 5
#### Problem 1

https://projecteuler.net/problem=1
> If we list all the natural numbers below 10 that are multiples of 3 or 5, we get 3, 5, 6 and 9. The sum of these multiples is 23.
Find the sum of all the multiples of 3 or 5 below 1000.

To tackle this problem, there are a few approaches but the straight forward one is to consider:

> 1. The multiples of 3 below 1000
> 2. The multiples of 5 below 1000
> 3. The sum of the union of the two sets of multiples

Now that is basically
>  sum of 1 plus sum of 2 minus the repeating elements

The progression of these multiples are what we call the arithmethic series. And their sum is given by
![arithmeticprogression](https://www.onlinemathlearning.com/image-files/xarithmetic-series.png.pagespeed.ic.kx-x1loOGX.png)


<div class="input_area" markdown="1">

```python
## Function to calculate sum of multiples
def sum_of_multiples(a_1, n, d):
  return (n/2)*(2*a_1 + (n-1)*d)

```

</div>

To use the equation above, we need the first term, the number of terms and the common difference.

The first term and the common difference is trivial in both cases.
> For 3, 6, 9, ...   First term = 3, common difference = 3
> For 5, 10, 15, ... First term = 5, common difference = 5

To find the number of terms, it is suffice to calculate
> floor ( 999/common_difference )


<div class="input_area" markdown="1">

```python
## Find the number of terms

n_threes = int(999/3)
n_fives  = int(999/5)

print("Number of 3 multiples below 1000 = " + str(n_threes))
print("Number of 5 multiples below 1000 = " + str(n_fives))
```

</div>

{:.output_stream}
```
OUTPUT:
Number of 3 multiples below 1000 = 333
Number of 5 multiples below 1000 = 199

```

Now we have all the terms we needed, we can proceed to calculate the sums of the multiples


<div class="input_area" markdown="1">

```python
threes_sum = int(sum_of_multiples(3, n_threes, 3))
fives_sum = int(sum_of_multiples(5, n_fives, 5))

print("Sum of 3 multiples below 1000 = " + str(threes_sum))
print("Sum of 5 multiples below 1000 = " + str(fives_sum))
```

</div>

{:.output_stream}
```
OUTPUT:
Sum of 3 multiples below 1000 = 166833
Sum of 5 multiples below 1000 = 99500

```

Finally we still need to minus off the repeating elements, which is
> Sum of multiples of 15 below 1000

So we calculate the same for 15


<div class="input_area" markdown="1">

```python
n_fifteen = int(999/15)
fifteen_sum = int(sum_of_multiples(15, n_fifteen, 15))

print("Number of 15 multiples below 1000 = " + str(n_fifteen))
print("Sum of 15 multiples below 1000 = " + str(fifteen_sum))
```

</div>

{:.output_stream}
```
OUTPUT:
Number of 15 multiples below 1000 = 66
Sum of 15 multiples below 1000 = 33165

```

### Find the sum of all the multiples of 3 or 5 below 1000.


<div class="input_area" markdown="1">

```python
sum = threes_sum + fives_sum - fifteen_sum

print("Sum = " + str(threes_sum) + " + " + str(fives_sum) + " - " + str(fifteen_sum))
print("Sum = " + str(sum))
```

</div>

{:.output_stream}
```
OUTPUT:
Sum = 166833 + 99500 - 33165
Sum = 233168

```

Which is the number we wanted to find.
