# Next greater node in linked list
You are given the head of a linked list with n nodes.

For each node in the list, find the value of the next greater node. That is, for each node, find the value of the first node that is next to it and has a strictly larger value than it.

Return an integer array answer where answer[i] is the value of the next greater node of the ith node (1-indexed). If the ith node does not have a next greater node, set answer[i] = 0.

### Constraints:
1. The number of nodes in the list is n.
2. 1 <= n <= 104
3. 1 <= Node.val <= 109
