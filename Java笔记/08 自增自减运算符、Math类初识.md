# 自增自减运算符
> ++ 自增  -- 自减  (一元运算符)

```java
public class Demo {
    public static void main(String[] args) {
        int a = 3;

        int b = a++; // 先给b赋值，再自增。 a++ -> a = a + 1

        System.out.println(a);   // 4

        int c = ++a; // 先自增，再给c赋值。 ++a -> a = a + 1

        System.out.println(a);   // 5
        System.out.println(b);   // 3
        System.out.println(c);   // 5
    }
}
```

# Math类
> 包含用于执行基本数学运算的方法，如初等指数、对数、平方根和三角函数。

```java
public class Demo {
    public static void main(String[] args) {
        double a = Math.abs(-5);    // 绝对值
        double b = Math.pow(2, 3);  // 2的3次方
        double c = Math.sqrt(16);   // 平方根 
    }  
}
```