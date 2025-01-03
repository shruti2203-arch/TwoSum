# TwoSum
The problem is Solved By using DataStructure : HashMap

import java.util.HashMap; 

public class TwoSum {
    public static int[] findTwoSum(int[] nums, int target) {
        // Creating Hashmap For storing Nums and their Indices
        HashMap<Integer, Integer> map = new HashMap<>();

        
        for (int i = 0; i < nums.length; i++) {
            //find complent target-nums
            int complement = target - nums[i];
            //Check if compkement already exist in map
            if (map.containsKey(complement)) {
               //return indices of two numbers
                return new int[] { map.get(complement), i };
            }

            // Add the current number and its index to the map
            map.put(nums[i], i);
        }

      //Exception to be decleared if their is no solution
        throw new IllegalArgumentException("No two sum solution");
    }

    public static void main(String[] args) {
        int[] nums = {3,4,7,4,1};
        int target = 8;

        try {
            int[] result = findTwoSum(nums, target);
            System.out.println("Indices: " + result[0] + ", " + result[1]);
        } catch (IllegalArgumentException e) {
            System.out.println(e.getMessage());
        }
    }
}
