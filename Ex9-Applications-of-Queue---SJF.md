```

Ex9 Finding the Longest Length of Nested Set in a Permutation Array
AIM:
To write a program that finds the length of the longest set s[k] defined as s[k] = { nums[k], nums[nums[k]], nums[nums[nums[k]]], … },where the iteration stops before a duplicate element occurs.


The task is to return the maximum size among all such sets.
```
```

Algorithm
Create an array nums[] and a visited[] array to track which elements have been used.
For each index k in the array, start forming the set s[k] by repeatedly jumping to nums[k].
Continue the jumps until you reach an element already marked as visited, meaning a duplicate would occur.
Count the number of unique jumps made in this chain and update the maximum length found so far.
After checking all k, return the largest size among all sets s[k].
## Program:

```
```
public class LongestSet {

    // Method to find the longest set length
    public static int arrayNesting(int[] nums) {
        int n = nums.length;
        boolean[] visited = new boolean[n];
        int maxLength = 0;

        for (int i = 0; i < n; i++) {
            if (!visited[i]) {
                int count = 0;
                int current = i;

                while (!visited[current]) {
                    visited[current] = true;
                    current = nums[current];
                    count++;
                }

                if (count > maxLength) {
                    maxLength = count;
                }
            }
        }

        return maxLength;
    }

    public static void main(String[] args) {
        int[] nums = {5, 4, 0, 3, 1, 6, 2};

        int result = arrayNesting(nums);
        System.out.println("Longest Set Length: " + result);
    }
}

```

## Output:

<img width="1609" height="515" alt="image" src="https://github.com/user-attachments/assets/b75d2b24-98ad-4ca8-aa86-47a35d0e2404" />



## Result:
Thus, the code to calculate the Total Waiting Time and Average Waiting Time in Shortest Job First scheduling algorithm is implemented successfully.
