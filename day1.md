# Lets learn about c++ stl

follow this link to read in depth --> https://www.geeksforgeeks.org/the-c-standard-template-library-stl/

STL has 4 components:

- Algorithms
- Containers
- Functors
- Iterators

## `Algorithms`

- Sorting
- Searching
- Important STL Algorithms
- Useful Array algorithms
- Partition Operations

### Sorting

This function internally uses IntroSort. In more details it is implemented 
using hybrid of QuickSort, HeapSort and InsertionSort.By default, it uses 
QuickSort but if QuickSort is doing unfair partitioning and taking more 
than N*logN time, it switches to HeapSort and when the array size becomes 
really small, it switches to InsertionSort. 

syntax is --> sort(startaddress, endaddress) <br>
So actually sort() sorts in the range of --> [startaddress,endaddress) . It do not include the endaddress.

General time complexity is O(nlogn) and Auxiliary space is O(1)  <br>

NOTE : how to calculate the size of array --> int size = sizeof(a) / sizeof(a[0]);

### Searching
This  algorithm requires array to be sorted.

syntax is -->binary_search(startaddress, endaddress,valuetofind) <br>

General time complexity is O(logn) and Auxiliary space is O(1)  <br>

### Other useful algorithms

#### Non-Manipulating Algorithms

- sort(first_iterator, last_iterator, greater<int>()) – <br>
  To sort the given container/vector in descending order or in custom order.
- reverse(first_iterator, last_iterator) –<br>
  To reverse a vector. ( if ascending -> descending  OR  if descending -> ascending)
- *max_element (first_iterator, last_iterator) –<br>
  To find the maximum element of a vector.
- *min_element (first_iterator, last_iterator) –<br>
  To find the minimum element of a vector.
- accumulate(first_iterator, last_iterator, initial value of sum) –<br>
  Does the summation of vector elements
- count(first_iterator, last_iterator,x) –<br>
  To count the occurrences of x in vector.
- find(first_iterator, last_iterator, x) –<br>
  Returns an iterator to the first occurrence of x in vector and points to last address of vector ((name_of_vector).end()) if element is not present in vector.
- binary_search(first_iterator, last_iterator, x) –<br>
  Tests whether x exists in sorted vector or not.
- lower_bound(first_iterator, last_iterator, x) –<br>
  returns an iterator pointing to the first element in the range [first,last) which
  has a value not less than ‘x’.
- upper_bound(first_iterator, last_iterator, x) –<br>
  returns an iterator pointing to the first element in the range [first,last)
  which has a value greater than ‘x’. 

#### Some Manipulating Algorithms

- arr.erase(position to be deleted) –-><br>
  This erases selected element in vector and shifts and resizes the vector elements accordingly.
- arr.erase(unique(arr.begin(),arr.end()),arr.end()) –-><br>
  This erases the duplicate occurrences in sorted vector in a single line.
- next_permutation(first_iterator, last_iterator) –-><br>
  This modified the vector to its next permutation.
- prev_permutation(first_iterator, last_iterator) –-><br>
  This modified the vector to its previous permutation.
- distance(first_iterator,desired_position) –-><br>
  It returns the distance of desired position from the first iterator.This function
  is very useful while finding the index.

### Useful Array algorithms
  
 - all_of() <br>
   This function operates on whole range of array elements and can save time to run a loop to check each elements one by one.
   It checks for a given property on every element and returns true when each element in range satisfies specified property, else returns false. 
 - any_of() <br>
   This function checks for a given range if there’s even one element satisfying a given property mentioned in function.
   Returns true if at least one element satisfies the property else returns false. 
 - none_of() <br>
   This function returns true if none of elements satisfies the given condition else returns false. 
 - iota() <br>
   This function is used to assign continuous values to array. This function accepts 3 arguments, the array name, size, and the starting number.

Complexity of above algorithms : <br>
  Time Complexity: O(n)<br>
  Auxiliary Space: O(1)

### Partition operations :

- partition(beg, end, condition) :- <br>
  This function is used to partition the elements on basis of condition mentioned in its arguments.
- is_partitioned(beg, end, condition) :- <br>
  This function returns boolean true if container is partitioned else returns false.<br>
  example: 
  ```diff
  partition(vect.begin(), vect.end(), [](int x)
    {
        return x%2==0;
         
    });
    ```
- stable_partition(beg, end, condition) :-<br>
  This function is used to partition the elements on basis of condition mentioned in its arguments in such a way that
  the relative order of the elements is preserved..
- partition_point(beg, end, condition) :- <br>
  This function returns an iterator pointing to the partition point of container i.e. the first element in the partitioned
  range [beg,end) for which condition is not true. The container should already be partitioned for this function to work.
