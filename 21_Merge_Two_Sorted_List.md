Problem Statement:

Merge two sorted linked lists and return it as a new sorted list. The new list should be made by splicing together the nodes of the first two lists.

Constraints:

The number of nodes in both lists is in the range [0, 50].
-100 ≤ Node.val ≤ 100

Both l1 and l2 are sorted in non-decreasing order.

Examples:

Example 1:

Input: l1 = [1,2,4], l2 = [1,3,4]

Output: [1,1,2,3,4,4]

Solution code:

    class Solution:
        def mergeTwoLists(self, l1: Optional[ListNode], l2: Optional[ListNode]) -> Optional[ListNode]:
            if not l1:
              return l2
            if not l2:
              return l1
            current=dummy=ListNode()
            while l1 and l2:
              if l1.val<l2.val:
                current.next=l1
                l1=l1.next
              else:
                current.next=l2
                l2=l2.next
              current=current.next
            if l1:
                current.next=l1
            if l2:
                current.next=l2
            return dummy.next

