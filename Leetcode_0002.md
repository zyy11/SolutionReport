# Leetcode 2 Add Two Numbers

## 问题重述

给定两个以单链表倒序存储的数`l1`、`l2`，计算其和，并以单链表形式输出。

### 样例输入
l1=(2 -> 4 -> 3), l2=(5 -> 6 -> 4)

### 样例输出

7 -> 0 -> 8

### 样例解释
342+465=807

### 单链表节点定义

```
Definition for singly-linked list.
class ListNode:
    def __init__(self, x):
        self.val = x
        self.next = None
```

## 解法：模拟
