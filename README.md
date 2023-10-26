# 78.-Subsets_leetcode
78. Subsets
Medium
16K
235
Companies
Given an integer array nums of unique elements, return all possible 
subsets
 (the power set).

The solution set must not contain duplicate subsets. Return the solution in any order.

 

Example 1:

Input: nums = [1,2,3]
Output: [[],[1],[2],[1,2],[3],[1,3],[2,3],[1,2,3]]
Example 2:

Input: nums = [0]
Output: [[],[0]]
 

Constraints:

1 <= nums.length <= 10
-10 <= nums[i] <= 10
All the numbers of nums are unique.

class Solution {
    public List<List<Integer>> subsets(int[] arr) {
       List<Integer> curr = new ArrayList<Integer>();
		   List<List<Integer>> ans = new ArrayList<>();
			 rect(arr, 0, curr, ans);
       return ans;
		}
	public void rect(int[] arr, int i, List<Integer> curr, List<List<Integer>> ans) {
			if(i==arr.length){
			ans.add(new ArrayList<Integer>(curr));
			return;
			}
			curr.add(arr[i]);
			rect(arr, i+1, curr, ans);
			curr.remove(curr.size()-1);
			rect(arr, i+1, curr, ans);
			
					
		}
}
