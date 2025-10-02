# Searchin-in-cpp

--------------------------------------------------
AIM
--------------------------------------------------
The aim of this project is to study and implement different searching algorithms in C++:
1. Linear Search
2. Binary Search
3. Jump Search
4. Interpolation Search
5. Fibonacci Search

The project helps in understanding various searching strategies, their time complexities, and their applications on sorted and unsorted data sets.


--------------------------------------------------
THEORY
--------------------------------------------------
Searching is the process of finding the position of a target element (key) within a collection such as an array.

There are many searching algorithms, each with different efficiency and use cases. The most common are:

1. LINEAR SEARCH
   - Simple method, works on both sorted and unsorted arrays.
   - Traverse elements one by one until target is found or array ends.
   - Time Complexity: O(n)
   - Advantage: Simple, no preconditions.
   - Limitation: Slow for large arrays.

2. BINARY SEARCH
   - Works only on sorted arrays.
   - Repeatedly divides the array into halves and compares target with middle element.
   - Time Complexity: O(log n)
   - Advantage: Very efficient on large sorted data.
   - Limitation: Requires sorted data.

3. JUMP SEARCH
   - Works on sorted arrays.
   - Jump ahead by fixed block size (usually √n) and then do linear search within the block.
   - Time Complexity: O(√n)
   - Advantage: Fewer comparisons than linear search.
   - Limitation: Requires sorted data.

4. INTERPOLATION SEARCH
   - Works on sorted and uniformly distributed data.
   - Improves binary search by estimating the position of the target using interpolation formula.
   - Time Complexity: O(log log n) in best/average case; O(n) in worst case.
   - Advantage: Very fast for uniform data (like searching in phonebook).
   - Limitation: Performance degrades on non-uniform distributions.

5. FIBONACCI SEARCH
   - Works on sorted arrays.
   - Uses Fibonacci numbers to divide the array into smaller sections (similar to binary search but positions are chosen using Fibonacci sequence).
   - Time Complexity: O(log n)
   - Advantage: Useful when division (/) is expensive operation, as it uses only addition/subtraction.
   - Limitation: More complex to implement than binary search.


--------------------------------------------------
ALGORITHMS
--------------------------------------------------
LINEAR SEARCH (arr[0..n-1], key = x)
1. For i = 0 to n-1
2.    If arr[i] == x, return i
3. End loop
4. If not found, return -1

BINARY SEARCH (sorted arr[0..n-1], key = x)
1. Set low = 0, high = n - 1
2. While low <= high:
3.    mid = (low + high) / 2
4.    If arr[mid] == x → return mid
5.    If arr[mid] < x → low = mid + 1
6.    Else high = mid - 1
7. Return -1 if not found

JUMP SEARCH (sorted arr[0..n-1], key = x)
1. Let step = √n
2. Jump ahead by steps until arr[min(step, n)-1] >= x
3. Do linear search backward from step to previous block
4. If element found, return index else return -1

INTERPOLATION SEARCH (sorted arr[0..n-1], key = x)
1. Set low = 0, high = n - 1
2. While low <= high and x >= arr[low] and x <= arr[high]:
3.    pos = low + ((x - arr[low]) * (high - low)) / (arr[high] - arr[low])
4.    If arr[pos] == x → return pos
5.    If arr[pos] < x → low = pos + 1
6.    Else high = pos - 1
7. Return -1 if not found

FIBONACCI SEARCH (sorted arr[0..n-1], key = x)
1. Find the smallest Fibonacci number greater than or equal to n
2. Initialize offset = -1
3. While fibM > 1:
4.    i = min(offset + fibMm2, n-1)
5.    If arr[i] < x → move Fibonacci window right
6.    If arr[i] > x → move Fibonacci window left
7.    If arr[i] == x → return i
8. Return -1 if not found


--------------------------------------------------
FILES
--------------------------------------------------
- Linear Search.cpp
- Binary Search.cpp
- Jump Search.cpp
- Interpolation Search.cpp
- Fibonacci Search.cpp

Each file contains the implementation of one searching algorithm in C++.


--------------------------------------------------
CONCLUSIONS
--------------------------------------------------
- Linear Search is simple but inefficient for large data sets.
- Binary Search is very efficient (O(log n)) but requires sorted input.
- Jump Search provides a compromise between linear and binary search.
- Interpolation Search is extremely efficient for uniformly distributed data.
- Fibonacci Search is similar to binary search but uses Fibonacci numbers and only addition/subtraction.

By implementing all these algorithms, we learn that the choice of searching technique depends on:
- Whether the data is sorted or not,
- The size of the dataset,
- The distribution of data.

Thus, understanding multiple searching methods helps in selecting the most appropriate algorithm for a given problem.
