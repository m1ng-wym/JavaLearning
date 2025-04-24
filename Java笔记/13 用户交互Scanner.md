# 用户交互Scanner
## Scanner对象
java.util.Scanner是java5的新特征，**我们可以通过Scanner类来获取用户的输入**。

基本语法：
```java
Scanner s = new Scanner(System.in);
```

***在读取前可以使用hasNext()与hasNextLine()判断是否还有输入的数据。***

使用完Scanner类后，要***调用.close()方法关闭***，否则会一直占用资源。

### next()方法
- 一定要读取到有效字符后才可以结束输入。                         
> 若用户不输入，程序就会一直等待。

- 对输入有效字符之前遇到的空白，next()方法会自动将其去掉。
> 输入     hello，输出结果为hello。

- 只有输入有效字符后才将其后面输入的空白作为分隔符或者结束符。
> 输入hello world，输出结果为hello。

- ***next()不能得到带有空格的字符串。***

### nextLine()方法
- 以Enter为结束符，也就是说***nextLine()方法返回的是输入回车之前的所有字符***。
- 可以获得空白。