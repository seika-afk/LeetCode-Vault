[[backtracking]]


``` python
# Input: list of lists
choices = [
    ['a', 'b'],
    ['1', '2'],
    ['X', 'Y']
]

res = []

def backtrack(i, path):
    if i == len(choices):
        res.append("".join(path))
        return
    for c in choices[i]:
        backtrack(i + 1, path + [c])

backtrack(0, [])

print(res)

```