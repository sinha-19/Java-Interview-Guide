# 14. Java Interview Coding Patterns & Problem Types

---

## Common Coding Problem Types

1. **Arrays and Strings**
   - Reverse an array/string
   - Find duplicates
   - Two Sum, Subarray Sum
   - Anagram checks, Palindrome detection

2. **Linked Lists**
   - Reverse a linked list
   - Detect loop/cycle
   - Merge two sorted lists

3. **Stacks and Queues**
   - Implement stack/queue using arrays or linked lists
   - Balanced parentheses

4. **Trees**
   - Binary tree traversals (inorder, preorder, postorder)
   - Depth/height calculation
   - Lowest common ancestor

5. **Graphs**
   - BFS, DFS
   - Detect cycles
   - Shortest path (Dijkstra, BFS for unweighted)

6. **Recursion & Backtracking**
   - Factorial, Fibonacci
   - Subsets, permutations
   - N-Queens, Sudoku solver

7. **Sorting & Searching**
   - Binary search
   - Quick sort, Merge sort
   - Custom comparators

8. **Hashing**
   - HashMap/HashSet use
   - Find first unique element

9. **Dynamic Programming**
   - Coin change
   - Longest increasing subsequence
   - Edit distance

10. **OOP Design**
    - Design patterns (Singleton, Factory, Observer)
    - Class design for real-world objects (e.g., Library System)
    - LRU Cache

---

## Java-Specific Patterns & Tips

- **Use of Collections:** Prefer `HashMap`, `HashSet`, `ArrayList` for efficiency.
- **Custom Comparators:** Use `Comparator<T>` for sorting complex objects.
- **Immutability:** Make helper objects immutable when possible.
- **Edge Cases:** Always check for `null`, empty input, and boundary conditions.

---

## Sample Interview Code Template

```java
public class Solution {
    public int someMethod(int[] arr) {
        // Validate input
        if (arr == null || arr.length == 0) return -1;
        
        // Main logic
        for (int i = 0; i < arr.length; i++) {
            // process arr[i]
        }
        
        return result;
    }
}
```

---

## Example: Reverse a Linked List

```java
class ListNode {
    int val;
    ListNode next;
    ListNode(int x) { val = x; }
}

public ListNode reverseList(ListNode head) {
    ListNode prev = null, curr = head;
    while (curr != null) {
        ListNode nextTemp = curr.next;
        curr.next = prev;
        prev = curr;
        curr = nextTemp;
    }
    return prev;
}
```

---

## Interview Tips

- **Clarify Requirements:** Repeat the problem statement in your own words and confirm details.
- **Discuss Approach:** Outline your plan before coding.
- **Write Clean Code:** Use descriptive names, modularize logic.
- **Test Cases:** Write tests for edge and typical cases.
- **Time & Space Complexity:** Be ready to explain and optimize.

---

## Possible Follow-Up Questions

- How would you optimize your solution?
- What is the space and time complexity?
- How does your code handle invalid input?
- Can you generalize your approach for similar problems?

---

## Final Words

- Practice coding under time constraints.
- Review Java standard library features.
- Communicate clearly during interviews.
- Stay calm — problem-solving skills matter most!
