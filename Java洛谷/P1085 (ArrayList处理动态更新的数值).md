## 1.
```java
import java.util.ArrayList;
import java.util.Scanner;

public class P1085 {
    public static void main(String[] args) {
        ArrayList<Integer> whetherHappy = new ArrayList<>();            // 用ArrayList来动态增加新数值
        Scanner sc = new Scanner(System.in);

        for (int i = 0 ; i < 7 ; i++){                                  // for循环处理多个输入
            String dayInput = sc.nextLine();
            CheckWhetherHappy(whetherHappy,dayInput);
        }

        int result = -1;
        boolean whetherZeroArr = CheckZero(whetherHappy);               // 判断一周是否有不开心情况

        if (whetherZeroArr) {
            result = 0;
            System.out.println(result);
        }else {
            result = CheckDay(whetherHappy);
            System.out.println(result);
        }

        sc.close();
    }

    public static void CheckWhetherHappy (ArrayList<Integer> arr,String everyDay) {     // 判断时长是否大于8
        String[] arrStr = everyDay.split(" ");
        int class1 = Integer.parseInt(arrStr[0]);
        int class2 = Integer.parseInt(arrStr[1]);
        int totalTime = class1 + class2;

        if (totalTime > 8) {                                              // 大于8，将超时部分添加到数组中
            arr.add(totalTime - 8);
        }else {                                                           // 否则添加0
            arr.add(0);
        }
    }

    public static boolean CheckZero (ArrayList<Integer> arr) {            // 判断一周是否有不开心
        for (int num : arr) {
            if (num != 0) {
                return false;
            }
        }
        return true;
    }

    public static int CheckDay (ArrayList<Integer> arr) {                 // 找出一周中最不开心的一天
        int indexValue = 0;
        int maxValue = 0;

        for (int i = 0 ; i < arr.size() ; i++) {
            if (arr.get(i) > maxValue) {
                indexValue = i + 1;
                maxValue = arr.get(i);
            }
        }

        return indexValue;
    }
}
```

## 2.
```java
import java.util.Scanner;

public class P1085 {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int max = 8;
        int unhappyDay = 0;
        for (int i = 0; i < 7 ; i++){
            int num1 = sc.nextInt();
            int num2 = sc.nextInt();
            int totalTime = num1 + num2;

            if (totalTime > max) {
                max = totalTime;
                unhappyDay = i + 1 ;
            }
        }
        
        System.out.println(unhappyDay);
        
        sc.close();
    }
}
```

# P1085 [NOIP 2004 普及组] 不高兴的津津

## 题目描述

津津上初中了。妈妈认为津津应该更加用功学习，所以津津除了上学之外，还要参加妈妈为她报名的各科复习班。另外每周妈妈还会送她去学习朗诵、舞蹈和钢琴。但是津津如果一天上课超过八个小时就会不高兴，而且上得越久就会越不高兴。假设津津不会因为其它事不高兴，并且她的不高兴不会持续到第二天。请你帮忙检查一下津津下周的日程安排，看看下周她会不会不高兴；如果会的话，哪天最不高兴。

## 输入格式

输入包括 $7$ 行数据，分别表示周一到周日的日程安排。每行包括两个小于 $10$ 的非负整数，用空格隔开，分别表示津津在学校上课的时间和妈妈安排她上课的时间。

## 输出格式

一个数字。如果不会不高兴则输出 $0$，如果会则输出最不高兴的是周几（用 $1, 2, 3, 4, 5, 6, 7$ 分别表示周一，周二，周三，周四，周五，周六，周日）。如果有两天或两天以上不高兴的程度相当，则输出时间最靠前的一天。

## 输入输出样例 #1

### 输入 #1

```
5 3
6 2
7 2
5 3
5 4
0 4
0 6
```

### 输出 #1

```
3
```

## 说明/提示

NOIP2004 普及组第 1 题

- 2021-10-27：增加一组 hack 数据
- 2022-06-05：又增加一组 hack 数据