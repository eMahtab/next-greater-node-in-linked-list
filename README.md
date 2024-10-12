# Next greater node in linked list
You are given the head of a linked list with n nodes.

For each node in the list, find the value of the next greater node. That is, for each node, find the value of the first node that is next to it and has a strictly larger value than it.

Return an integer array answer where answer[i] is the value of the next greater node of the ith node (1-indexed). If the ith node does not have a next greater node, set answer[i] = 0.

### Constraints:
1. The number of nodes in the list is n.
2. 1 <= n <= 104
3. 1 <= Node.val <= 10^9

## Implementation :
```java
/**
 * Definition for singly-linked list.
 * public class ListNode {
 *     int val;
 *     ListNode next;
 *     ListNode() {}
 *     ListNode(int val) { this.val = val; }
 *     ListNode(int val, ListNode next) { this.val = val; this.next = next; }
 * }
 */
class Solution {
    public int[] nextLargerNodes(ListNode head) {
        if(head == null)
          return new int[0];
        if(head.next == null)
          return new int[]{0};

        List<int[]> result = new ArrayList<>();
        Stack<int[]> stack = new Stack<>();
        ListNode curr = head;
        int index = 0;
        while(curr != null) {
            while(!stack.isEmpty() && curr.val > stack.peek()[1]) {
                int[] node = stack.pop();
                result.add(new int[]{node[0], curr.val});
            }
            stack.push(new int[]{index, curr.val});
            index++;
            curr = curr.next;
        }
        while(!stack.isEmpty()) {
            int[] node = stack.pop();
            result.add(new int[]{node[0], 0});
        }
        int[] output = new int[index];
        for(int[] num : result) {
            output[num[0]] = num[1];
        }
        return output;  
    }
}
```

# References :
1. https://github.com/eMahtab/daily-temperatures (Same problem but on an array)
