# Trapping-Rain-Water
Given an integer array height where height[i] represents the height of a bar at index i, return the amount of rainwater that can be trapped after raining.
Explanation of Trapping Rain Water Problem
The goal is to calculate the total amount of rainwater trapped between the bars when it rains. We use the Two-Pointer Approach for an efficient O(n) solution.

Step-by-Step Approach
1. Understanding Water Trapping
Water is trapped at an index only if there are taller bars on both the left and right.

The amount of trapped water at any index i is given by:

water at i
=min⁡(maxLeft,maxRight)−height[𝑖]
water at i=min(maxLeft,maxRight)−height[i]
maxLeft → The maximum height on the left side of i.
maxRight → The maximum height on the right side of i.
The minimum of maxLeft and maxRight determines the max possible water level.
2. Using Two Pointers Efficiently
Instead of calculating maxLeft and maxRight separately for each element (which takes O(n^2) time), we use two pointers (left and right), moving towards the center.

Initialize Two Pointers

left = 0 (starting from the left end)
right = n-1 (starting from the right end)
leftMax = 0 (tracks the highest bar from the left)
rightMax = 0 (tracks the highest bar from the right)
water = 0 (stores the total trapped water)
Move the Pointer with the Smaller Height

If height[left] < height[right]:
If height[left] ≥ leftMax, update leftMax
Otherwise, calculate trapped water at left
Move left pointer to the right (left++)
Otherwise:
If height[right] ≥ rightMax, update rightMax
Otherwise, calculate trapped water at right
Move right pointer to the left (right--)
