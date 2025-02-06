# Daily-Leetcode-problem-solution12
PROBLEM

Given an array nums of distinct positive integers, return the number of tuples (a, b, c, d) such that a * b = c * d where a, b, c, and d are elements of nums, and a != b != c != d.

Intuition

Use a hashmap (unordered_map). The idea is to iterate through all pairs (a, b) in nums and calculate their product. Store the frequency of each product in the hashmap. If a product appears more than once, it means there exist multiple ways to form that product with different pairs (c, d).
Once we have the frequency of each product, we can count the valid tuples using combinatorial counting.

Approach

Use an unordered_map<int, int> to store the frequency of each product.
Iterate through all pairs (a, b) in nums, compute a * b, and update the frequency in the map.
For each product that appears freq times in the map:
The number of ways to choose two pairs from freq is freq * (freq - 1) / 2.
Each valid selection contributes 8 to the final count because (a, b, c, d) can be permuted in 8 ways:
(a, b, c, d), (a, b, d, c), (b, a, c, d), (b, a, d, c), (c, d, a, b), (c, d, b, a), (d, c, a, b), (d, c, b, a).

Complexity

Time complexity:
𝑂(n^2) since we iterate over all pairs in nums and use a hashmap lookup, which is O(1) on average.

Space complexity:
O(N^2)
