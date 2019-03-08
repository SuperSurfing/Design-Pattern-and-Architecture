

#### 导读

&emsp;&emsp;像大多数的数学表达式一样，正则表达式也是一个中很“**反人性**”的表达式，相信很多人看正则表达式跟看天书一样，即使学习和使用过正则表达式，也很快就忘了它的规则。而本文的目的就是让普通人能够轻松快速地了解正则表达式，并把握正则表达式的设计哲学，不会那么容易就忘记。

&emsp;&emsp;注意，为简单起见，本文并不会介绍“正则表达式”的全部规则，而只是介绍一些常用规则，以应付日常的搜索和编程需要。如果想要更进一步学习正则表达式，可以先继续阅读 [正则表达式30分钟入门](https://deerchao.net/tutorials/regex/regex.htm)，本文也参考了该博文。如果你需要设计一些复杂的正则表达式，除了 google ，你还可以使用 [正则表达式手册](http://tool.oschina.net/uploads/apidocs/jquery/regexp.html) 。如果你想检验自己设计的正则表达式是否正确，你可以使用 [正则表达式-在线工具](https://c.runoob.com/front-end/854)，这个工具还提供生成代码的功能，非常实用。如果你使用 Python，你还可以参考 [Python 正则表达式指南](https://www.cnblogs.com/huxi/archive/2010/07/04/1771073.html) 和 [菜鸟教程：Python 正则表达式](http://www.runoob.com/python/python-reg-expressions.html)。学习完本文，并配合这些网络资源，足以让你对付日常对正则表达式的需求。

<font size=4 face="微软雅黑" color=""></font>
<font size=4 face="微软雅黑" color=""></font>


#### 正则表达式的设计哲学

&emsp;&emsp;普通人对正则表达式“无法理解”和“不能记住”的原因是：正则表达式与自然语言的设计哲学完全不同，它很“**反人性**”。但是，如果你了解了正则表达式的设计哲学，那么你将能很好沿着这个脉络牢牢地掌握正则表达式，而不会觉得“难以理解”和“轻易忘记”。因此，我将它放在最开始进行介绍。

#### 设计哲学一：
>以字符（char）为单位进行匹配，引入通配符

&emsp;&emsp;自然语言是以单词（word）为单位，而正则表达式是以字符（char）为单位。我们需要牢记，正则表达式是对单个字符（char）的匹配，比如，通配符，它只能匹配一个字符。我们熟知的在 Linux 或 Windows 命令行中的通配符——星号“※”或者问号“?”，它实际上是正则表达式中的通配符+限定符的简写，它把真正的通配符点号“dot”省略了。

&emsp;&emsp;而字符串（string or char array）匹配、分支匹配和分组匹配都是在字符匹配的基础上进行延伸。
#### 设计哲学二：
>多种组合方式：字符连续排列、字符（串）重复、逻辑或

&emsp;&emsp;真正让正则表达式产生威力的是它对单个字符的组合方式，如下：

 - 字符连续排列 - 仿照自然语言，由字母到单词
 - 字符（串）重复 - 引入“**限定符**”，表明重复的次数
 - 逻辑或 - 引入字符集[a-z0-9]和分支语句，表达逻辑或
 
&emsp;&emsp;当然，这些组合方式除了应用在单个字符上，也可以扩展到字符串和分组上面，从而能够匹配各种复杂的东西。
#### 设计哲学三：
>反义匹配：一般小写表示正向匹配，大写表示反义匹配

&emsp;&emsp;对于大多数通配符，正则表达式式还提供反义匹配符，类似于“**逻辑非**”的功能。比如：
|通配符|作用  |反义符|
|--|--|--|
| \b | 匹配一个单词边界（boundary），也就是指单词和空格间的位置。例如，“er\b”可以匹配“never”中的“er”，但不能匹配“verb”中的“er”  | \B |
| \d | 匹配一个数字字符。等价于[0-9]  | \D |
| \s | 匹配任何空白字符，包括空格、制表符、换页符等等。等价于[ \f\n\r\t\v]。 | \S |
| \w | 匹配包括下划线在内的任何单词字符。等价于“[A-Za-z0-9_]” | \W |

#### 设计哲学四：
>贪婪匹配与懒惰匹配，默认使用贪婪匹配，加问号开启懒惰匹配

&emsp;&emsp;正则表达式默认使用贪婪匹配，也就是说匹配尽可能多的的一串字符；如果要限定更小的范围，可以通过添加限定符“?”，关闭贪婪匹配。

<font size=4 face="微软雅黑" color=""></font>
<font size=4 face="微软雅黑" color=""></font>

## 正则表达式规则树

&emsp;&emsp;熟悉了正则表达式的设计哲学后，我们再来从总体上看看正则表达式的规则，将它以语法树的形式展现出来：

![正则表达式规则树](https://github.com/SuperSurfing/Design-Pattern-and-Architecture/blob/master/Regular%20Expression%20for%20Python/Images/R.E..png?raw=true)

<font size=4 face="微软雅黑" color=""></font>
<font size=4 face="微软雅黑" color=""></font>

## 正则表达式速查

&emsp;&emsp;阅读完上面的内容，已经对正则表达式有了大概的认识，再配合正则表达式的速查资料，你就可以轻松掌握常用的正则表达式了。

 - [正则表达式手册](http://tool.oschina.net/uploads/apidocs/jquery/regexp.html)
 - [正则表达式在线工具](https://c.runoob.com/front-end/854)
 - [正则表达式教程](https://deerchao.net/tutorials/regex/regex.htm)
 - [Python RE](https://www.cnblogs.com/huxi/archive/2010/07/04/1771073.html)
