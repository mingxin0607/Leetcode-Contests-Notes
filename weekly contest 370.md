

### [2925. Maximum Score After Applying Operations on a Tree](https://leetcode.com/problems/maximum-score-after-applying-operations-on-a-tree/)
#### category / tags
dynamic programming on a tree
backtracking
depth first search

#### Approach
- Consider the opposite to simplify the situation
- Assume to choose to collect all the nodes at first, then choose minimal sum of nodes that satisfy the rule of "healthy tree"
- To break down the task, dfs from any node (say node 0)
- For each node, either choose itself to not be counted in the answer, or let its children do that, find the minimal sum.
- The reason why dp works is that if all of the subtrees of one tree are healthy, the tree is certain to be healthy. And if any of its subtree is not healthy, the current node (or root node of this tree) must not be 0
- No need to use @cache in python, only visit each node for one time. Simliar as traversing.

#### performance analysis
both O(n)


### [2926. Maximum Balanced Subsequence Sum](https://leetcode.com/problems/maximum-balanced-subsequence-sum/)

???
#### category
dp
TreeMap

#### approach
nums[i] - nums[j] >= i - j
nums[i] - i  >= nums[j] - j

b[i] = nums[i] - i
select one ascending subsequence from b
find max of sum(nums[i])

dp[i] = subsequence end in i, the max of sum of subsequence
ans = max(dp)

dp[i] = dp[j] + nums[i]  for j < i and b[j] <= b[i]

a = 2 6 5 7
b = 2 5 3 4

Use TreeMap
 