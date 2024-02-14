1) Sort Colors
	**Problem Description**
	Given an array `nums` with `n` objects colored red, white, or blue, sort them **[in-place](https://en.wikipedia.org/wiki/In-place_algorithm)** so that objects of the same color are adjacent, with the colors in the order red, white, and blue.

	We will use the integers `0`, `1`, and `2` to represent the color red, white, and blue, respectively.

	You must solve this problem without using the library's sort function.

	**Brief Explanation**

	This is the dutch national flag problem
	Algorithm explained

	Use 3 pointers- p0 defines the right-most boundary of all the zeros (index after the last 0), p2 defines the left-most boundary for all 2's (index just before the first 2), and curr points to the element under consideration

	1) Start with p0, curr = 0 and p2 = last index of array
	2) while curr <= p2, check
	3) if nums[curr] = 0 then swap nums[curr] with nums[p0], advance both p0 and curr
	4) if nums[curr] = 2, then swap nums[curr] with nums[p2], decrement p2
	5) if not the above, then nums[curr] = 1 then simply advance curr

	This will sort the array in-place
	Time complexity: O(n)
	Space complexity: O(1)

	**LeetCode link**
	https://leetcode.com/problems/sort-colors/description/


2) Sub-array product less than K
	**Problem Description**
	Given an array of integers `nums` and an integer `k`, return _the number of contiguous subarrays where the product of all the elements in the subarray is strictly less than_ `k`
	**Input:** nums = [10,5,2,6], k = 100
	**Output:** 8
	**Explanation:** The 8 subarrays that have product less than 100 are:
	[10], [5], [2], [6], [10, 5], [5, 2], [2, 6], [5, 2, 6]
	Note that [10, 5, 2] is not included as the product of 100 is not strictly less than k

	**Brief Explanation**
	This can be solved using the sliding window pattern

	Use two pointers left and right, start with 0 Then check every index and slowly expand the window. The left and right pointers create an interval. For the first index both left and right is 0th index, if the element is less than k we will add 1 to ans and include that subarray

	Then we advance right, the interval becomes (left, right+1)
	we multiply prod with the value stored at right index. While the product is greater or equal to k we divide nums[left] from the product and advance left. At the end of each loop we add the number of elements in the interval (left, right) to ans
	ans = (right - left) + 1 because the number of elements in the interval is also equal to the number of subarrays in that interval
	
	**LeetCode link**
	https://leetcode.com/problems/subarray-product-less-than-k/description/

3) **Problem Description**

	**Brief Explanation**

	**LeetCode link**

4) **Problem Description**

	**Brief Explanation**

	**LeetCode link**

5) **Problem Description**

	**Brief Explanation**

	**LeetCode link**

