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