[[brute-force]]
[[backtracking]]
```
class Solution:

def combinationSum(self, candidates: List[int], target: int) -> List[List[int]]:
	res=[]

def dfs(i,curr,total):

		if total==target:
		
			res.append(curr.copy())
			
			return
			
		if i>=len(candidates) and total>target:
		
			return
			
		#decision to add
		
		curr.append(candidates[i])
		
		dfs(i,curr,total+candidates[i])
		
		curr.pop()
		
		dfs(i+1,curr,total)
		
	  
	
	dfs(0,[],0)
	
	return res
	
	

```

