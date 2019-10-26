### try..except...详细用法

1、如果一段代码有多种类型的错误，例如:

[![复制代码](https://common.cnblogs.com/images/copycode.gif)](javascript:void(0);)

```
 1 try:
 2     print('======1')
 3     name
 4     print('======2')
 5     l = [1, 2, 3]
 6     l[100]
 7     print('======3')
 8     d = {}
 9     d['name']
10     print('======4')
11 
12 except NameError as e:
13     print('---->', e)
14 
15 结果为：
16 
17 ======1
18 ----> name 'name' is not defined
```

[![复制代码](https://common.cnblogs.com/images/copycode.gif)](javascript:void(0);)

定制什么类型异常，能捕获相应的异常，但是没有指定的异常的话还是会报错的，

[![复制代码](https://common.cnblogs.com/images/copycode.gif)](javascript:void(0);)

```
 1 try:
 2     print('======1')
 3     # name
 4     print('======2')
 5     l = [1, 2, 3]
 6     l[100]
 7     print('======3')
 8     d = {}
 9     d['name']
10     print('======4')
11 
12 except NameError as e:
13     print('---->', e)
14 
15 结果为：
16 
17 ======1
18 Traceback (most recent call last):
19 ======2
20   File "C:/Users/xu516/PycharmProjects/Python全栈开发/第三模块/面向对象编程/33 try...except详细用法.py", line 8, in <module>
21     l[100]
22 IndexError: list index out of range
```

[![复制代码](https://common.cnblogs.com/images/copycode.gif)](javascript:void(0);)

这样的话，能不能写多个except呢，答案是可以的，这就是异常的多分支

[![复制代码](https://common.cnblogs.com/images/copycode.gif)](javascript:void(0);)

```
 1 try:
 2     print('======1')
 3     # name
 4     print('======2')
 5     l = [1, 2, 3]
 6     # l[100]
 7     print('======3')
 8     d = {}
 9     d['name']
10     print('======4')
11 
12 except NameError as e:
13     print('---->', e)
14 
15 except IndexError as e:
16     print('---->', e)
17 
18 except KeyError as e:
19     print('---->', e)
20 
21 结果为：
22 
23 ======1
24 ======2
25 ======3
26 ----> 'name'
```

[![复制代码](https://common.cnblogs.com/images/copycode.gif)](javascript:void(0);)

这样就能捕获多种类型的异常，

多分支：被检测的代码块抛出的异常有多种可能性，并且我们需要针对每一种异常类型都定制专门的处理逻辑

[![复制代码](https://common.cnblogs.com/images/copycode.gif)](javascript:void(0);)

```
 1 try:
 2     print('======1')
 3     # name
 4     print('======2')
 5     l = [1, 2, 3]
 6     # l[100]
 7     print('======3')
 8     d = {}
 9     d['name']
10     print('======4')
11 
12 except NameError as e:
13     print('---->', e)
14 
15 except IndexError as e:
16     print('---->', e)
17 
18 except KeyError as e:
19     print('---->', e)
20 
21 print('after code')
22 
23 结果为：
24 
25 ======1
26 ======2
27 ======3
28 ----> 'name'
29 after code
```

[![复制代码](https://common.cnblogs.com/images/copycode.gif)](javascript:void(0);)

捕获异常后的代码会正常执行，

万能异常：Exception ,被检测的代码块抛出的异常有多种可能性，并且我们针对所有的异常类型都只用一种处理逻辑就可以了，那就使用Exception，

[![复制代码](https://common.cnblogs.com/images/copycode.gif)](javascript:void(0);)

```
 1 try:
 2     print('======1')
 3     # name
 4     print('======2')
 5     l = [1, 2, 3]
 6     # l[100]
 7     print('======3')
 8     d = {}
 9     d['name']
10     print('======4')
11 
12 except Exception as e:
13     print('---->', e)
14 
15 
16 print('after code')
17 
18 结果为:
19 
20  ======1
21 ======2
22 ======3
23 ----> 'name'
24 after code
```

[![复制代码](https://common.cnblogs.com/images/copycode.gif)](javascript:void(0);)

当然，万能异常也可以和定制异常混合使用，除了我们关心的异常使用定制异常，其它的异常类型我们使用万能异常

代码示例如下：

[![复制代码](https://common.cnblogs.com/images/copycode.gif)](javascript:void(0);)

```
 1 try:
 2     print('======1')
 3     name
 4     print('======2')
 5     l = [1, 2, 3]
 6     l[100]
 7     print('======3')
 8     d = {}
 9     d['name']
10     print('======4')
11 
12 except NameError as e:
13     print('---->', e)
14 
15 except IndexError as e:
16     print('---->', e)
17 
18 except KeyError as e:
19     print('---->', e)
20 
21 except Exception as e:
22     print('---->', e)
23 
24 
25 print('after code')
26 
27 结果为：
28 
29 ======1
30 ----> name 'name' is not defined
31 after code
```

[![复制代码](https://common.cnblogs.com/images/copycode.gif)](javascript:void(0);)

 还可以在except后加else判断语句，该语句会在被检测的代码块没有发生异常时执行

如：

[![复制代码](https://common.cnblogs.com/images/copycode.gif)](javascript:void(0);)

```
 1 try:
 2     print('======1')
 3     # name
 4     print('======2')
 5     l = [1, 2, 3]
 6     # l[100]
 7     print('======3')
 8     d = {}
 9     # d['name']
10     print('======4')
11 
12 except NameError as e:
13     print('---->', e)
14 
15 except IndexError as e:
16     print('---->', e)
17 
18 except KeyError as e:
19     print('---->', e)
20 
21 except Exception as e:
22     print('---->', e)
23 
24 else:
25     print('在被检测代码块没有发生异常时执行')
26 
27 
28 print('after code')
29 
30 结果为：
31 
32 ======1
33 ======2
34 ======3
35 ======4
36 在被检测代码块没有发生异常时执行
37 after code
```

[![复制代码](https://common.cnblogs.com/images/copycode.gif)](javascript:void(0);)

加finally语句，不管被检测的代码块有没有发生异常都会执行

[![复制代码](https://common.cnblogs.com/images/copycode.gif)](javascript:void(0);)

```
 1 try:
 2     print('======1')
 3     # name
 4     print('======2')
 5     l = [1, 2, 3]
 6     # l[100]
 7     print('======3')
 8     d = {}
 9     d['name']
10     print('======4')
11 
12 except NameError as e:
13     print('---->', e)
14 
15 except IndexError as e:
16     print('---->', e)
17 
18 except KeyError as e:
19     print('---->', e)
20 
21 except Exception as e:
22     print('---->', e)
23 
24 else:
25     print('在被检测代码块没有发生异常时执行')
26 
27 finally:
28     print('不管被检测的代码块有没有发生异常都会执行')
29 
30 
31 print('after code')
32 
33 结果为：
34 
35 
36 ======1
37 ======2
38 ======3
39 ----> 'name'
40 不管被检测的代码块有没有发生异常都会执行
41 after code
```

[![复制代码](https://common.cnblogs.com/images/copycode.gif)](javascript:void(0);)

finally的代码应用案例：

[![复制代码](https://common.cnblogs.com/images/copycode.gif)](javascript:void(0);)

```
 1 try:
 2     f = open('a.txt')
 3     print(next(f))
 4     print(next(f))
 5     print(next(f))
 6     print(next(f))
 7     print(next(f))
 8     print(next(f))
 9     print(next(f))
10 
11 finally:
12     print('final')
13     f.close()
14 
15 结果为：
16 
17 111
18 Traceback (most recent call last):
19 
20 222
21 
22 333
23   File "C:/Users/xu516/PycharmProjects/Python全栈开发/第三模块/面向对象编程/33 try...except详细用法.py", line 42, in <module>
24 
25 444
26     print(next(f))
27 
28 StopIteration
29 555
30 final
跳过异常继续执行
try:
        data=pd.read_csv('A_stock/overview-push-%d/stock overview.csv' %date, encoding='gbk')
        pieces.append(data)
except Exception as e:
        pass
continue
```