# 256 Paint House
[https://leetcode.com/problems/paint-house](https://leetcode.com/problems/paint-house)


## solution

```python
class Solution:
    def minCost(self, costs: List[List[int]]) -> int:
        cost_red = cost_blue = cost_green = 0
        for cost_of_red, cost_of_blue, cost_of_green in costs:
            new_cost_red = min(cost_blue, cost_green) + cost_of_red
            new_cost_blue = min(cost_red, cost_green) + cost_of_blue
            new_cost_green = min(cost_red, cost_blue) + cost_of_green
            cost_red, cost_blue, cost_green = new_cost_red, new_cost_blue, new_cost_green
        return min(cost_red, cost_blue, cost_green)
```
时间复杂度：O(n) <br>
空间复杂度：O(1)