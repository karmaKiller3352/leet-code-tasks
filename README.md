### 232. Implement Queue using Stacks


```
var MyQueue = function() {
    this.queue = []
};

/** 
 * @param {number} x
 * @return {void}
 */
MyQueue.prototype.push = function(x) {
    this.queue.push(x)
};

/**
 * @return {number}
 */
MyQueue.prototype.pop = function() {
   return this.queue.shift()
};

/**
 * @return {number}
 */
MyQueue.prototype.peek = function() {
    return this.queue[0]
};

/**
 * @return {boolean}
 */
MyQueue.prototype.empty = function() {
    return this.queue.length === 0
};
```

![Test](https://github.com/karmaKiller3352/leet-code-tasks/blob/main/assets/queue.png)

### 206. Reverse Linked List

```
/**
 * Definition for singly-linked list.
 * function ListNode(val, next) {
 *     this.val = (val===undefined ? 0 : val)
 *     this.next = (next===undefined ? null : next)
 * }
 */
/**
 * @param {ListNode} head
 * @return {ListNode}
 */

const reverseListIterate = function(head) {
    let [prev, current] = [null, head]
    
    while(current) {
        [current.next, prev, current] = [prev, current, current.next]
    }
    
    return prev
};

const reverseList = function(head, prev = null) {
    if (!head) {
        return prev
    }
    
    const next = head.next;
    head.next = prev;
    
    return reverseList(next, head);
};
```

![Test](https://github.com/karmaKiller3352/leet-code-tasks/blob/main/assets/linked-list.png)

### 100. Same Tree

```
/**
 * Definition for a binary tree node.
 * function TreeNode(val, left, right) {
 *     this.val = (val===undefined ? 0 : val)
 *     this.left = (left===undefined ? null : left)
 *     this.right = (right===undefined ? null : right)
 * }
 */
/**
 * @param {TreeNode} p
 * @param {TreeNode} q
 * @return {boolean}
 */

var isSameTree = function(p, q) {
    if (!p && !q) return true
    
    if (!p || !q) return false;
    
    if (p.val !== q.val) return false
    
    if (!isSameTree(p.left, q.left)) return false
    
    if (!isSameTree(p.right, q.right)) return false
 
    return true
};
```
![Test](https://github.com/karmaKiller3352/leet-code-tasks/blob/main/assets/same-tree.png)

### 53. Maximum Subarray

```
/**
 * @param {number[]} nums
 * @return {number}
 */
var maxSubArray = function(nums) {
    let globalMax = -Number.MAX_VALUE;
    let localMax = 0;
    
    for (let i = 0; i < nums.length; i++) {
        globalMax = Math.max(globalMax, localMax + nums[i])
        
        localMax = Math.max(localMax + nums[i], 0)
    }
    
    return globalMax
};
```
![Test](https://github.com/karmaKiller3352/leet-code-tasks/blob/main/assets/maximum-subarray.png)

### 1. Two Sum

```
/**
 * @param {number[]} nums
 * @param {number} target
 * @return {number[]}
 */
var twoSum = function(nums, target) {
    const map = new Map()
    
    for(let i = 0; i < nums.length; i++) {
        const char = nums[i]
        const diff = target - char
        
        if (map.has(diff)) {
            return [map.get(diff), i]
        }
        
        map.set(char, i)
    }
    return []
};
```
![Test](https://github.com/karmaKiller3352/leet-code-tasks/blob/main/assets/two-sum.png)