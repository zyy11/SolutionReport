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
    def __init__(self, val=0, next=None):
        self.val = val
        self.next = next
```

## 解法：模拟

用carry变量存储进位，在每一位上获取l1和l2对应位上的数值x和y（若已到达链表结尾则置0）
利用x+y+carry计算该数位结果和进位
移动到下一位（若已到达链表结尾则不移动）
若计算完毕，carry不为零，则还需要添加一个节点

### 代码

```
class Solution:
    def addTwoNumbers(self, l1: ListNode, l2: ListNode) -> ListNode:
        carry=0
        p=l1
        q=l2
        ans=ListNode()
        cur=ans
        
        while p!=None or q!=None:
            if p==None:
                x=0
            else:
                x=p.val
            if q==None:
                y=0
            else:
                y=q.val
                
            digit=x+y+carry
            carry=digit//10
            cur.next=ListNode(digit%10)
            cur=cur.next
            
            if p!=None: 
                p=p.next
            if q!=None:
                q=q.next
                
        if carry>0:
            cur.next=ListNode(carry)
        return ans.next
```
