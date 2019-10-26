### python字符串操作:

#### 字符串一般常用操作:

> 字符串的替换、删除、截取、复制、连接、比较、查找、分割等

#### 字符串内置操作方法:

> 使用type获取创建对象的类 type(name)
> 使用dir获取类的成员dir(name)
> 使用vars获取类的成员和各个成员的值

#### 字符串常用方法操作:

##### 1:casefold()将所有的字符转化为小写:

```
name = "ZhangSan"
print("{0}".format(name.casefold()))
# 打印结果:zhangsan

```

##### 2:capitalize()字符串首字母大写其他字符都小写:

```
name = "zhangSan"
name = name.capitalize()
print("{0}".format(name))
# 打印结果:Zhangsan
```

3:center()字符串宽度填充

```
name = "zhangSan"
name = name.center(12)
print("{0}".format(name))
# 打印结果:'  Zhangsan  '
# 默认以空格填充

name = "zhangSan"
name = name.center(12, "#")
print("{0}".format(name))
# 打印结果:'##Zhangsan##'
# 以‘#’填充
```

##### 4:count()统计字符在字符串中出现的次数:

```
name = "zhangSan"
num = name.count('S')
print("{0}".format(num))
# 打印结果:1

name = "zhangSan"
num = name.count('S', 0, 3) #从0，1，2索引里找
print("{0}".format(num))
# 打印结果:0

```

##### 5:encode()字符串编码:

```
name = "zhangsan"
name = name.encode('gbk')
print("{0}".format(name))
# 打印结果:b'zhangsan'
```

##### 6:startswith()判断字符串以某个字符串开头，返回boolean类型:

```
name = "zhangsan"
isTrue = name.startswith("zh")
print(isTrue)
# 打印结果:True
```

##### 7:endswith()判断字符串以某个字符串结尾，返回boolean类型:

```
name = "zhangsan"
isTrue = name.endswith("san")
print(isTrue)
# 打印结果:True
```

##### 8:find()在字符串中查找指定字符串，找不到时返回-1:

```
name = "zhangsan"
isIn = name.find("an")
print(isIn)
# 打印结果:2
# 返回字符串开始的下标
```

##### 9:format()格式化输出字符串:

```
name = "{} {} zhangsan" #"{} {}"是占位符，用下边format()里边的参数填充
name = name.format('I', 'am')
print(name)
# 打印结果:I am zhangsan
```

##### 10:index()在字符串中查找指定的字符串,找不到时直接报错:

```
name = "zhangsan"
isIn = name.index('h')
print(isIn)
# 打印结果:1
```

##### 11:join()字符串连接：

```
name = "zhangsan"
name = '*'.join(name)
print(name)
# 打印结果:z*h*a*n*g*s*a*n
```

##### 12:isalnum()判断字符串是否包含字母数字字符：

```
name = "zhangsan1"
isTrue = name.isalnum()
print(isTrue)
# 打印结果:True

name = "zhangsan1*"
isTrue = name.isalnum()
print(isTrue)
# 打印结果:False
```

##### 13:isalpha()判断是否只包含字母:

```
name = "zhangsan"
isTrue = name.isalpha()
print(isTrue)
# 打印结果:True

name = "zhangsan1"
isTrue = name.isalpha()
print(isTrue)
# 打印结果:False
```

##### 14:isdigit()判断字符串只由数字构成:

```
name = "1234"
isTrue = name.isdigit()
print(isTrue)
# 打印结果:True

name = "zhangsan1234"
isTrue = name.isdigit()
print(isTrue)
# 打印结果:False
```

##### 15:isspace()判断字符串是否是空格:

```
name = " "
isTrue = name.isspace()
print(isTrue)
# 打印结果:True

name = "zhang san"
isTrue = name.isspase()
print(isTrue)
# 打印结果:False
```

##### 16:isupper()判断字符串是否全是大写字符:

```
name = "ZHANGSAN"
isTrue = name.isupper()
print(isTrue)
# 打印结果:True
```

##### 17:lower()将所有的大写字符转为小写字符:

```
name = "ZHANGSAN"
name = name.lower()
print(name)
# 打印结果:zhangsan
```

##### 18:lstrip()去除字符串左边的空格:

```
name = "   zhangsan  "
name = name.lstrip()
print(name)
# 打印结果:zhangsan  
```

##### 19:rstrip()去除字符串右边的空格:

```
name = "   zhangsan  "
name = name.rstrip()
print(name)
# 打印结果:   zhangsan
```

##### 20:去除字符串2边的空格:

```
name = "   zhangsan   "
name = name.strip()
print(name)
# 打印结果:zhangsan
```

##### 21:replace()字符串替换:

```
name = "zhangsan"
name = name.replace("zhang", "li")
print(name)
# 打印结果:lisan
```

##### 22:split()字符串分割，默认是空格:

```
name = "zhang san"
name = name.split()
print(name)
# 打印结果:['zhang', 'san']
```

##### 23:**add**()在字符串后边添加字符串:

```
name = "zhang"
name = name.__add__("san")
print(name)
# 打印结果:zhangsan
```

##### 24:**contains**()判断指定字符串是否包含在字符串中:

```
name = "zhangsan"
isTrue = name.__contains__("san")
print(isTrue)
# 打印结果:True
```

##### 25:**eq**（）判断字符串是否相等:

```
name = "zhangsan"
name1 = "zhangsan"
isEq = name.__eq__(name1)
print(isEq)
# 打印结果:True
```

