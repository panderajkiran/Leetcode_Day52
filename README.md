# Leetcode_Day52
# Day 52 — Linked List Cycle

## 🧩 Problem

Given the head of a linked list, determine whether the linked list contains a cycle.

A cycle exists when a node's `next` pointer points back to a previous node instead of becoming `null`.

**LeetCode:** 141. Linked List Cycle  
**Difficulty:** Easy  
**Language:** Java

---

## 💡 Approach

I used **Floyd's Cycle Detection Algorithm**, also known as the **Slow and Fast Pointer** technique.

- `slow` moves one node at a time.
- `fast` moves two nodes at a time.
- If there is a cycle, both pointers will eventually meet.
- If there is no cycle, `fast` will reach `null`.

### Java Code

```java
public class Solution {
    public boolean hasCycle(ListNode head) {

        ListNode slow = head;
        ListNode fast = head;

        while (fast != null && fast.next != null) {

            slow = slow.next;
            fast = fast.next.next;

            if (slow == fast) {
                return true;
            }
        }

        return false;
    }
}
🔍 Example

Input:

[3, 2, 0, -4]

The last node points back to the node containing 2.

So, the linked list contains a cycle.

Output:

true

⏱️ Complexity
Time Complexity

O(n)

In the worst case, we may need to traverse the linked list.

Space Complexity

O(1)

Only two pointers are used, so no extra data structure is required.

📚 What I Learned

Today I learned how the slow and fast pointer technique can detect a cycle without using extra memory.

The interesting part is that even though both pointers move at different speeds, if a cycle exists, the faster pointer will eventually catch the slower pointer.

This is a useful technique for many linked-list problems.

🎯 Takeaway

Today's lesson was simple:

Sometimes, you don't need extra memory to solve a problem — you just need to look at how the pointers move.

Another day of learning, another small step forward. 🚀
