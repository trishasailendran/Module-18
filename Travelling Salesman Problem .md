# Ex. No: 18D - Travelling Salesman Problem (TSP)

## AIM:
To write a Python program to find the shortest possible route that visits every city exactly once and returns to the starting point using the **Travelling Salesman Problem (TSP)** approach.

## ALGORITHM:

**Step 1**: Start the program.

**Step 2**: Input the number of cities and the distance matrix.

**Step 3**: Set the starting city (e.g., city `0`).

**Step 4**: Generate all possible permutations of the remaining cities.

**Step 5**: For each permutation:
- Calculate the total cost of traveling through the permutation starting and ending at city `0`.
- Keep track of the **minimum cost** and the corresponding route.

**Step 6**: Return the **route** and the **minimum cost**.

**Step 7**: End the program.

## PYTHON PROGRAM

```python

#Reg.no 212222060280
#Name Trisha S

# Python3 program to implement traveling salesman
# problem using naive approach.
from sys import maxsize
from itertools import permutations
V = 4

# implementation of traveling Salesman Problem
def travellingSalesmanProblem(graph, s):

	# store all vertex apart from source vertex
	vertex = []
	for i in range(V):
		if i != s:
			vertex.append(i)

	# store minimum weight Hamiltonian Cycle
	   
	min_path = maxsize
	next_permutations = permutations(vertex)
	for i in next_permutations:
		current_pathweight = 0
		k = s
		for j in i:
		    current_pathweight += graph[k][j]
		    k = j
		current_pathweight += graph[k][s]
		min_path= min(min_path,current_pathweight)
	return min_path
		
# Driver Code
if __name__ == "__main__":

	# matrix representation of graph
	graph = [[0, 10, 15, 20], [10, 0, 35, 25],
			[15, 35, 0, 30], [20, 25, 30, 0]]
	s = int(input())
	print(travellingSalesmanProblem(graph, s))

```

## OUTPUT

<img width="1756" height="332" alt="image" src="https://github.com/user-attachments/assets/27181c23-293c-40cb-ad41-8ff90212705f" />


## RESULT
Thus, a Python program to find the shortest possible route that visits every city exactly once and returns to the starting point using the Travelling Salesman Problem (TSP) approach has been executed.
