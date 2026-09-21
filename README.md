# DSA Solution Contribution Guide & Template
This repository is designed to be a collaborative knowledge base where you can share clean, well-explained Data Structures and Algorithms (DSA) solutions. 

Good code solves the problem; great code teaches the reader *why* and *how* it works. Please use this guide and the accompanying template to ensure our repository remains organized, readable, and valuable for everyone.

---

## File Naming & Directory Structure

Please organize your solutions into the DSA (1st Year) folder.

*   **Directory Path:** `DSA-Juniors/{Date-Problem_name}.md`
*   **Example File Path:** `DSA-Juniors/21-09-26-Bubble_sort.md`

Use the same naming convention as used above.

---

## Solution Template

Copy the Markdown template below, rename it to match your problem slug, fill in your solution details, and submit it via a Pull Request.

```markdown
# [Problem Title](Insert link to LeetCode, Codeforces, HackerRank, etc.)

**Difficulty:** Easy | Medium | Hard  
**Topic:** Arrays / Strings / Graphs / DP, etc.  
**Author:** Your Name / Handle  

---

## Problem Statement

Write a brief 1-2 sentence summary of what the problem asks you to do in your own words, or include the core challenge.

---

## Intuition & Approach

Explain your thought process step-by-step. How did you arrive at the solution?

1. **Initial Thoughts:** Did a brute-force approach come to mind first? Why is it insufficient?
2. **Key Insight:** What pattern or data structure unlocks the optimal solution? (e.g., Two Pointers, Sliding Window, Memoization, BFS/DFS).
3. **Step-by-Step Logic:**
   * Step 1: Initialize pointers or data structures.
   * Step 2: Iterate through the input...
   * Step 3: Handle edge cases.

---

## Complexity Analysis

* **Time Complexity:** $O(n)$ — Explain briefly why (e.g., "We iterate through the array of size $n$ exactly once").
* **Space Complexity:** $O(1)$ — Explain briefly why (e.g., "Only constant extra space is used for pointers").

---

## Code Implementation

Create code blocks like those done below.
```

### C
```c
#include <stdlib.h>

int* solution() {
    // Your clean, commented code here
    return NULL;
}
```

### C++
```cpp
#include <bits/stdc++.h>
using namespace std;

vector<int> solution(vector<int>& nums, int target) {
    // Your clean, commented code here
    return {};
}
```

### Python 3
```python
def solution(nums, target):
    # Your clean, commented code here
    pass
```

### Java
```java
import java.util.*;

class Solution {
    public int[] solution(int[] nums, int target) {
        // Your clean, commented code here
        return new int[]{};
    }
}
```

### Rust
```rust
impl Solution {
    pub fn solution(nums: Vec<i32>, target: i32) -> Vec<i32> {
        // Your clean, commented code here
        vec![]
    }
}
```
