# Q1: Good Pair

**Problem Description**

```
Given an array A and an integer B. A pair(i, j) in the array is a good pair if i != j and (A[i] + A[j] == B). Check if any good pair exist or not.
```
~~~
Google, Facebook, Amazon, Microsoft
~~~

~~~
A: [3, 2, 1, 3, 6, 8]
B: 10
~~~

## Brute Force Approach

```java
public int solve(int[] A, int B) 
{
	int n = A.length;
	
	for(int i = 0; i < n; i++)
	{
		for(int j = 0; j < n; j++)
		{
			if(i == j)
			{
				continue;
			}
				  
			if(A[i] + A[j] == B)
			{
				return 1;
			}
		}
	}
	
	return 0;
}
```

~~~
TC: O(n²)
SC: O(1)
~~~

## Using Sort

```java
import java.util.*;

public class Soultion 
{
	public int solve(int[] A, int B) 
	{
		Arrays.sort(A);
		int i = 0, j = A.length;
		
		while(i < j)
		{
			if(A[i] == A[j])
			{
				return 1;
			}
			else if(A[i] + A[j] < B)
			{
				i++;
			}
			else
			{
				j--;
			}
		}
		
		return 0;
	}
}
```

~~~
TC: O(n log(n))
SC: O(1)
~~~

---
