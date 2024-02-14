
Merge Intervals
1) Meeting rooms
	**Problem Description**
	Given an array of meeting time `intervals` where `intervals[i] = [starti, endi]`, determine if a person could attend all meetings.

	**Example 1:**

	**Input:** intervals =  [[0,30],[5,10],[15,20]]
	**Output:** false

	**Explanation**
	Solution 1: Brute force
	We need to check if the any of the intervals are overlapping, compare each interval with every other interval to check if they are overlapping. Time complexity is O(n^2)

	Solution 2: Sorting
	Sort the intervals according to the start time, then compare each interval with the next interval by iterating the array of intervals in a loop. If the end time of the first interval is greater than the start time of the second interval then return False. If we reach the end of the array then that means there are no overlapping intervals, so return True

	**Leetcode link**
	https://leetcode.com/problems/meeting-rooms/description/


2) Merge Intervals
	**Problem Description**
	Given an array of `intervals` where `intervals[i] = [starti, endi]`, merge all overlapping intervals, and return _an array of the non-overlapping intervals that cover all the intervals in the input_.

	**Example 1:**

	**Input:** intervals = [[1,3],[2,6],[8,10],[15,18]]
	**Output:** [[1,6],[8,10],[15,18]]
	 Since intervals [1,3] and [2,6] overlap, merge them into [1,6].

	**Explanation**
	Solution 1 : Connected Components (Graph)

	Solution 2: Sorting
	* Sort the intervals according to the start time
	* Create a new array that will store the merged intervals
	* Iterate the list of intervals: Add the interval to merged array if it is empty or if the interval that is being checked has its start time greater than the end time of the last interval in the merged array
	* Otherwise, merge the last interval in the merged array with the current interval being inspected. The end time of the newly merged interval is the maximum of the end time of the last interval in the merged array and the end time of the current interval, so there is no need to append a new item to merged array list, simply modifying the last interval in the merged array works
	* Return merged array

	**Leetcode link**
	https://leetcode.com/problems/merge-intervals/description/

