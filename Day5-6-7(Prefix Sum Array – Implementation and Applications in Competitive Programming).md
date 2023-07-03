# Prefix Sum of array
  
    void fillPrefixSum(vector<int> arr,vector<int>&prefixSum)
    {
      int n = arr.size();
      prefixSum[0]=arr[0];
      
      for(int i=1;i<n;i++)
        prefixSum[i] = prefixSum[i-1]+arr[i];
      
    }

 ## Sum of an array between indexes L and R using Prefix Sum:

 for 1 based index <br>
 If L is greater than 1, then print prefixSum[R] – prefixSum[L-1] <br>
 else print prefixSum[R] <br>

## Example Problem: 

Consider an array of size N with all initial values as 0. Perform the given ‘m’ add operations 
from index ‘a’ to ‘b’ and evaluate the highest element in the array. An add operation adds 100 
to all the elements from a to b (both inclusive). 

Naive Approach:  <br>
To solve the problem follow the below idea: <br>
A simple approach is running a loop ‘m’ times. Inputting a and b and running a loop from a to b, adding all elements by 100. <br>
Time Complexity: O(N * M) <br>
Auxiliary Space: O(1) <br>

The efficient approach is to use Prefix Sum Array <br>

Follow the given steps to solve the problem: <br>

Run a loop for ‘m‘ times, inputting ‘a‘ and ‘b‘. <br>
Add 100 at index ‘a-1‘ and subtract 100 from index ‘b‘. <br>
After completion of ‘m‘ operations, compute the prefix sum array. <br>
Scan the largest element and we’re done. <br>

Time Complexity: O(N + M), where N is the size of the array and M is the number of operations <br>
Auxiliary Space: O(N) <br>

## Find if there is a subarray with 0 sum

  Follow the given steps to solve the problem:

- Declare a variable sum, to store the sum of prefix elements <br>
- Traverse the array and at each index, add the element into the sum and check if this sum exists earlier. If the sum exists, then return true <br>
- Also, insert every prefix sum into a map, so that later on it can be found whether the current sum is seen before or not <br>
- At the end return false, as no such subarray is found <br>

```
  arr[] = {1, 4, -2, -2, 5, -4, 3}

Consider all prefix sums, one can notice that there is a subarray with 0 sum when :

Either a prefix sum repeats or <br>
Or prefix sum becomes 0. <br>
Prefix sums for above array are: 1, 5, 3, 1, 6, 2, 5 <br>
Since prefix sum 1 repeats, we have a subarray with 0 sum. <br>
```
