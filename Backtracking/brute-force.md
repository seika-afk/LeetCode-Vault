Going back to some point to  solve the problem.
Like permutation and Combination
[[backtracking]]

#### Algorithm :

```
def  backtracking (nums):
	res=[]
	sub=[]
	def dfs (i):
		if i >= len(nums):
			res.append(sub.copy())
			return
		# decision to add in the subset 
		subset.append(nums[i])
		dfs(i+1)
		# decision to remove from the subset
		subset.pop()
		dfs(i+1)

```


[[bruteforce-dr]]
