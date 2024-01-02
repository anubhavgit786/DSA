# Q1: Count of elements

**Problem Description**

```
Given an array A of N integers. 
Count the number of elements that have at least 1 elements greater than itself.
```
~~~
PayTM
~~~

**arr: -3, 2, 6, 8, 4, 5, 8** 

*Clearly, all elements will follow the condition except the maximum one. We have total 7 integers. The count of maximmum integers is 2. So, the answer will be 7 - 2 = 5.*

```java
public class Solution
{
	public int count(int []arr)
	{
		int max = Integer.MIN_VALUE;
        int n = arr.length;

		for(int i = 0; i < n; i++)
		{
            if(max < arr[i])
            {
				max = arr[i];
            }
        }

		int count = 0;

		for(int i = 0; i < n; i++)
		{
			if(max == arr[i])
			{
				count++;
			}
		}

		return n-count;
    }
}
```
~~~
TC: O(n)
SC: O(1)
~~~
---


# Q2: Reverse in a range

**Problem Description**

```
Given an array A of N integers and also given two integers B and C. Reverse the elements of the array A within the given inclusive range [B, C].
```
~~~
OYO
~~~

```java

public class Solution
{
	public int[] solve(int[] A, int B, int C)
	{
		int i = B, j = C;
	
		while(i < j)
		{
			int temp = A[i];
			A[i] = A[j];
			A[j] = temp;
			i++;
			j--;
		}
		return A;
	}
}

```

~~~
TC: O(n)
SC: O(1)
~~~
---

# Q3: Array Rotation

**Problem Description**

```
Given an integer array A of size N and an integer B, you have to return the same array after rotating it B times towards the right.
```

~~~
Amazon, Adobe, Apple, Google, Accenture, Uber, Zoho, Walmart Labs, Goldman Sachs, Microsoft, Yahoo, Facebook, SAP, TCS, LinkedIn, Bloomberg, Cohesity, Salesforce, Infosys. 
~~~

```java
public class Solution
{
	public void rotate(int arr[], int start, int end)
	{
    	while(start < end)
    	{
        	int temp = arr[start];
        	arr[start] = arr[end];
        	arr[end] = temp;
        	start++;
        	end--;
    	}
	}

	public int[] solve(int[] A, int B) 
	{
		B = B % A.length;
		rotate(A, 0, A.length-1);
		rotate(A, 0, B-1);
		rotate(A, B, B.length-1);
    	return A;
	}
}
```
~~~
TC: O(n)
SC: O(1)
~~~
---

# Q4: Max Min of an Array

**Problem Description**

```
Given an array A of size N. You need to find the sum of Maximum and Minimum element in the given array.
```

~~~java

public class Solution
{
	public int solve(int[] A) 
    {
		int max = Integer.MIN_VALUE;
        int min = Integer.MAX_VALUE;
        
		for(int i = 0 ; i < A.length; i++ )
        {
            if(max < A[i])
            {
                max = A[i];
            }

            if(A[i] < min)
            {
                min = A[i];
            }
        }

        return max + min;
    }
}
~~~

~~~
TC: O(n)
SC: O(1)
~~~
---

# Q5: Linear Search - Multiple Occurences

**Problem Description**

~~~
Given an array A and an integer B, find the number of occurrences of B in A.
~~~

~~~java

public class Solution 
{
	public int solve(int[] A, int B) 
    {
        int count = 0;
        for(int i = 0; i < A.length; i++)
        {
            if(A[i]==B)
            {
                count++;
            }
        }

        return count;
    }
}
~~~

~~~
TC: O(n)
SC: O(1)
~~~
---

# Q6:  Second Largest


**Problem Description**

~~~
You are given an integer array A. You have to find the second largest element/value in the array or report that no such element exists.
Return the second largest element. If no such element exist then return -1.
~~~

~~~java

public class Solution 
{
	public int solve(int[] A) 
    {
		int index = 0, n = A.length;
		
		// This will give us the maximum element of A
        for(int i = 1; i < n; i++)
		{
            if(A[index] < A[i])
			{
                index = i;
            }
        }
        
        int ans = -1;
        // This will give us maximum element of A which is less than A[index]
        for(int i = 0; i < n; i++)
		{
            if(A[i] != A[index])
			{
                ans = Math.max(ans, A[i]);
            }
        }
        
        return ans;
    }
}
~~~

~~~
TC: O(n)
SC: O(1)
~~~
---

# Q7: Time to equality

**Problem Description**

~~~
Given an integer array A of size N. In one second, you can increase the value of one element by 1.
Find the minimum time in seconds to make all elements of the array equal.
~~~

~~~java

public class Solution 
{
	public int solve(int[] A) 
    {
        int count = 0; 
        int max = Integer.MIN_VALUE;
        for(int i = 0; i < A.length; i++)
        {
            if(max < A[i])
            {
                max = A[i];
            }
        }

        for(int i = 0; i < A.length; i++)
        {
            count = count + max - A[i];
        }

        return count;
    }
}
~~~

~~~
TC: O(n)
SC: O(1)
~~~
---


# Q8: Range Sum Query - II

**Problem Description**

~~~
You are given an integer array A of length N.
You are also given a 2D integer array B with dimensions M x 2, where each row denotes a [L, R] query.
For each query, you have to find the sum of all elements from L to R indices in A (0 - indexed).
More formally, find A[L] + A[L + 1] + A[L + 2] +... + A[R - 1] + A[R] for each query.
~~~

~~~
A = [1, 2, 3, 4, 5]
B = [[0, 3], [1, 2]]
Output: [10, 5]
~~~

~~~java

public class Solution 
{
    public int[] solve(int[] A, int[][] B) 
    {
        int result[] = new int[B.length];
        for(int i = 0; i < B.length; i++)
        {
            int start = B[i][0];
            int end = B[i][1];
            int sum = 0;
            for(int j = start; j<=end; j++)
            {
                sum = sum + A[j];
            }
            result[i] = sum;
        }

        return result;
    }
}

~~~

~~~
TC: O(n)
SC: O(1)
~~~
---


