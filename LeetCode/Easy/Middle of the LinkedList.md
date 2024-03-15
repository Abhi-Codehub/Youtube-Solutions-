# Java Solution 
## Brute Force (Using Count variable)
```
class ListNode {
    int val;
    ListNode next;
    ListNode(int x) { val = x; }
}

public class MiddleOfLinkedList {

    public ListNode middleNode(ListNode head) {
        if (head == null)
            return null;

        int count = 0;
        ListNode current = head;

        // Counting the number of nodes in the linked list
        while (current != null) {
            count++;
            current = current.next;
        }

        // Finding the middle node using the count
        current = head;
        int middleIndex = count / 2;
        for (int i = 0; i < middleIndex; i++) {
            current = current.next;
        }
        return current;
    }
}

```
## Optimal Approach (Using 2 pointers Approach)
```
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
    public ListNode middleNode(ListNode head) {

      ListNode slow = head;
      ListNode fast = head;

        if(head==null || head.next==null){
        return head;
    }
        while(fast != null && fast.next != null){
            slow = slow.next;
            fast = fast.next.next;
            
        }
        return slow;
        
    }
}
```

