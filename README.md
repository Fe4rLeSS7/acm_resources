# DSA Solution Contribution Guide & Template

This repository is designed to be a collaborative knowledge base where you can share clean, well-explained Data Structures and Algorithms (DSA) solutions. 

Good code solves the problem; great code teaches the reader *why* and *how* it works. Please use this guide and the accompanying template to ensure our repository remains organized, readable, and valuable for everyone.

---

## File Naming & Directory Structure

Please organize your solutions into the appropriate difficulty or topic folder (e.g., `DSA-Juniors/`).

*   **Directory Path:** `DSA-Juniors/{Date}-{Problem_Name}.md`
*   **Example File Path:** `DSA-Juniors/21-09-26-Bubble_Sort.md`

Use standard PascalCase, camelCase, or snake_case for problem names, and keep it consistent.

---

## Adding Images & Visuals

Visuals drastically improve the readability of complex algorithms (like Trees, Graphs, or Sliding Windows). 
* Place your images in an `assets/` or `images/` folder in the root directory.
* Reference them in your markdown file using standard syntax: `![Alt text](../assets/problem_name_diagram.png)`.
* Alternatively, you can use external image links, but local repository images are preferred to prevent broken links.

---

## Solution Template

Copy the Markdown template below, rename it to match your problem slug, fill in your solution details, and submit it via a Pull Request.

---
**(Copy the template from this block)**
---

```md
# [Problem Title](Insert link to LeetCode, Codeforces, HackerRank, etc.)

**Difficulty:** `Easy` | `Medium` | `Hard`  
**Topic:** `Arrays` / `Strings` / `Graphs` / `DP`, etc.  
**Author:** [Your Name / GitHub Handle](https://github.com/your-username)  

## 1. Problem Statement

Write a brief 1-2 sentence summary of what the problem asks you to do in your own words, or include the core challenge.

**Sample Input / Expected Output:**
> **Input:** `nums = [2, 7, 11, 15], target = 9`
> **Output:** `[0, 1]`
> **Explanation:** Because nums[0] + nums[1] == 9, we return [0, 1].

**Constraints:**
* $1 \le \text{nums.length} \le 10^4$
* $-10^9 \le \text{nums[i]} \le 10^9$
* *Mention if exactly one solution exists, or if modifying the array is allowed.*

---

## 2. Intuition & Approach

Explain your thought process step-by-step. How did you arrive at the solution?

* **Initial Thoughts (Brute Force):** Did a brute-force approach come to mind first? Why is it insufficient? (e.g., $O(N^2)$ time complexity will lead to Time Limit Exceeded).
* **Key Insight (Optimal Strategy):** What pattern or data structure unlocks the optimal solution? (e.g., Two Pointers, Sliding Window, Hash Map, BFS/DFS).

### Step-by-Step Logic
1. Initialize pointers or a hash map to track values.
2. Iterate through the input array...
3. If a specific condition is met, update the result.
4. Return the final structure.

---

## 3. Visual Explanation / Dry Run (Optional but Highly Recommended)

*Use this section to add diagrams or a step-by-step table showing how variables change during execution.*

**Test Case:** `nums = [3, 2, 4], target = 6`

| Iteration | Current Element | Target - Current | Map State (Key: Value) | Action |
| :--- | :--- | :--- | :--- | :--- |
| `i = 0` | `3` | `6 - 3 = 3` | `{}` | `3` not in map. Add `{3: 0}`. |
| `i = 1` | `2` | `6 - 2 = 4` | `{3: 0}` | `4` not in map. Add `{2: 1}`. |
| `i = 2` | `4` | `6 - 4 = 2` | `{3: 0, 2: 1}` | `2` found in map at index `1`! |
| **Result** | - | - | - | **Return `[1, 2]`** |

*(If you have a whiteboard sketch or flowchart, embed it here: `![Algorithm Flowchart](../assets/my_flowchart.png)`)*

---

## 4. Complexity Analysis

* **Time Complexity:** $\mathcal{O}(n)$ — Explain briefly why. (e.g., "We traverse the array of size $n$ exactly once. Hash map lookups take $\mathcal{O}(1)$ on average.")
* **Space Complexity:** $\mathcal{O}(n)$ — Explain briefly why. (e.g., "In the worst case, we might store $n-1$ elements in the hash map.")

---

## 5. Edge Cases Handled

* **Empty arrays / Null inputs:** How does the code behave?
* **Negative numbers / Zeroes:** Does the logic still hold?
* **Single element / No solution exists:** What is returned? 

---

## 6. Code Implementation

*Please provide clean, well-commented code. Remove any boilerplate if it distracts from the core logic.*
```

### C++
```c++
#include <vector>
#include <unordered_map>
using namespace std;

vector<int> solution(vector<int>& nums, int target) {
    unordered_map<int, int> seen;
    
    for (int i = 0; i < nums.size(); i++) {
        int complement = target - nums[i];
        if (seen.count(complement)) {
            return {seen[complement], i};
        }
        seen[nums[i]] = i;
    }
    
    return {}; 
}
```

### Python
```python
def solution(nums: list[int], target: int) -> list[int]:
    # Stores the seen numbers and their indices
    seen = {}
    
    for i, num in enumerate(nums):
        complement = target - num
        if complement in seen:
            return [seen[complement], i]
        seen[num] = i
        
    return [] # Expected output if no solution exists
```

### C
```C
#include <stdlib.h>

// Note: C implementation often requires manual hash map creation or nested loops.
// This is a naive O(n^2) approach for demonstration.
int* solution(int* nums, int numsSize, int target, int* returnSize) {
    int* result = (int*)malloc(2 * sizeof(int));
    *returnSize = 2;
    
    for(int i = 0; i < numsSize; i++) {
        for(int j = i + 1; j < numsSize; j++) {
            if(nums[i] + nums[j] == target) {
                result[0] = i;
                result[1] = j;
                return result;
            }
        }
    }
    
    *returnSize = 0;
    return NULL;
}
```

### Java
```java
import java.util.HashMap;
import java.util.Map;

class Solution {
    public int[] solution(int[] nums, int target) {
        Map<Integer, Integer> seen = new HashMap<>();
        
        for (int i = 0; i < nums.length; i++) {
            int complement = target - nums[i];
            if (seen.containsKey(complement)) {
                return new int[] { seen.get(complement), i };
            }
            seen.put(nums[i], i);
        }
        
        return new int[]{};
    }
}
```

### Rust
```rust
use std::collections::HashMap;

impl Solution {
    pub fn solution(nums: Vec<i32>, target: i32) -> Vec<i32> {
        let mut seen = HashMap::new();
        
        for (i, &num) in nums.iter().enumerate() {
            let complement = target - num;
            if let Some(&index) = seen.get(&complement) {
                return vec![index as i32, i as i32];
            }
            seen.insert(num, i);
        }
        
        vec![]
    }
}
```
