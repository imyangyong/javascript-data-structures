<h1 align="center" style="margin: 30px 0 35px;">JavaScript Data Structures</h1>
<p align="center">
  <a href="https://travis-ci.com/AngusYang9/javascript-data-structures"><img src="https://travis-ci.com/AngusYang9/javascript-data-structures.svg?branch=master" /></a>
</p>

[在线地址](https://www.imyangyong.com/javascript-data-structures)

现在，让我们开始学习所有的数据结构。

很令人兴奋，对吧？ 🏖

它虽不是最有意思的话题，但是很重要。它会极大助力我们程序员的成长！

数据结构可以帮助你什么？

- 管理复杂性，使你的程序更容易理解。
- 构建高性能、内存高效的程序。

合理地使用数据结构可以极大简化复杂的逻辑；它也可以对性能及内存在效率上有极大提升。

为了了解数据结构，我们将一起实现它们。不用担心，我们会保持代码简洁。实际上，注释比代码多得多。😆

```javascript
============================================================================

,.-'`'-.,.-'`'-.,.-'`'-.,.-'`'-.,.-'`'-.,.-'`'-.,.-'`'-.,.-'`'-.,.-'`'-.,.-'

============================================================================
```

**什么是数据结构？**

本质上，它们是不同的存储和组织数据的方法，满足不同的需求。

数据总是可以用许多不同的方式来表示。然而，取决于数据是什么以及你需要如何处理它，来用一种表现形式更优于其他形式。

为了便于理解，我们先来谈谈算法。

```javascript
/*** ===================================================================== ***\
 ** - ALGORITHMS ---------------------------------------------------------- **
 * ========================================================================= *
 *                                                                           *
 *                        ,--,--.    ,--,--.                                 *
 *   ,----------.        |   |   |  |   |   |            _____               *
 *  |`----------'|       |   |   |  |   |   |           |     |    ,------.  *
 *  |            |       |   |   |  |   |   |      ,--. | o o |   |`------'| *
 *  |            |      ,| +-|-+ |  | +-|-+ |`     |  | |_____|   |        | *
 *  |            | ,:==| | |###|======|###| | |====#==#====#=,,   |        | *
 *  |            | ||   `| +---+ |  | +---+ |'  ,,=#==#====O=``  ,|        | *
 *  |            | ||    |   |   |  |   |   |   ``=#==#====#=====||        | *
 *   `----------'  ||    |   |   |  |   |   |      |__|          `|        | *
 *    | | ``=| |===``    `--,',--`  `--,',--`      /||\            `------'  *
 **   \_/    \_/         / /   \ \  / /   \ \     //||\\           |_|  |_| **
\*** ===================================================================== ***/
```

> [Javascript 算法介绍与实现](https://www.imyangyong.com/javascript-algorithms/) 👈

**算法**是一个用于逐步执行操作集合的花哨名称。

数据结构是用算法实现的，且算法也是用数据结构实现的。这就是数据结构和算法，一直可延伸到计算机工作的微观底层。

任何任务都可以以多种方式实现。对于常见的任务，人们通常会想出很多不同的算法。

例如，对一组无序项进行排序的算法非常多：

- 插入排序，选择排序，归并排序，冒泡排序，堆排序，快速排序... ...

其中一些算法比其他的要快得多。有些使用的内存更少，有些很容易实现，有些是基于对数据集的假设。

它们中的每个算法都会因为“某些东西”而变得更好。所以你需要根据自己的需求做出决定，为此，你需要一种比较它们的方法，一种衡量它们的方法。

当我们比较算法的性能时，我们使用一种叫做“Big-O”的东西来粗略衡量它们的平均和最差性能。

```javascript
/*** ===================================================================== ***\
 ** - BIG-O NOTATION ------------------------------------------------------ **
 * ========================================================================= *
 *           a           b                                 d                 *
 *           a         b    O(N^2)                      d                    *
 *     O(N!) a        b                O(N log N)    d                    c  *
 *           a      b                            d                 c         *
 *          a      b                          d             c        O(N)    *
 *          a    b                         d         c                       *
 *          a  b                       d      c                              *
 *         a  b                     d  c                                     *
 *         ab                   c                          O(1)              *
 *  e    e    e    e    ec   d    e    e    e    e    e     e    e    e      *
 *      ba        c      d                                                   *
 *    ba   c        d                       f    f    f    f    f    f    f  *
 ** cadf    f d    f    f    f    f    f       O(log N)                     **
\*** ===================================================================== ***/
```

**Big-O** 符号是粗略衡量算法性能的一种方法，为了在讨论它们的时候比较它们。

你可以用 Big-O 来衡量两个主要的东西：

- **时间复杂度**：指一个算法的总操作数。
- **空间复杂度**：指一个算法运行时所占的总内存。

我们单独测量这两种复杂度，因为一个算法可能比另一个执行更少的操作，也可能占用更多的操作内存。根据你的需求，其中一个可能是比另一个更好的选择。

以下是常见的 Big-O：

| Name     | Notation   | How you feel when they show up at your party |
| -------- | ---------- | -------------------------------------------- |
| 常数     | O(1)       | AWESOME!!                                    |
| 对数     | O(log N)   | GREAT!                                       |
| 线性     | O(N)       | OKAY.                                        |
| 线性对数 | O(N log N) | UGH...                                       |
| 多项式   | O(N ^ 2)   | SHITTY                                       |
| 指数     | O(2 ^ N)   | HORRIBLE                                     |
| 阶乘     | O(N!)      | WTF                                          |

让你对我们讨论的运算有个概念。让我们看一下，给定(N)项，这些会等于什么。

|            | N = 5     | 10        | 20             | 30                                          |
| ---------- | --------- | --------- | -------------- | ------------------------------------------- |
| O(1)       | 1         | 1         | 1              | 1                                           |
| O(log N)   | 2.3219... | 3.3219... | 4.3219...      | 4.9068...                                   |
| O(N)       | 5         | 10        | 20             | 30                                          |
| O(N log N) | 11.609... | 33.219... | 84.638...      | 147.204...                                  |
| O(N ^ 2)   | 25        | 100       | 400            | 900                                         |
| O(2 ^ N)   | 32        | 1024      | 1,048,576      | 1,073,741,824                               |
| O(N!)      | 120       | 3,628,800 | 2,432,902,0... | 265,252,859,812,191,058,636,308,480,000,000 |

如你所见，即使是相对较小的数据集，你也会做大量的额外工作。

使用数据结构，你可以执行 4 种主要的操作类型：访问、查询、插入和删除。

需要注意的是，数据结构可能擅长某项操作，但不擅长另一项操作：

|                                | Accessing | Searching | Inserting | Deleting |
| ------------------------------ | --------- | --------- | --------- | -------- |
| 数组(Array)                    | O(1)      | O(N)      | O(N)      | O(N)     |
| 链表(Linked List)              | O(N)      | O(N)      | O(1)      | O(1)     |
| 二叉查找树(Binary Search Tree) | O(log N)  | O(log N)  | O(log N)  | O(log N) |

这可以理解为... ...

|                                | Accessing | Searching | Inserting | Deleting  |
| ------------------------------ | --------- | --------- | --------- | --------- |
| 数组(Array)                    | AWESOME!! | OKAY      | OKAY      | OKAY      |
| 链表(Linked List)              | OKAY      | OKAY      | AWESOME!! | AWESOME!! |
| 二叉查找树(Binary Search Tree) | GREAT!    | GREAT!    | GREAT!    | GREAT!    |

没有完美的数据结构，你要根据你要处理的数据和你要用它做的事情来选择一个。这就是为什么了解许多不同的常见数据结构非常重要，这样你就可以从中选择。