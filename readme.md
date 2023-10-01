# Road map
- [Road map](#road-map)
  - [1. Array and Hashing](#1-array-and-hashing)
  - [2. Two Pointers](#2-two-pointers)
  - [3. Sliding Window](#3-sliding-window)

## 1. Array and Hashing

Questions
| Problems 	| Difficulty 	|
|----------	|------------	|
| [Contains Duplicate](https://leetcode.com/problems/contains-duplicate/) |      Easy      	|
| [Valid Anagram](https://leetcode.com/problems/valid-anagram/) |      Easy      	|
| [Two Sum](https://leetcode.com/problems/two-sum/) |      Easy      	|
| [Group Anagrams](https://leetcode.com/problems/group-anagrams/) |      Medium    	|
| [Top K Frequent Elements](https://leetcode.com/problems/top-k-frequent-elements/) |      Medium     	|
| [Product of Array Except Self](https://leetcode.com/problems/product-of-array-except-self/) |      Medium     	|
| [Longest Substring Without Repeating Characters](https://leetcode.com/problems/longest-substring-without-repeating-characters/)| Medium |
| [Valid Sudoku](https://leetcode.com/problems/valid-sudoku/) | Medium|
| [Longest Consecutive Sequence](https://leetcode.com/problems/longest-consecutive-sequence/)| Medium |

## 2. Two Pointers

Has two types : 
- opposite direction, i.e one from the start and the other from the end, __TYPE 1__
- slow and fast runner, in the same direction, __TYPE 2__


Questions:
  
| Problems 	| Difficulty 	| Type |
|----------	|------------	| -----|
| [Valid Palindrome](https://leetcode.com/problems/valid-palindrome/) |      Easy      	| TYPE 1|
| [Reverse String](https://leetcode.com/problems/reverse-string/) |      Easy      	| TYPE 1|
| [Move Zeros](https://leetcode.com/problems/move-zeroes/) |      Easy      	|TYPE 2|
| [Remove Duplicates from Sorted Array](https://leetcode.com/problems/remove-duplicates-from-sorted-array/) |      Easy      	|TYPE 2|
| [Linked List Cycle](https://leetcode.com/problems/linked-list-cycle/)| Easy | Type 2|
| [Two Sum II Input Array Is Sorted](https://leetcode.com/problems/two-sum-ii-input-array-is-sorted/) |      Medium    	|TYPE 1|
| [3Sum](https://leetcode.com/problems/3sum/) |      Medium     	|TYPE 1|
| [Container With Most Water](https://leetcode.com/problems/container-with-most-water/) |      Medium     	|TYPE 1|
| [Longest Substring Without Repeating Characters](https://leetcode.com/problems/longest-substring-without-repeating-characters/)| Medium |TYPE 2|
| [Trapping Rain Water](https://leetcode.com/problems/trapping-rain-water/)| Hard|TYPE 1|

## 3. Sliding Window

1. In sliding window problems if asked to find k numbers in any sequence __try out sorting the array first__.
2. In Sliding window problems if k is small value i.e < 4 use manual comparison rather than using complex data structures.
3. IN SLIDING WIN problems, if the set data is involved
```cpp
  while(st.find(s[i]) != st.end()){
    st.erase(s[l]);
    l++;
  }
  st.insert(s[i]);
   ```
Questions:
  
| Problems 	| Difficulty 	| Type |
|----------	|------------	| -----|
| [Maximum of all subarrays of size k](https://practice.geeksforgeeks.org/problems/maximum-of-all-subarrays-of-size-k3101/1) |      Medium   	| |
| [First negative integer in every window of size k ](https://practice.geeksforgeeks.org/problems/first-negative-integer-in-every-window-of-size-k3345/1) |      Easy     	| |
| [Longest Sub-Array with Sum K](https://practice.geeksforgeeks.org/problems/longest-sub-array-with-sum-k0809/1) |      Medium   	| |
| [Longest K unique characters substring](https://practice.geeksforgeeks.org/problems/longest-k-unique-characters-substring0853/1) |      Medium   	| |
