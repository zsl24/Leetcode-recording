# Leetcode-recording
leetcode 刷题思路与打卡

## 2020.5.27

#### NO.1 两数之和 easy 数组

#### NO.2 两数相加 mid 链表

#### N0.7 整数反转 easy  数学

#### N0.20 有效括号 easy 栈 字符串

栈是在表尾进行插入和删除操作的线性表。进行插入和删除操作的称为栈顶，表头为栈底。

队列是在表的前端进行删除操作，在表的后端插入元素。进行删除操作的称为队头，进行

插入操作的称为队尾。

## 2020.5.28

#### NO.21 合并两个有序列表 easy

#### NO.83 删除排序列表中的重复元素 easy

## 2020.5.29

#### NO.141 环形列表 easy 快慢指针追逐法 哈希表查询法

#### NO.225 用队列实现栈 easy

#### NO.206 反转链表 

## 2020.5.30

#### NO.976 三角形最大周长 easy

 对数组进行降序排序，从开始选三个元素就符合了三角形a>b>=c的原则，再查看是否满足a<b+c的条件，若不满足，则a往后遍历。

#### NO.9 回文数 easy

## 2020.6.1 

#### NO.1431 拥有最多糖果的孩子 easy

## 2020.5.31

#### NO.26 删除排序数组中的重复项 easy 时间复杂度低解法

len_new为改后数组索引，遍历数组，若下一个元素与该元素不同，则nums[len_new]赋值，len_new+1，若不同，则继续遍历，直到遇到不同元素，对len_new进行赋值。该方法在没有使用额外空间的情况下，利用新的索引，创造了新的虚拟数组。

#### NO.38 外观数列 easy 60mins

#### NO.443 压缩字符串 easy

这道题和NO.26很相似，都是涉及到原地算法。原地算法要求算法不使用除了输入以外的空间进行操作，只能原地进行数组修改。所以只能用“指针”，即列表中的索引进行处理。通过anchor指针来指向每一字符块的起点，用read指针指向当前迭代指向的元素，用write来指向改写数组的位置。当read指针对应的元素处于字符块终点，则用write指针写入当前元素，写完一次write就往后指一个位置，并通过read - anchor + 1来计算字符块大小，并用write将大小写入数组。

## 2020.6.3

### 时间复杂度

是指执行当前算法所消耗的时间

时间复杂度公式：$T(n)=O(f(n))$

$f(n)$表示每行代码执行次数之和，而$O$表示正比例关系，这个公式的全称是：**算法的渐进时间复杂度**，用来表示代码执行时间的增长变化趋势。

常见的时间复杂度量级有：

- 常数阶O(1)

  无论代码执行了多少行，只要是没有循环结构，这个代码的时间复杂度就都是$O(1)$。

- 对数阶O(logN)

  ```c++
  int i = 1;
  while(i<n)
  {
      i = i * 2;
  }
  ```

  循环将会执行到$i>2^{n}$才会停止，则循环的次数x为$x=log(2^{n})$，则代码的时间复杂度为：$O(logn)$

- 线性阶O(n)

  ```c++
  for(i=1; i<=n; ++i)
  {
     j = i;
     j++;
  }
  ```

  这段代码中，for循环里面的代码会执行n遍，因此它消耗的时间是随着n变化而变化的。

- 线性对数阶O(nlogN)

  就是将时间复杂度为$O(logn)$的代码循环N遍

- 平方阶O(n²)

  将$O(n)$的代码再嵌套循环一遍，时间复杂度就是$O(n^{2})$

- 立方阶O(n³)

  三层循环

- K次方阶O(n^k)

  k层循环

- 指数阶(2^n)

### 空间复杂度

是指执行当前算法需要占用多少内存空间

计算算法在运行过程中临时占用存储空间大小的一个度量

- $O(1)$

  代码中所占用的空间不随着处理数据的过程中变化，因此其空间复杂度为$O(1)$

- $O(n)$

  ```c
  int[] m = new int[n]
  for(i=1; i<=n; ++i)
  {
     j = i;
     j++;
  }
  ```

  一开始分配了大小为n的数组

NO.28 实现strStr() easy

## 2020.6.5

#### NO.19 删除链表的倒数第N个节点 med

- 方法1：利用list从存储列表内容，再利用list.pop()删除内容，再将list内容赋值给链表。

（注意：有链表大小只有1，或者要删除头节点，则应该在头节点前设置哑节点）

- 方法2：不需要另外内存空间放列表，直接操作链表。

先遍历一次链表获得链表长度L，再遍历一次链表直到指针指到第L-N个结点，将该节点的next指向下下个节点，就完成了删除任务。

（注意：有些链表大小只有1，或者要删除头节点，则应该在头节点前设置哑节点）

#### NO.13 罗马数字转整数 easy

这道题最主要的思维是要发现罗马数字的规律。某一个字符和下一个字符的关系有两种，一种是该字符大于下一个字符，这是正常情况，只需要简单加上该字符的值就可以；另一种是该字符小于下一个字符，则加上的数值应该是下一个字符的值减去该字符的值。

则代码只需要遍历数组，判断当前字符和下一个字符的关系来决定要加的数值。

#### NO.27 移除元素 easy

#### NO.203 移除链表元素 easy

算法：

- 初始化哨兵节点为 ListNode(0) 且设置 sentinel.next = head。
- 初始化两个指针 curr 和 prev 指向当前节点和前继节点。
- 当 curr != nullptr：
  - 比较当前节点和要删除的节点：
    - 若当前节点就是要删除的节点：则 prev.next = curr.next。
    - 否则设 prve = curr。
  - 遍历下一个元素：curr = curr.next。
- 返回 sentinel.next。



## 2020.7.2

#### NO.82 删除排序列表中的重复元素II medium

利用前后两个指针，前面的指针用来检测重复元素，后面的指针负责删除所有重复元素。

#### NO.234 回文列表 easy

部分逆序法：利用快慢指针找到链表的中点，然后从中点对链表的后半部分进行逆序，最后将这个逆序与链表前半部分进行逐一对比，查看是否一致。

栈方法：将元素一一入栈，再让元素一一出栈，比较两个序列。



## 2020.7.6 

#### NO.24 两两交换链表中的节点 medium

输入：1 → 2 → 3 → 4      输出：2 → 1 → 4 → 3 

递归方法：
先将方法抽象化，A为交换两元素的第一个元素，B为第二个，若要完成交换的过程，则A首先指向已经完成交换的新链表的表头，B指向A，这就完成了一次交换。

```python
first.next = swapPairs(second.next) 
second.next = first
```

#### NO.1608 面试题 删除中间节点 easy



## 2020.7.8

#### NO.445 两数相加II medium

先将链表进行倒序，再进行带进位的逐位相加，然后再每次计算结果倒序存储。

#### NO.67 二进制求和 easy

#### NO.387 字符串中的第一个唯一字符 easy



## 2020.7.9

#### NO.415 字符串相加 easy

#### NO.58 最后一个单词的长度 easy



## 2020.7.11

#### NO.151 翻转字符串中的单词 medium

双解法，一种语言API直接暴力解法

另一种是堆栈法

#### NO.88 合并两个有序数组 easy

将p1p2分别指向两个数组的有效末端，并且将p指向合并数组的有效末端。

比较p1和p2指向的值，p的值等于两者较大值。这样从大到小，从列表尾部向头部，逐个降序插入元素。最后p1p2任意一个指针到头，都会结束迭代。最后将nums2数组剩下未被访问的元素，放到nums1的数组最开头的位置。因为如果nums2还剩下元素未被访问，则说明此时nums1的元素已经放置完毕，剩下的空位正是留给nums2剩下的元素。

这个解法真的很巧。

#### NO.1160 拼写单词 easy

#### 剑指offer53. 0~1中缺失的数字 easy



## 2020.7.13

#### NO.242 有效的字母异位词 easy 13mins

#### NO.35 搜索插入位置 easy 11mins

## 2020.7.16

#### NO.349 两个数组的交集 easy

## 2020.7.17

#### NO.136 只出现一次的数字 easy

#### NO.160 相交链表 easy

## 2020.7.20

#### NO.237 删除链表中的节点 easy

#### NO.206 反转链表  easy

#### 面试题 02.01 移除重复节点 easy

## 2020.7.22

#### NO.86 分隔链表 medium

#### NO.101 高度检查器 easy

## 2020.7.23

#### NO.217 存在重复元素 easy

## 2020.7.24

#### 面试题 02.07 链表相交 easy

题目中的链表是无环的，则无环链表相交情况只有一种：

1  →  2  →   3 → 8

5  →  5  → 4 ↑

即开头无重复节点，从相交处开始，共用节点，一直到最后。

首先，遍历两个链表，使得指针一直直到最后节点，如果两个节点不一样，则说明不相交，同时记录两个链表长度。

若相交，则长的链表开始指针往前走 长度差 个节点，然后两个链表节点开始往下走，走到相同节点就是相交节点。



#### NO.138 复制带随机指针列表 medium

两种方法：

①哈希表：空间复杂度0(N) 笔试用

遍历老链表，建立哈希表，key是老链表节点，value是新链表节点，建立起新老节点对应的关系

再次遍历老链表，或者遍历哈希表，设置新节点的random指针，新节点random指针是通过老节点的random指针指向的老节点对应的新节点来确定的；设置新节点的next指针，新节点的next指针是通过老节点的next指针指向的老节点对应的新节点来确定的。

②级联新旧节点：空间复杂度O(1) 面试用

级联新旧节点，方式是，将新节点插入到对应老节点的后面，类似于：

老1 → 新1 → 老2 → 新2 → None

老节点通过next指针找到对应新的节点，这样就代替了哈希表的mapping作用。

这时候，要先设置random再设置next，两步在不同循环，因为在random还没有全部设置好的情况下，改动next指针将会破坏这种新老对应关系。

先设置random指针，新节点的random指针是通过老节点的random指针指向的老节点对应的新节点来确定的。

再设置next指针，新节点的next指针就是它的下下个节点。



## 2020.7.25

#### NO.102 二叉树的层序遍历 medium

广度优先遍历，即二叉树从根节点从上往下从左往右逐层遍历，并且逐层存储节点值。

这就用到队列。

设置哈希表，key是节点，value是节点所在层

首先将头节点入队列；

然后进入循环：

{弹出一个节点；

先后将该节点的左孩子和右孩子入队列；

判断该节点是否为某层第一个节点，若是，则结算上层节点，即，将上层所有节点列表写入总列表

若不是，则将该节点写入该层节点列表

}



#### NO.662 二叉树最大宽度 medium

#### 面试题04.04 检查平衡性 easy

#### NO.662 二叉树最大宽度 medium

#### NO.958 二叉树的完全性检验medium

#### NO700 . 二叉搜索树中的搜索 easy

#### NO.102 二叉树的层序遍历 medium



## 2020.8.5 

#### NO.208 实现前缀树 med

#### NO.125 验证回文串 easy

#### NO.110 平衡二叉树 easy

#### NO.51 N皇后 hard



## 2020.8.6 

#### 剑指Offer 41 数据流中的中位数 hard

该方法用到了两个堆，一个大根堆，一个小根堆。

利用大根堆来接收数据流较小的数字，小根堆接受数据流中较大的数字，同时保持大小根堆的大小差值不为1，这样就能保证中位数保持在大根堆或小根堆的堆头。

具体做法是：

把第一个数字放入大根堆。

加入一个数字的操作：

1.查看这个数字于大根堆堆头大小关系（也可以是小根堆，只要初始化的时候把数字放在小根堆就行），大于堆头，数字放小根堆，小于等于堆头，数字放大根堆

2.修正大根堆小根堆大小，若其中一方的尺寸比另一边大2，则把起堆头弹出送到另一边。

如何查看当前数据流的中位数：

判断大根堆小根堆的大小关系：
①两个堆相同，则已输入数据量为偶数，中位数为两个堆的头的平均值；

②大根堆大1，则中位数为大根堆堆头

③小根堆大1，则中位数为小根堆堆头



#### NO.23 合并K个排序链表 hard

这道题就可以使用归并排序的思想。

K个链表可以由两个K/2个链表合并，其中K/2个链表又可以由两个K/4个链表合并。这样分割递归的base case是当分到只有两个链表，开始通过归并将两个链表合并起来。

合并两个链表需要申请额外空间生成新的链表，具体的做法是：

①分别用两个指针分别指向两个链表的表头，两个指针代表了链表的当前节点；

②对比两个指针的节点大小，较小的那个值送到新的链表中。链表中每取走一个值，指针都往后走一格；

③周而复始，总有一边指针会指到尾部，此时再把另一边的剩余部分补充到新链表中，就完成了归并。

#### NO.94 二叉树的中序遍历 med

这道题利用了递归算法解决。

中序遍历是对于一棵树，先访问左子树的节点，再访问根节点，最后访问右子树的节点。

那么来到一个节点，则先访问这个节点的左子树，将遍历结果加入res列表，访问完左子树，再加入当前节点的值到结果中，最后再访问右子树。

base case是当前节点为空，则不执行语句直接返回。



## 2020.8.7

#### NO297.二叉树的序列化与反序列化 hard

二叉树的序列化是指将二叉树的节点值按照一定顺序转化为字符串；

二叉树的反序列化是将字符串按照一定规则转化为二叉树。

这道题中所要求的序列是二叉树的层序遍历，涉及到二叉树的层序遍历，那就一定要用到队列，先进先出。

**二叉树序列化**层序遍历的算法如下：

①加入树的根节点到队列

循环 （当队列不为空）：

②从队列中弹出一个节点；

③进行相应处理，可以是打印，或者加入结果列表，本题是将值加入字符串中；

③若有，先后将左右孩子放入队列中（到时候会先访问左孩子，因为左孩子先放）

循环结束

**二叉树反序列化**

①取字符串第一个值为头节点，将头节点加入队列；设置i指向第二个字符

*循环（队列不为空）*：

②从队列中弹出一个节点，为当前节点；

③判断i是否是有效值，若是，则该值是当前节点的左孩子，并将左孩子加入队列；

④i往后移一位，因为字符串该位置已经检测过了；

⑤判断i是否是有效值，若是，则该值是当前节点的右孩子，并将右孩子加入队列；

⑥i往后移一位

*循环结束*

#### NO.43 字符串相乘 med

#### NO.104 二叉树的最大深度 easy

**二叉树的深度**是层次最深的叶子节点距离根节点的最短距离。

这是一个可以利用算法课中的递归思维解题。

就是**根节点可以分别从左右子树中获取信息，来计算所需要的结果**。

这道题，对于根节点，其深度就是**左树最大深度和右树最大深度中的最大值加1**。

则，根节点找左右子树要的信息就是最大深度。

**base case**: 当前节点为空，则返回0，因为空节点的深度为0。

#### NO.111 二叉树的最小深度 easy

与上一道题有些类似，这里是求最小深度。

根节点的深度等于**左树最小深度和右数最小深度的最小值加1**。本题中的当前节点会出现几种情况：

- 当左右孩子有一个为空时，最小深度不应该是0加1，还是不为空的那个孩子的深度加1
- 当左右孩子都在，返回最小的那个加1
- 当左右孩子都没有，返回1

**base case**：当一个节点为空时，返回0

#### 剑指Offer 17 打印1到最大的n位数 easy

#### NO.202 快乐数 easy

## 2020.8.9

#### NO.8 字符串转换整数 med

#### 剑指Offer 38 字符串的排列 med

采用**回溯法**解决该问题。

这是经典的排列问题，求字符串所有可能不重复的排列。

对于每一位字符位，每次不重复地选字符集合里的其中一个，下一位字符则跟字符串剩余部分的每个字符进行交换，交换一次，继续递归下一位，递归到最后得到最终结果，加入res列表。

为了保证每一位选的字符不重复，我们采用了集合visit来确定哪些元素也被选中过不能再选，以免重复，也就是剪枝操作。

~~~python
string = 'abc'
def permuation(string):#主函数
    result = []
    if len(string) == 0:
        return result
    process(0, string, result)
    return result

def process(i, string, result):#递归函数
    '''
    string是当前排列，与原字符串不一样，当得到当前的排列结果，并且将排列结果存到结果列表result中后，string就恢复原来的样子
    '''
    if i == len(string):# base case:当遍历完整个字符串，则应该结算排列结果
        result.append(string)
        return
    visit = set()
    for j in range(len(string)):#此时string[:i]已经选定，对于字符串的第i个位置，其取值可以是string[i:]的每个字符，所以每次循环就将后面字符串切片中的每个不重复字符与第i个位置的字符进行交换。每个字符交换过后，就加入visit集合，防止有重复字符放在第i个位置上，导致结果重复。
        if strqing[j] not in visit:
            visit.add(string[j])
            string[i], string[j] = string[j], string[i]#交换后继续计算下一个字符
            process(i + 1, string, result)
            string[i], string[j] = string[j], string[i]#计算完后，恢复字符串，以进行下一个循环
~~~



#### NO.78 子集 med 

采用**回溯法**解决该问题。

这是经典的组合问题，这个相比于排列要更为简单一些。

遍历字符串，到达某个字符时，选择是否将该字符加入当前组合，加入是一个选择，不加入是另一个选择，递归遍历所有字符，当递归到最后一个字符之后，将当前组合结果加入res列表。

换句话说，每到一个字符，都有两条路可以选择，最后相当于把所有路径都给保存起来了。

~~~python
def subsets(string):#主函数
    result = []
    if len(string):
        return result
    subset = ''
    process(0, string, subset, result)
    return result

def process(i, string, subset, result):
    if i == len(string):
        result.append(subset)
        return
    process(i + 1, subset + string[i], result)
    process(i + 1, subset, result)
    
~~~



#### NO.47 全排列II med

## 2020.8.10

#### NO.50 Pow(x, n)

采用**二分法**来求解。

x的n次幂，是对x进行平方，再对其结果进行平方，周而复始，直到求到n次方。这样计算量就少了许多，不需要每一次只乘一次x，原来是O(N)，现在是O(logn)。

**算法**：

递归函数**mul**(x, N)

**base case：**当N = 0，则返回1，因为任何数的0次幂都是1。

当N为偶数时，x的N次幂等于x的N/2次幂 * x的N/2次幂；

当N为奇数时，x的N次幂等于x的N//2次幂 * x的N//2次幂 * x

~~~python
def mul(x, N):
    if N == 0:
        return 1
    y = mul(x, N//2)
    if N % 2 == 0:
        return y * y
    else:
        return y * y * x
~~~

主函数**pow**(x, n)：

当N为正数，正常返回，当N为负数，返回其正数次幂的倒数

~~~python
def pow(x,n):
	return mul(x,n) if N>=0 else 1/(mul(x, -n))
~~~

#### 面试题 16.07 最大数值 easy

找出两个数字的最大值，不能使用条件语句，也不能使用比较符号。

这里运用了一个数学公式：

$max(a,b) = (|a -b|+a+b)/2$







