[[backtracking]]
[[brute-force]]


## My Approach :

- Take element , every element from the board
- If it isnt in word , return ,else remove list of that word
- then check its 4 direction to see further chars
- Do By backtracking


```

class Solution:
    def exist(self, board: List[List[str]], word: str) -> bool:
        
        stack=[x for x in word]
        # print(board[0])
        for  row_index,rows in enumerate(board):
            curr_row=rows
            for word_index ,char in enumerate(rows):
                # print("word_index",board[row_index][word_index] )
                def backtrack(char,word_index,stack):
                    
                    print(stack)
                    if stack:
                        if  char == stack[0] :
                            
                            stack.pop(0)
                            if(word_index + 1 < len(curr_row) and curr_row[word_index + 1]):
                                backtrack(curr_row[word_index+1],word_index+1,stack)
                            if row_index + 1 < len(board) and board[row_index + 1][word_index]:
                                backtrack(board[row_index+1][word_index],word_index,stack)
                            if (row_index + 1 < len(board) and word_index + 1 < len(board[0]) and board[row_index + 1][word_index + 1]):
                                backtrack(board[row_index+1][word_index+1],word_index+1,stack)
                            if word_index - 1 >= 0 and curr_row[word_index - 1]:

                                backtrack(curr_row[word_index - 1], word_index, stack)
                            




                        else:
                            return

                    
                backtrack(char,word_index,stack)
                if not stack:
                    return True


        print("asdasdasdad")
        if stack:
            return False
        else:
            return True

                        
                    

```


### Issue :

```

Input
board =
[["A","B","C","E"],["S","F","C","S"],["A","D","E","E"]]

word =
"ABCB"

Stdout
['A', 'B', 'C', 'B']
['B', 'C', 'B']
['C', 'B']
['B']
['B']
['B']
['B']
[]


Output
true
Expected
false
```

-> Prev Element being used again 


```

❌ Mistakes in Your Code
1. Shared Mutable stack
You're passing the same stack list to each recursive call. Since lists are mutable, this causes unexpected side effects.

When you pop() from it in one path, it affects all other recursive paths, making your logic incorrect.

🔧 Fix: Create a copy of the stack for each recursive call using stack[:].

2. Wrong Assumption About Neighbors
You're checking:

if curr_row[word_index+1]:
or

if board[row_index+1][word_index]:
But you're not checking boundaries properly, and also missing backward and upward directions (important for this problem).


🔧 You should check all 4 directions: up, down, left, right — not diagonals unless explicitly allowed.

3. No Visited State Tracking
You can reuse letters in the same path, which is invalid.

🔧 You must mark a cell as visited and not revisit it in the same path. Use a visited set or modify the board temporarily.

4. Global Completion Check
This part:

python
Copy
Edit
if not stack:
    return True
Is misleading, because stack is shared, so even failed paths might modify it.


```




## ✅ Future Pointers

### 🧠 1. Understand Problem Constraints Clearly

- Ask: Can I reuse a letter?
    
- Are all directions allowed?
    
- What’s the input size (for choosing between BFS/DFS)?
    

---

### 🧱 2. Always Isolate Recursion Paths

Use **local copies** of state (e.g. strings, lists) unless you’re backtracking manually with undo steps.

---

### 🗺️ 3. Track Visited Cells

### 🧪 4. Test on Custom + Edge Cases

- Very small board (`1x1`)
    
- Word longer than number of cells
    
- Letters forming zigzag paths


# NeetCode Approach

-> only bruteforce solution

[[76 wordSearch-dr.excalidraw]]


```

class Solution:
    def exist(self, board: List[List[str]], word: str) -> bool:
        ROWS,COLS=len(board),len(board[0])
        path=set()

        def dfs(r,c,i):
            if i==len(word):
                return True
            
            if (r<0 or c<0 or
                r>=ROWS or c>= COLS or
                word[i] != board[r][c] or
                (r,c) in path
                ):
                return False

            path.add((r,c))
            res=(dfs(r+1,c,i+1) or
                dfs(r-1,c,i+1) or
                dfs(r,c+1,i+1) or
                dfs(r,c-1,i+1) )

            path.remove((r,c))
            return res
        for r in range(ROWS):
            for c in range(COLS):
                if dfs(r,c,0):
                    return True
        return False

        
```