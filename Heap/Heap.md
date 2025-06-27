Priority Queue
[[NeetCode -150]]

# Heaps and Priority Queues

-> binary Tree
[[Heaps-dr.excalidraw]]

```python
#unsorted heap
A=[-4,3,1,0,2,5,10,8,12,9]
#Heapify
#O(n),O(1)
import heapq
heapq.heapify(A)

#Heap Push (insert element)
#Time O(log(n))
heapq.heappush(A,4)
#Heap pop 
# O(logn)
min=heapq.heappop(A)

```


### Heap Sort
# Time: O(nlogn) ,space:O(n)
constant space is also possible
```python

def heapsort(arr):
	heapq.heapify(arr)
	n=len(arr)
	new_list x =[0]*n
	for i in range(n):
		min=heapq.heappop(arr)
		new_list[i]=minn
		#ascending order of list
	return new_list
	
```




# Max Heap

```
B= array
n=len(B)

for i in range(n):
B[i]=-B[i]

heapq.heapify(B)

largest=-headq.heappop(B)
```


# Heap from scratch
slower than heapify
from scratch->O(nlogn)
from heapify = O(n)
```python
A=array
heap=[]

for x in c:
	heapq.heappush(heap,x)
	print(Heap)

```


# Putting tuples of items on heap

```python
a=array
from collections import Counter
counter=Counter(a)
#getting frequency
 
```