---
title: 冒泡排序
date: 2018-12-08 11:41:23
tags:
typora-root-url: ..
---

**原理**：每次比较两个相邻的元素，如果第一个比第二个大，就交换他们两个。

**思路**：它重复地走访过要排序的元素列，依次比较两个相邻的[元素](https://baike.baidu.com/item/元素/9563223)，如果顺序（如从大到小、首字母从Z到A）错误就把他们两两交换过来。走访元素的工作是重复地进行直到没有相邻元素需要交换，也就是说该元素列已经排序完成。

**由来**：因为越小的元素会经由交换慢慢“浮”到数列的顶端（升序或降序排列），就如同碳酸饮料中[二氧化碳](https://baike.baidu.com/item/二氧化碳/349143)的气泡最终会上浮到顶端一样，故名“冒泡排序”。

**示例**：

1：注意6的两两交换过程。

![bubblesort1](/images/bubbleSort/bubblesort1.png)

<!-- more -->

2：整个完整过程

![bubblesort2](/images/bubbleSort/bubblesort2.png)

3：Java实现

```java
public static void bubbleSort(Integer[] arr) {
        int n = arr.length;
        if (n <= 1) return;       //如果只有一个元素就不用排序了
        for (int i = 0; i < n; ++i) {
            // 提前退出冒泡循环的标志位,即一次比较中没有交换任何元素，这个数组就已经是有序的了
            boolean flag = false;
            for (int j = 0; j < n - i - 1; ++j) {        //此处你可能会疑问的j<n-i-1，因为冒泡是把每轮循环中较大的数飘到后面，
                // 数组下标又是从0开始的，i下标后面已经排序的个数就得多减1，总结就是i增多少，j的循环位置减多少
                if (arr[j] > arr[j + 1]) {        //即这两个相邻的数是逆序的，交换
                    int temp = arr[j];
                    arr[j] = arr[j + 1];
                    arr[j + 1] = temp;
                    flag = true;
                }
            }
            if (!flag) break;//没有数据交换，数组已经有序，退出排序
        }
    }
```

