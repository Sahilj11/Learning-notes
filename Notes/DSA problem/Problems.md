# Array
## Medium
#### Kadane’s Algorithm : Maximum Subarray Sum in an Array
**Problem Statement**: Given an integer array arr, find the contiguous subarray (containing at least one number) which  
has the largest sum and returns its sum and prints the subarray.

**Examples**

**Example 1:**

**Input:** arr = [-2,1,-3,4,-1,2,1,-5,4] 

**Output:** 6 

**Explanation:** [4,-1,2,1] has the largest sum = 6. 

**Examples 2:** 

**Input:** arr = [1] 

**Output:** 1 

**Explanation:** Array has only one element and which is giving positive sum of 1.

#### Stock buy and sell
**Problem Statement:** You are given an array of prices where prices[i] is the price of a given stock on an ith day.

You want to maximize your profit by choosing a single day to buy one stock and choosing a different day in the future to sell that stock. Return _the maximum profit you can achieve from this transaction_. If you cannot achieve any profit, return 0.

**Examples**

**Example 1:**

**Input:** prices = [7,1,5,3,6,4]
**Output:** 5
**Explanation:** Buy on day 2 (price = 1) and 
sell on day 5 (price = 6), profit = 6-1 = 5.

**Note**: That buying on day 2 and selling on day 1 
is not allowed because you must buy before 
you sell.

**Example 2:**

**Input:** prices = [7,6,4,3,1]
**Output:** 0
**Explanation:** In this case, no transactions are 
done and the max profit = 0.

#### Rearrange array element by sign
**Problem Statement**:

There’s an array ‘A’ of size ‘N’ with an equal number of positive and negative elements. Without altering the relative order of positive and negative elements, you must return an array of alternately positive and negative values.

**Note:** Start the array with positive elements.

**Examples:** 

**Example 1**:

**Input**:
arr[] = {1,2,-4,-5}, N = 4
**Output**:
1 -4 2 -5

**Explanation**: 

Positive elements = 1,2
Negative elements = -4,-5
To maintain relative ordering, 1 must occur before 2, and -4 must occur before -5.

**Example 2**:
**Input**:
arr[] = {1,2,-3,-1,-2,-3}, N = 6
**Output:**
1 -3 2 -1 3 -2
**Explanation**: 

Positive elements = 1,2,3
Negative elements = -3,-1,-2
To maintain relative ordering, 1 must occur before 2, and 2 must occur before 3.
Also, -3 should come before -1, and -1 should come before -2.

#### next_permutation : find next lexicographically greater permutation
**Problem Statement:** Given an array Arr[] of integers, rearrange the numbers of the given array into the lexicographically next greater permutation of numbers.

If such an arrangement is not possible, it must rearrange to the lowest possible order (i.e., sorted in ascending order).

**Examples**

**Example 1 :**

**Input format:** Arr[] = {1,3,2}
**Output**: Arr[] = {2,1,3}
**Explanation:** All permutations of {1,2,3} are {{1,2,3} , {1,3,2}, {2,13} , {2,3,1} , {3,1,2} , {3,2,1}}. So, the next permutation just after {1,3,2} is {2,1,3}.

**Example 2:**

**Input format:** Arr[] = {3,2,1}
**Output:** Arr[] = {1,2,3}
**Explanation:** As we see all permutations of {1,2,3}, we find {3,2,1} at the last position. So, we have to return the topmost permutation.

#### Leaders in array
**Problem Statement:** Given an array, print all the elements which are leaders. A Leader is an element that is greater than all of the elements on its right side in the array.

**Examples**

**Example 1:**
**Input:**
 arr = [4, 7, 1, 0]
**Output**:
 7 1 0
**Explanation:**
 Rightmost element is always a leader. 7 and 1 are greater than the elements in their right side.

**Example 2:**
**Input:**
 arr = [10, 22, 12, 3, 0, 6]
**Output:**
 22 12 6
**Explanation:**
 6 is a leader. In addition to that, 12 is greater than all the elements in its right side (3, 0, 6), also 22 is greater than 12, 3, 0, 6.