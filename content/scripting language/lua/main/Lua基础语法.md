# Lua基础语法

## 一、Lua 基础认识：

> Lua的脚本文件后最为`.lua`

### 1.注释：

- 单行注释：`--`
- 多行注释：`--[[ 多行注释 多行注释 --]]`

### 2.标识符：

&emsp;&emsp;Lua 标示符用于定义一个变量，函数获取其他用户定义的项。标示符以一个字母 A 到 Z 或 a 到 z 或下划线 _
开头后加上0个或多个字母，下划线，数字（0到9）。

### 3.关键字：

&emsp;&emsp;以下列出了 Lua 的保留关键字。保留关键字不能作为常量或变量或其他用户自定义标示符：

![](img/Snipaste_2022-10-14_22-08-28.png)

&emsp;&emsp;一般约定，以下划线开头连接一串大写字母的名字（比如 _VERSION）被保留用于 Lua 内部全局变量。

### 4.全局变量：

&emsp;&emsp;**在默认情况下，变量总是认为是全局的。**

&emsp;&emsp;全局变量不需要声明，给一个变量赋值后即创建了这个全局变量，访问一个没有初始化的全局变量也不会出错，只不过得到的结果是：nil。

```lua
b = nil
print(b)      --> nil
```

&emsp;&emsp;如果你想删除一个全局变量，只需要将变量赋值为nil。

<hr/>

## 二、Lua 数据结构：

> Lua是动态类型语言，变量不要类型定义,只需要为变量赋值。 值可以存储在变量中，作为参数传递或结果返回。

Lua中有8个基本类型分别为：nil、boolean、number、string、userdata、function、thread和table

![](img/Snipaste_2022-10-14_22-21-22.png)

我们可以使用type函数测试给定变量或者值的类型:

```lua
print(type("Hello world"))      --> string
print(type(10.4 * 3))             --> number
print(type(print))              --> function
print(type(type))               --> function
print(type(true))               --> boolean
print(type(nil))                --> nil
print(type(type(X)))            --> string
```

### 1.nil（空 Null）:

nil 类型表示一种没有任何有效值，它只有一个值 -- nil，例如打印一个没有赋值的变量，便会输出一个 nil 值。

对于全局变量和 table，nil 还有一个"删除"作用，给全局变量或者 table 表里的变量赋一个 nil 值，等同于把它们删掉

```lua
tab1 = { key1 = "val1", key2 = "val2", "val3" }
for k, v in pairs(tab1) do
    print(k .. " - " .. v)
end

tab1.key1 = nil
for k, v in pairs(tab1) do
    print(k .. " - " .. v)
end
```

使用 nil 作比较时应该加上双引号：

```lua
> type(X)
nil
> type(X)==nil
false
> type(X)=="nil"
true
>
```

### 2.boolean 布尔类型：

boolean 类型只有两个可选值：true（真） 和 false（假），Lua 把 false 和 nil 看作是"假"，其他的都为"真":

```lua
print(type(true))
print(type(false))
print(type(nil))

if false or nil then
    print("至少有一个是 true")
else
    print("false 和 nil 都为 false")
end

if 0 then
    print("数字 0 是 true")
else
    print("数字 0 为 false")
end
```

### 3.number 数字类型：

Lua 默认只有一种 number 类型 -- double（双精度）类型（默认类型可以修改 luaconf.h 里的定义），以下几种写法都被看作是 number
类型：

```lua
print(type(2))
print(type(2.2))
print(type(0.2))
print(type(2e+1))
print(type(0.2e-1))
print(type(7.8263692594256e-06))
```

### 4.string 字符串：

字符串由一对双引号或单引号来表示。

```lua
string1 = "this is string1"
string2 = 'this is string2'
```

也可以用 2 个方括号 "[[]]" 来表示"一块"字符串。

```lua
html = [[
<html>
<head></head>
<body>
    <a href="//www.csbox.com/">CSBOX</a>
</body>
</html>
]]
print(html)
```

字符串连接使用的是 ..

```lua
> print("a" .. 'b')
ab
> print(157 .. 428)
157428
> 
```

使用 # 来计算字符串的长度，放在字符串前面，如下实例：

```lua
> len = "www.w3cschool.cn"
> print(#len)
16
> print(#"www.csbox.com")
13
> 
```

### 5.table 表：

