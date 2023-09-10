# 26. Remove Duplicates from Sorted Array

Given an integer array nums sorted in non-decreasing order, remove the duplicates in-place such that each unique element appears only once. The relative order of the elements should be kept the same. Then return the number of unique elements in nums.


Consider the number of unique elements of nums to be k, to get accepted, you need to do the following things:

-Change the array nums such that the first k elements of nums contain the unique elements in the order they were present in nums initially. The remaining elements of nums are not important as well as the size of nums.

-Return k.

_______________________________________________________________________

Intuition 1: Two Pointers in the Same Direction

if(nums.length == 1) return 1;
if(nums[0] == nums[1] && nums.length == 2) return 1;

Initialize i=1, j = 1;

if nums[0] == nums[1] then j++
  for(j=1; j < nums.length; j++){
      if nums[i] != nums[j] then nums[i] == nums[j] and i++
  }
 return i

 This pseudocode is wrong. We shouldn't compare nums[i] with nums[j], they are two independent segments. What we should compare is nums[j] and nums[j-1] since duplicates appear consecutively.
