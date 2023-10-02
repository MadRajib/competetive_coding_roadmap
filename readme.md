# Road map
- [Road map](#road-map)
  - [1. Array and Hashing](#1-array-and-hashing)
  - [2. Two Pointers](#2-two-pointers)
  - [3. Binary Search](#3-binary-search)
      - [1. Find First and Last Position of Element in Sorted Array ( Medium )](#1-find-first-and-last-position-of-element-in-sorted-array--medium-)
      - [2. Find Minimum in Rotated Sorted Array ( Medium )](#2-find-minimum-in-rotated-sorted-array--medium-)
      - [3. Search in Rotated Sorted Array ( Medium )](#3-search-in-rotated-sorted-array--medium-)
  - [4. Sliding Window](#4-sliding-window)

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


## 3. Binary Search
Questions:

#### 1. [Find First and Last Position of Element in Sorted Array](https://leetcode.com/problems/find-first-and-last-position-of-element-in-sorted-array/)<span style="color:red"> ( Medium )</span>
<details>
  <summary>Show code</summary>

  ```cpp
   vector<int> searchRange(vector<int>& nums, int target) {
        return {bs(nums, target, 1), bs(nums, target, 2)};
    }
    
    int bs(vector<int>& nums, int target, int mode){
        int l = 0, h = nums.size() -1, m, res = -1;
        
        while( l <= h){
            m = l + (h-l)/2;
            if(target == nums[m]) {
                res = m;
                if(mode == 1) h = m-1;
                else if(mode == 2) l = m+1;
            }else if(target < nums[m]) h = m-1;
            else l = m +1;
        }
        
        return res;
    }
   ```
</details>

#### 2. [Find Minimum in Rotated Sorted Array](https://leetcode.com/problems/find-minimum-in-rotated-sorted-array/description/)<span style="color:red"> ( Medium )</span>
<details>
  <summary>Show code</summary>

```cpp
    int findMin(vector<int>& nums) {
        int l = 0, h = nums.size()-1;
        while(l<h){
            int m = l + (h-l)/2;
            if(nums[m] <= nums[h])
              h = m;
            else
            l = m +1;
        }
        return nums[l];
        
    }
```
</details>


#### 3. [Search in Rotated Sorted Array](https://leetcode.com/problems/search-in-rotated-sorted-array/)<span style="color:red"> ( Medium )</span>

<details>
  <summary>Show code</summary>

```cpp
    int search(vector<int>& A, int target) {
        int l = 0, h = A.size()-1;
        
        while(l<=h){
            int m = l + (h-l)/2;
            if(A[m] == target) return m;
            
            //Bottom half is sorted
            if(A[l]<=A[m]){
                if(A[l]<=target && target <=A[m] )
                     h = m-1;
                else l = m+1;
                
            //upper half is sorted
            }else{
                if(A[m]<=target && target <=A[h] )
                     l = m+1;
                else h = m-1;
                
            }
        }
        return -1;
    }
```
</details>

## 4. Sliding Window

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
| [Maximum of all subarrays of size k same as Sliding Window Maximum](https://practice.geeksforgeeks.org/problems/maximum-of-all-subarrays-of-size-k3101/1) |      Medium   	| |

| [First negative integer in every window of size k ](https://practice.geeksforgeeks.org/problems/first-negative-integer-in-every-window-of-size-k3345/1) |      Easy     	| |
| [Longest Sub-Array with Sum K](https://practice.geeksforgeeks.org/problems/longest-sub-array-with-sum-k0809/1) |      Medium   	| |
| [Longest K unique characters substring](https://practice.geeksforgeeks.org/problems/longest-k-unique-characters-substring0853/1) |      Medium   	| |
| [Longest Substring Without Repeating Characters](https://leetcode.com/problems/longest-substring-without-repeating-characters/description/abcabcabc/) |      Medium   	| |
| [Minimum Window Substring](https://leetcode.com/problems/minimum-window-substring/description/) |      Medium   	| |
| [Permutation in String](https://leetcode.com/problems/permutation-in-string/description/) |      Medium   	| |
