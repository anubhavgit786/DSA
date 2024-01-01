Q1: Given an array A of N integers. Count the number of elements that have at least 1 elements greater than itself.

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