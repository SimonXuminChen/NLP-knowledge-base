---
description: 重点，大厂面试的侧重点，基础很重要。
---

# 算法基础



### 时间复杂度&空间复杂度

* 时间复杂度：运行这个程序需要多少时间
* 空间复杂度：运行这个程序需要多少内存

计算复杂度一般都用 **O notation** 去表示，符号为**O\(\)**

定理：如果算法X的时间复杂度优于Y的时间复杂度，那么存在一个足够大的数M，当n&gt;M时，可以保证X的实际效率要优于Y的实际效率。

O\(log n\)一般都是搜索一个element的算法的复杂度，如tree，heap，binary search

O\(n \* log n\)一般都是quick sort，merge sort，heapsort



### 

\*\*\*\*

\*\*\*\*

### **Master Theorem 主方法定理**

可以通过主方法定理去判断递归情况下的复杂度.

当我们的结构目标可以表达成此式时： ****$$T(n) = aT(\frac {n} {b})+f(n)$$ 我们可以用**Master Theorem**去判断该结构的时间复杂度，我们不过分讨论引用中的复杂公式，也不考虑各种符号的含义，将三个函数符号统一看成**O notation**，用最简单的话来说，就是将三个式子中公有的 $$n^{\log_ba}$$ 这一项与 $$f(n)$$ 进行大小比较，然后根据大小的三种情况，得出该情况下的复杂度大小，具体的公式可以参考下图。

![Master Theorem](.gitbook/assets/image%20%283%29.png)

_Reference:_[_http://people.csail.mit.edu/thies/6.046-web/master.pdf_](http://people.csail.mit.edu/thies/6.046-web/master.pdf)\_\_

### 递归问题

**注意，解递归问题一定要有base case！！！**

为了更好的记住并理解递归，引入著名的Fibonacci数列来解释并举例。

```python
Fibonacci 
有一个无穷数列:[0, 1, 1, 2, 3, 5, 8, 13, 21, 34...]
其中每一个数都是前两个数的和

从该数列可知，前两个数是0，1，我们先来用暴力法去试试：

def Fibonacci(n):
    n1 = 0
    n2 = 1
    for i in range(1,n):
        result = n1+n2
        n1 = n2
        n2 = result
        
    return result
    
当然，为了方便说明，这里只是简写，还有一些情况我没有考虑，面试和刷题的时候记得考虑上。
```

但是无疑这样的时间复杂度是非常高的，所以我们用递归的方法，去实现它，什么是递归呢？

递归就是在定义函数的时候，调用自身函数，我们将上面的Fibonacci函数用递归的方法重写一下：

```python
def Fibonacci(n):
    if n<3:
        return 1
    return Fibonacci(n-2)+Fibonacci(n-1)
```

这样应该看得懂了吧！

那么接下来，考虑一下递归算法的时间复杂度和空间复杂度，像这种情况，我们该怎么去计算呢？我们引入递归树这个概念，递归树和Master Theorem一样，都是用来计算时间复杂度的，不过递归树一般用于递归的情况

#### 递归树

如下图所示，这就是一棵自上而下的递归树，每个节点记录一个数值

![&#x9012;&#x5F52;&#x6811;&#xFF0C;&#x5047;&#x8BBE;n=8](.gitbook/assets/image%20%281%29.png)

树的深度为H，每个节点都有两个子节点（叶子结点除外），因此我们可以得知每层有 $$2^n$$ 个操作点，总的时间复杂度为 $$O(8) = O (2^0)+O(2^1)+O(2^2)+...$$ 所以递归算法的时间复杂度也就是 $$O(2^n)$$ ，而空间复杂度就是结点的个数。

但是这里就引出了另外一个问题了，从上图可知，有些结点的数值重复了很多次，那么这个问题我们该怎么解决呢？

### 动态规划

### 基本排序算法

#### 归并排序 Merge Sort

归并排序属于**Divide & Conquer的算法种类范畴**
