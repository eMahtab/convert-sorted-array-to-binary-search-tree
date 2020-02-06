# Convert Sorted Array to Binary Search Tree
### https://leetcode.com/problems/convert-sorted-array-to-binary-search-tree

Given an array where elements are sorted in ascending order, convert it to a height balanced BST.

For this problem, a height-balanced binary tree is defined as a binary tree in which the depth of the two subtrees of every node never differ by more than 1.
```
Example:

Given the sorted array: [-10,-3,0,5,9],

One possible answer is: [0,-3,9,-10,null,5], which represents the following height balanced BST:

      0
     / \
   -3   9
   /   /
 -10  5
 ```
 
 ## Implementation :
 
 ```java
 /**
 * Definition for a binary tree node.
 * public class TreeNode {
 *     int val;
 *     TreeNode left;
 *     TreeNode right;
 *     TreeNode(int x) { val = x; }
 * }
 */
class Solution {
    public TreeNode sortedArrayToBST(int[] nums) {
        if(nums == null || nums.length == 0)
            return null;
        return constructTree(nums, 0, nums.length - 1);
    }
    
    public TreeNode constructTree(int[] nums, int left, int right){
        if(left > right)
            return null;
        int mid = left + (right - left) / 2;
        TreeNode node = new TreeNode(nums[mid]);
        node.left = constructTree(nums, left, mid -1);
        node.right = constructTree(nums, mid+1, right);
        return node;
    }
}
 
 ```
 
 ## References :
 1. https://www.youtube.com/watch?v=PZYTs9y4f4o
 2. https://www.youtube.com/watch?v=12omz-VAyRk
 
