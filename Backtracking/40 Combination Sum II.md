
[[39 Combination Sum]]
[[brute-force]]
[[backtracking]]

Algorithm:

[[40 CombinationSumII -dr]]

```
class Solution:
    def combinationSum2(self, candidates: List[int], target: int) -> List[List[int]]:
        res=[]
        subset=[]
        def dfs(i,subset):

            if (sum(subset)==target):
                subset=sorted(subset)
                if not subset in res:
                    res.append(subset.copy())
                return
            if i>= len(candidates):
                return
            
            #decision to add
            subset.append(candidates[i])
            dfs(i+1,subset)

            #decision to not add
            subset.pop()
            dfs(i+1,subset)
        dfs(0,subset)
    
        print(res)
        return res
        
```

ERROR : Time Limit Exceeded


### OPTIMAL SOLUTION:

#### STILL BRUTE FORCE


```
class Solution:
    def combinationSum2(self, candidates: List[int], target: int) -> List[List[int]]:
        candidates.sort()
        res=[]

        def backtrack(pos,cur,target):
            if target ==0 :
                res.append(cur.copy())
            if target <=0:
                return
            prev=-1
            for i in range(pos,len(candidates)):
                if candidates[i]== prev:
                    continue
                cur.append(candidates[i])
                backtrack(i+1,cur,target-candidates[i])
                cur.pop()
                prev=candidates[i]
        backtrack(0,[],target)
        return res
```


