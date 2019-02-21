# Big-Data-Structure
大话数据结构

# 1. 数据结构绪论

## 数据结构起源
数据结构是一门研究非数值计算的程序设计问题中的操作对象，以及它们之间的关系和操作等相关问题的科学。

## 基本概念和术语
* **数据：** 数据是描述客观事物的符号，是计算机中可以操作的对象，是能被计算机识别，并输入给计算机的符号集合。 
* **数据元素：** 是组成数据的、有一定意义的基本单位，在计算机中通常作为整体处理，也被称为记录。 
* **数据项：** 一个数据元素由若干个数据项组成，数据项是数据不可分割的最小单位。 
* **数据对象：** 是性质相同的数据元素的集合，是数据的子集。 
* **数据结构：** 是相互之间存在一种或多种特定关系的数据元素的集合。 

## 逻辑结构与物理结构
### 逻辑结构
是指数据对象中数据元素之间的相互关系。 

* **集合结构：** 集合结构中的数据元素除了同属于一个集合外，它们之间没有其他关系。 
![aggregate.png](https://github.com/Ewenwan/reading-notes/blob/master/da-hua-shu-ju-jie-gou/01-intro/assets/aggregate.png)
* **线性结构：** 线性结构中的数据元素之间是一对一的关系。  
![aggregate.png](https://github.com/Ewenwan/reading-notes/blob/master/da-hua-shu-ju-jie-gou/01-intro/assets/linear.png)
* **树形结构：** 树形结构中的数据元素之间存在一种一对多的层次关系。  
![aggregate.png](https://github.com/Ewenwan/reading-notes/blob/master/da-hua-shu-ju-jie-gou/01-intro/assets/tree.png)
* **图形结构：** 图形结构的数据元素是多对多的关系。  
![aggregate.png](https://github.com/Ewenwan/reading-notes/blob/master/da-hua-shu-ju-jie-gou/01-intro/assets/graph.png)

### 物理结构
是指数据的逻辑结构在计算机中的存储形式  

* **顺序存储结构：** 是把数据元素存放在地址连续的存储单元里，其数据间的逻辑关系和物理关系是一致
![sequence.png](https://github.com/Ewenwan/reading-notes/blob/master/da-hua-shu-ju-jie-gou/01-intro/assets/sequence.png)
* **链式存储结构：** 是把数据元素存放在任意的存储单元里，这组存储单元可以是连续的，也可以是不连续的。
![sequence.png](https://github.com/Ewenwan/reading-notes/blob/master/da-hua-shu-ju-jie-gou/01-intro/assets/chain.png)

### 抽象数据类型
* **数据类型：** 是指一组性质相同的值得集合及定义在此集合上的一些操作的总称。  
	* **原子类型：** 是不可以再分解的基本类型，包括整型、实型、字符型等。  
	* **结构类型：** 由若干个类型组合而成，可以是再分解的。例如：整形数组是由若干整形数据组成的。 
* **抽象数据类型（Abstract Data Type， ADT）：** 是指一个数学模型及定义在该模型上的一组操作。  

	```
	ADT 抽象数据类型名
	Data
		数据元素之间逻辑关系的定义
	Operation
		操作1
			初始条件
			操作结果描述
		操作2
			……
		操作n
			……
	endADT
	
	```
	
### 总结回顾
* 数据结构概念  
![](https://github.com/Ewenwan/reading-notes/blob/master/da-hua-shu-ju-jie-gou/01-intro/assets/data-structure-concept.png)
* 数据结构分类  
![](https://github.com/Ewenwan/reading-notes/blob/master/da-hua-shu-ju-jie-gou/01-intro/assets/data-structure-classify.png)

# 2.算法

## 算法定义
算法是解决特定问题求解步骤的描述，在计算机中表现为指令的有限序列，并且每条指令表示一个或多个操作。

## 算法的特性
* **输入输出：** 算法具有零个或多个输入
* **有穷性：** 指算法在执行有限的步骤之后，自动结束而不会出现无限循环，并且每一个步骤在可接受的时间内完成。
* **确定性：** 算法的每一个步骤都具有确定的含义，不会出现二义性。
* **可行性：** 算法的每一步都必须是可行的，也就是说每一步都能够通过执行有限的次数完成。

## 算法设计的要求
* **正确性：** 算法的正确性是指算法至少应该具有输入、输出和加工处理无歧义性、能正确反映问题的需求、能够得到问题的正确答案。
	1. 	算法程序没有语法错误
	2. 算法程序对于合法的输入能够产生满足要求的输出结果
	3. 算法程序对于非法的输入数据能够得出满足规格说明的结果。
	4. 算法程序对于精心选择的，甚至刁难的测试数据都有满足要求的输出结果。
* **可读性：** 算法设计的另一目的是为了便于阅读、理解和交流。
* **健壮性：** 当输入数据不合法时，算法也能做出相关处理，而不是产生异常或莫名其妙的结果。  
* **时间效率高和存储量低：** 设计算法应该尽量满足时间效率高和存储量低的需求。  

## 算法效率的度量方法
* **事后统计方法：** 这种方法主要是通过设计好的测试程序和数据，利用计算机计时器对不同算法编制的程序运行时间进行比较，从而确定算法效率的高低。
* **事前分析估算方法：** 在计算机程序编制前，依据统计方法对算法进行估算。

## 函数的渐进增长
给定两个函数 f(n) 和 g(n), 如果存在一个整数 N，使得对于所有的 n > N, f(n) 总是比 g(n) 大，那么我们说f(n)的增长渐进快于 g(n)。

## 算法的时间复杂度
### 算法时间复杂度的定义
在进行算法分析时，语句总的执行次数 T(n) 是关于问题规模 n 的函数，进而分析 T(n) 随 n 的变化情况并确定 T(n)的数量级。算法的时间复杂度，也就是算法的时间量度，记作：T(n)=O(f(n))。它表示随问题规模的增大，算法执行时间的增长率和 f(n) 的增长率相同，乘坐算法的渐进时间复杂度，简称为时间复杂度。其中 f(n) 是问题规模 n 的某个函数。

### 推导大O阶方法
1. 用常数 1 取代运行时间中的所有加法常数。
2. 在修改后的运行次数函数中，只保留最高阶项。
3. 如果最高阶项存在且不是 1，则去除与这个项相乘的常数。得到的结果就是大 O 阶

### 常数阶
```c
int sum =0, n=100;
sum = (1+n)*n/2;
printf("%d", sum);
```
1. 算法运行次数函数为 f(n) = 3;
2. 用常数 1 取代运行时间中的所有加法常数，得到 f(n) = 1。
3. 由于没有最高阶项，所以此算法的时间复杂度为 O(1)。

### 线性阶
```c
int i;
for(i=0; i<n; i++) {
	/* 时间复杂度为 O(1) 的程序步骤序列 */
}
```
1. 算法运行次数的函数为 f(n) = n;
2. 没有加法常数取代, f(n) = n;
3. 只保留最高阶项，f(n) = n;
4. 最高阶项存在但是1，所以该算法时间复杂度为 O(n)

### 对数阶
```c
int count = 1;
while(count < n) {
	count = count * 2;
	/* 时间复杂度为 O(1) 的程序步骤序列 */
}
```
1. 有多少个 2 相乘后大于 n，则会退出循环，由 2^x = n, 得到算法运行次数函数 f(n) = log<sub>2</sub>n。
2. 没有加法常数取代, f(n) = log<sub>2</sub>n。
3. 至保留最高阶项，f(n) = log<sub>2</sub>n。
4. 最高阶项存在且不是1，去除与这个项相乘的系数，所以该算法时间复杂度为 O(logn)


### 平方阶
```c
int i, j;
for(i=0; i<n; i++) {
	for(j=0; j<n; j++) {
		/* 时间复杂度为 O(1) 的程序步骤序列 */
	}
}
```
1. 算法运行次数函数 f(n) = n^2。
2. 没有常数，f(n) = n^2。
3. 只保留最高阶项，f(n) = n^2。
4. 最高阶项存在但系数为1，所以该算法时间复杂度为 O(n^2)

### 常见的时间复杂度
| 执行次数函数 | 阶 | 非正式术语 |
|:--:|:--:|:--:|
| 12 | O(1) | 常数阶 |
| 2n+3 | O(n) | 线性阶 |
| 3n^2 + 2n +1| O(n^2) | 平方阶 |
| 5log<sub>2</sub>n + 20| O(logn) | 对数阶| 
| 2n + 3nlog<sub>2</sub>n + 19 | O(nlogn) | nlogn 阶| 
| 6n^3 + 2n^2 + 3n + 4 | O(n^3) | 立方阶 |
| 2^n | O(2^n) | 指数阶 |

常用时间复杂度所耗费的时间从小到大依次是：   
**O(1) < O(logn) < O(n) < O(nlogn) < O(n^2) < O(n^3) < O(n!) < O(n^n)**

### 最坏情况与平均情况
最坏情况运行时间是一种保证，那就是运行时间不会再坏了。在应用中，这是一种最重要的需求，通常，除非特别指定，我们提到的运行时间都是最坏情况的运行时间。

平均运行时间是所有情况中最有意义的，因为它是期望的运行时间。

一般没有特殊说明的情况下，时间复杂度都是指最坏时间复杂度。  

### 算法空间复杂度
算法的空间复杂度通过计算算法所需的存储空间时间，算法空间复杂度的计算公式记作：**S(n)=O(f(n))**, 其中 n 为问题的规模，f(n) 为语句关于 n 所占存储空间的函数。

通常我们都使用 “时间复杂度” 来指运行时间的需求， “空间复杂度” 来指空间徐秀。当不用限定词的使用 “复杂度” 时，通常是指时间复杂度。

### 总结回顾
**算法的定义：** 算法是解决特定问题求解步骤的描述，在计算机中卫指令的有限序列，并且每条指令表示一个或多个操作。  
**算法的特性：** 有穷性、确定性、可行性、输入、输出。  
**算法的设计的要求：** 正确性、可读性、健壮性、高效率和低存储量需求。  
**算法的度量方法：** 事后统计方法(不科学、不准确)，事前分析估算方法。  
**函数的渐进增长：** 给定两个函数 f(n) 和 g(n)，如果存在一个整数 N, 使得对于所有的 n > N, f(n) 总是比 g(n) 大，那么我们说 f(n) 的增长渐进快于 g(n)。  
**推导大 O 阶：**  
  
* 	用常数 1 取代运行时间中的所有加法常数  
*  在修改后的运行次数函数中，只保留最高阶项  
*  如果最高阶项存在且不是1，则去除与这个项相乘的常数。 
 
得到的结果就是大 O 阶  

**常见时间复杂度所耗时间的大小排列：** O(1) < O(logn) < O(n) < O(nlogn) < O(n^2) < O(n^3) < O(n!) < O(n^n)


# 3.线性表

## 线性表的定义
**线性表：零个或多个数据元素的有限序列**  

若使用数学语言定义：  
**若将线性表记为（a<sub>1</sub>, ..., a<sub>i-1</sub>, a<sub>i</sub>, a<sub>i+1</sub>, ..., a<sub>n</sub>）则表中a<sub>i-1</sub>领先于a<sub>i</sub>, a<sub>i</sub> 领先于a<sub>i+1</sub>，称a<sub>i-1</sub>是a<sub>i</sub>的直接前驱元素，a<sub>i+1</sub>是a<sub>i</sub>的直接后继元素。当 i=1, 2, ..., n-1 时，a<sub>i</sub>有且仅有一个直接后继，当 i=2, 3, ..., n时，a<sub>i</sub>有且仅有一个直接前驱**  
所以  
**线性表元素的个数 n (n≥0)定义为线性表的长度，当n=0时，称为空表**

## 线性表的抽象数据类型

```
 ADT 线性表(List)
 Data
     线性表的数据对象集合为{a1,a2,...,an}, 每个元素的类型均为 DataType。
     其中除第一个元素a1外，每一个元素有且仅有一个直接前驱元素，
     除了最后一个元素an外，每一个元素有且仅有一个直接后继元素。
     数据元素之间的关系是一对一的关系
 Operation
     InitList(*L):          初始化操作，建立一个空的线性表 L。
     ListIsEmpty(L):        若线性表为空，返回 true, 否则返回false。
     ClearList(*L);         将线性表置空
     GetElem(L,i,*e):       将线性表 L 的第 i 个元素返回给 e。
     LocateElem(L, e):      在线性表 L 中查找与给定值 e 相等的元素，若查找成功，返回该元素在表中序号表示成功，否则返回0表示失败
     ListInsert(*L,i,e):    在线性表 L 中第 i 个位置插入新元素 e。
     ListDelete(*L,i,*e):   删除线性表中第 i 个位置的元素，并用 e 返回其值。
     ListLength(L):         返回线性表 L 的元素个数
 endADT
```

## 线性表的顺序存储结构
**顺序存储定义：** 线性表的存储结构，指的是用一段地址连续的存储单元依次存储线性表的数据元素  
**顺序存储方式：** 可以用一维数组来实现顺序存储结构  

```c
#define MAXSIZE 20              // 存储空间初始分配量
typedef int ElemType;           // ElemType类型根据实际情况而定, 这里假设为 int
typedef struct {
    ElemType data[MAXSIZE];     // 数组存储元素, 最大值为 MAXSIZE
    int length;                 // 线性表当前元素
} SqList;
```
**数组长度与线性表长度的区别：** 数组长度是存放线性表的存储空间长度，线性表长度是线性表中元素的个数。  
**地址：** 存储器中的每个存储单元都有自己编号，这个编号称为地址。  

## 顺序存储结构的插入与删除
### 获得元素的操作  
```c
// 相关操作状态定义
#define OK 1
#define ERROR 0
#define TRUE 1
#define FALSE 0
typedef int  Status;            // Status 是函数的类型,其值是函数结果状态码,如 OK 等

/**
 获取线性表中第 i 个元素
 
 @param L 线性表 L, 必须已存在
 @param i 要获取的编号, 需满足 i ≤ i ≤ ListLength(L)
 @param e 对应元素返回
 @return 操作结果 OK/ERROR
 */
Status GetSqListElem(SqList L, int i, ElemType *e) {
    if (L.length==0 || i<1 || i>L.length) return ERROR;
    *e = L.data[i-1];
    return OK;
}

```

### 插入操作
```c
/**
 向线性表的第 i 个位置插入元素
 
 @param L 线性表, 必须存在
 @param i 位置编号, 需满足 i ≤ i ≤ ListLength(L)
 @param e 要插入的元素
 @return 操作结果 OK/ERROR
 */
Status SqListInsert(SqList *L, int i, ElemType e) {
    
    // 顺序线性表已满
    if (L->length == MAXSIZE) return ERROR;
    // i 不在线性表范围内
    if (i<1 || i>L->length+1) return ERROR;
    // 插入数据位置不在表尾部
    if (i<=L->length) {
        // 将要插入位置后的元素统一后移一位
        for (int k=L->length-1; k>=i-1; k--) {
            L->data[k+1] = L->data[k];
        }
    }
    L->data[i-1] = e;
    L->length ++;

    return OK;
}
```

### 删除操作

```c
/**
 删除线性表第 i 个位置的元素
 
 @param L 线性表, 必须存在
 @param i 要删除的位置编号, 需满足 i ≤ i ≤ ListLength(L)
 @param e 被删除的元素返回
 @return 操作结果 OK/ERROR
 */
Status SqListDelete(SqList *L, int i, ElemType *e) {
    
    // 空表
    if (L->length==0) return ERROR;
    // 要删除的位置不正确
    if (i<1 || i>L->length) return ERROR;
    *e = L->data[i-1];
    // 若删除的不是表尾, 将删除位置后继元素前移
    if (i<L->length) {
        for (int k=i; k<L->length; k++) {
            L->data[k-1] = L->data[k];
        }
    }
    L->length --;
    
    return OK;
}
```
## 线性表的链式存储结构

### 线性表链式存储结构的定义
为了表示每个数据元素 a<sub>i</sub> 与其直接后继元素 a<sub>i+1</sub> 之间的逻辑关系，对数据元素 a<sub>i</sub> 来说，出了存储其本身的信息之外，还需存储一个指示其直接后继的信息（即直接后继的存储位置）。把存储数据元素信息的域称为数据域，把存储直接后继位置的域称为指针域。指针域中存储的信息乘坐指针或链。这两部分信息组成数据元素 a<sub>i</sub> 的存储映像，称为结点（Node）。  

n 个节点（a<sub>i</sub>的存储映像）链接成一个链表，即为线性表 (a<sub>1</sub>, a<sub>2</sub>, ..., a<sub>n</sub>) 的连式存储结构，因为此链表的每个节点中只包含一个指针域，所以叫做**单链表**。

链表中第一个节点的存储位置叫做**头指针**

有时，为了更加方便的对链表进行操作，会在单链表的第一个结点前附设一个结点，称为**头结点**

### 头指针和头结点的异同

![head_pointer_vs_head_node.png](https://github.com/Ewenwan/reading-notes/tree/master/da-hua-shu-ju-jie-gou/03-list/assets/head_pointer_vs_head_node.png)

### 线性表链式存储结构代码描述

```c
/**
 线性表的单链表的存储结构
 
 结点由存放数据元素的数据域和存放后继结点地址的指针域组成
 */
typedef struct Node {
    ElemType data;
    struct Node *next;
} Node;

// 定义 LinkList
typedef struct Node *LinkList;
```

## 单链表的读取
```c
/**
 获取单链表第i 个位置的元素
 
 @param L 单链表, 必须存在
 @param i 要获取元素的位置标号 1 ≤ i ≤ ListLength(L)
 @param e 返回元素
 @return 操作是否成功 OK/ERROR
 */
Status GetLinkListElem(LinkList L, int i, ElemType *e) {
    
    LinkList p = L->next;
    int j = 1;
    
    while (p && j<i) {
        p = p->next;
        ++j;
    }
    if (!p || j > i) {
        return ERROR;
    }
    *e = p->data;
    return OK;
}
```

## 单链表的插入与删除
### 单链表的插入

```c
/**
 向单链表第 i 个位置插入元素
 
 @param L 单链表, 必须存在
 @param i 要插入的位置标号, 1 ≤ i ≤ ListLength(L)
 @param e 要插入的元素
 @return 操作结果 OK/ERROR
 */
Status LinkListInsert(LinkList *L, int i, ElemType e) {
    
    LinkList p = *L;
    int j = 1;
    
    while (p && j<i) {
        p = p->next;
        ++j;
    }
    // 第 i 个元素不存在
    if (!p || j >i) return ERROR;
    
    // 生成一个新节点
    LinkList s = (LinkList)malloc(sizeof(Node));
    
    // 插入元素
    s->data = e;
    s->next = p->next;
    p->next = s;
    return OK;
}
```

### 单链表的删除

```c
/**
 移除单链表的第 i 个位置的元素
 
 @param L 单链表,必须存在
 @param i 要移除元素的位置标号, 1 ≤ i ≤ ListLength(L)
 @param e 要删除的元素返回
 @return 操作结果 OK/ERROR
 */
Status LinkListDelete(LinkList *L, int i, ElemType *e) {
    
    LinkList p = *L;
    int j = 1;
    while (p && j < i) {
        p = p->next;
        ++j;
    }
    // 第 i 个节点不存在
    if (!p->next || j > i) return ERROR;
    
    LinkList q = p->next;
    p->next = q->next;
    *e = q->data;
    free(q);
    
    return OK;
}
```

## 单链表的整表创建
**头插法**

```c
/**
 随机产生 n 个元素的值, 建立带表头节点的单链线性表 L(头插法)
 
 @param L 创建的线性表 L 返回
 @param n 表元素个数
 @return 操作结果 OK/ERROR
 */
Status CreateLinkListHead(LinkList *L, int n) {
    
    srand((unsigned int)time(0));
    *L = (LinkList)malloc(sizeof(Node));
    (*L) -> next = NULL;
    for (int i=0; i<n; i++) {
        LinkList p = (LinkList)malloc(sizeof(Node));
        p->data = rand() % 100 + 1;
        p->next = (*L)->next;
        (*L)->next = p;
    }
    return OK;
}
```

**尾插法**

```c
/**
 随机产生 n 个元素的值, 建立带表头节点的单链线性表 L(尾插法)
 
 @param L 创建的线性表 L 返回
 @param n 表元素个数
 @return 操作结果 OK/ERROR
 */
Status CreateLinkListTail(LinkList *L, int n) {
    
    srand((unsigned int)time(0));
    (*L) = (LinkList)malloc(sizeof(Node));
    LinkList r = *L;
    
    for (int i=0; i<n; i++) {
        LinkList p = (Node *)malloc(sizeof(Node));
        p->data = rand()%100+1;
        r->next = p;
        r = p;
    }
    r->next = NULL;
    return OK;
}

```

## 单链表的整表删除

```c
/**
 清空单链表
 
 @param L 单链表, 必须存在
 @return 操作结果 OK/ERROR
 */
Status ClearLinkList(LinkList *L) {
    
    LinkList p = (*L)->next;
    while (p) {
        LinkList q = p->next;
        
        free(p);
        p=q;
    }
    (*L)->next = NULL;
    return OK;
}
```

## 单链表结构与顺序存储结构优缺点
![](https://github.com/Ewenwan/reading-notes/tree/master/da-hua-shu-ju-jie-gou/03-list/assets/sqlist_vs_linklist.png)

## 静态链表
......用数组描述的链表叫静态链表（游标实现法）

#### 静态链表的定义
```c
#define MAXSIZE_FOR_STATICLINKLIST 1000
typedef struct {
    ElemType data;
    int cur;
} Component, StaticLinkList[MAXSIZE_FOR_STATICLINKLIST];
```

#### 静态链表的初始化
```c
/**
 初始化一个静态链表
 
 @param space 静态链表
 @return 初始化结果
 */
Status InitStaticLinkList(StaticLinkList space) {
    int i;
    for (i=0; i<MAXSIZE_FOR_STATICLINKLIST-1; i++) {
        space[i].cur = i+1;
        space[i].data = 0;
    }
    space[MAXSIZE_FOR_STATICLINKLIST-1].cur=0;
    return OK;
}
```
#### 静态链表模拟动态链表的内存分配和释放
```c
/**
 模拟动态链表存储空间的分配
 
 @param space 静态链表
 @return 若备用空间链表非空, 则返回分配的节点下标, 否则返回0
 */
int Malloc_SLL(StaticLinkList space) {
    // 数组第0位,始终记录静态链表下一个可用位置
    int i = space[0].cur;
    if (space[0].cur) {
        space[0].cur = space[i].cur;
    }
    return i;
}

/**
 模拟动态l链表存储空间的释放
 
 @param space 静态链表
 @param k 要释放的位置
 */
void Free_SLL(StaticLinkList space, int k) {
    space[k].cur = space[0].cur;
    space[0].cur = k;
}

```

#### 静态链表的插入
```c
/**
 静态链表的插入实现
 
 @param space 静态链表
 @param i 要插入的位置
 @param e 要插入的内容
 @return 插入结果
 */
Status StaticLinkListInsert(StaticLinkList space, int i, ElemType e) {
    int j, k, l;
    k = MAXSIZE_FOR_STATICLINKLIST-1;
    if (i<1 || i>StaticLinkListLength(space)+1) return ERROR;
    j = Malloc_SLL(space);
    if (!j) return ERROR;

    space[j].data = e;
    for (l=1; l<i; l++) {
        k = space[k].cur;
    }
    space[j].cur = space[k].cur;
    space[k].cur = j;

    return OK;
}
```

#### 静态链表的删除

```c
/**
 静态链表的删除实现
 
 @param space 静态链表
 @param i 要删除的元素编号
 @return 删除结果
 */
Status StaticLinkListDelete(StaticLinkList space, int i) {
    int j, k;
    
    if (i<1 || i> StaticLinkListLength(space)) return ERROR;
    k = MAXSIZE_FOR_STATICLINKLIST-1;
    for (j=1; j<i; j++) {
        k = space[k].cur;
    }
    
    j = space[k].cur; // space[k] 为要删除元素的前一个
    space[k].cur = space[j].cur;
    Free_SLL(space, j);
    
    return OK;
}
```

#### 静态链表的长度计算
```c
/**
 获取链表长度
 
 @param space 静态链表
 @return 链表长度
 */
int StaticLinkListLength(StaticLinkList space) {
    int j=0;
    int i = space[MAXSIZE_FOR_STATICLINKLIST-1].cur;
    
    while (i) {
        i = space[i].cur;
        j++;
    }
    
    return j;
}
```

### 静态链表的优缺点
![](https://github.com/Ewenwan/reading-notes/tree/master/da-hua-shu-ju-jie-gou/03-list/assets/static_link_list.png)


