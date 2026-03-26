
# 21. 明天是星期几？

![[Pasted image 20260326084750.png]]
## 正确答案

```
d = int(input())
if d == 7:
    a = 1
else:
    a = d+1
print(a)
```

## 知识点就是

```
if else
```


# 22. 闰年计算

![[Pasted image 20260326090232.png]]
## 正确答案

```
year=int(input())
if year%400==0:
    print("yes")
elif year%4==0 and year%100!=0:
    print("yes")
else:
    print("no")
```

## 知识点

```
if elif else
```

# 23. 比大小

# 24. 分段函数

![[Pasted image 20260326091410.png]]

## 正确答案

```
n=int(input())
if n%2==1:
    f_n=3*n+1
else:
    f_n=n/2
print(int(f_n))
```

## 注意点

```
/会自带小数
```


# 25. 牛妹数

![[Pasted image 20260326091759.png]]


# 26. 牛牛是否被叫家长

![[Pasted image 20260326092101.png]]

# 27. 三个数字比大小

![[Pasted image 20260326093019.png]]
## 正确答案

```
numbers = list(map(int, input().split()))
print("The maximum number is :", max(numbers))
print("The minimum number is :", min(numbers))
```

## 知识点 max， min

```
针对的是可迭代对象
```

# 28. 四季

![[Pasted image 20260326093830.png]]

## 正确答案

```
m=int(input()[4:6])
if m>=3 and m<=5:
    print("spring")
elif m>5 and m<=8:
    print("summer")
elif m>8 and m<=11:
    print("autumn")
else:
    print("winter")
```


# 29. 多组输入

![[Pasted image 20260326095454.png]]

## 知识点

```
因为 `input()` 和 `sys.stdin` 读的其实是同一个输入流（standard input / Standardeingabe），只是读取方式不同。它们都是往后读，不会把已经读过的内容再读一遍。
```


## 正确答案

```
lines_numbers=int(input())
for _ in range(lines_numbers):
    a,b=map(int,input().split())
    print(a+b)
```

# 30. 多组数据a+b

![[Pasted image 20260326101203.png]]
## 知识点

```
`break`：直接结束整个循环
`continue`：跳过本轮循环，进入下一轮
区别在这里就是彻底结束(break)，还是跳过0 0组合(continue)
```


# 31. 素数

![[Pasted image 20260326160401.png]]

## 知识点

```
1. for
    if
	    break
else
结构
`for-else` 是一个语法糖，用于优雅地表达“查找失败”或“验证全部通过”的逻辑。
else之后就是不break的情况

2. all() 里面都是True才是True

3. 生成器表达式

(expression for item in iterable if condition)
`expression`：对每个元素执行的表达式
- 只能迭代一次，不支持索引和切片

反之列表推导式[expression for item in iterable if condition]
```


## 正确答案

### 方法1： for else

```
import sys
numbers=int(input())
for line in sys.stdin:
    n=int(line)
    if n>1:
        for i in range(2,n):
            if n%i==0:
                print("No")
                break
        else:
            print("Yes")
    else:
        print("No")
```

### 方法2：一些数学公式吧

```
def is_prime(n):
    return n > 1 and all(n % i != 0 for i in range(2, int(n ** 0.5) + 1))
```

# 32. 数列

![[Pasted image 20260326161131.png]]

## 正确答案

```
n=int(input())
sum=0
for i in range(1,n+1):
    sum+=(-1)**(i-1)*i
print(sum)
```

# 33. 牛牛学数列

![[Pasted image 20260326161746.png]]

## 正确答案

```
n=int(input())
H_n=0
for i in range(1,n+1):
    H_n+=1/i
print(format(H_n,".6f"))
```


# 34. 最大的差

- 思路就是拿最大值减去最小值

![[Pasted image 20260326163010.png]]

## 正确答案

```
n=int(input())
a=list(map(int,input().split()))
max_a=max(a)
min_a=min(a)
print(max_a-min_a)
```

# 34. 牛牛学数列4

- 知识点是子循环
- 外层循环
- 内循环

## 正确答案

```
n=int(input())
sum=0
for i in range(1,n+1):
    for j in range(1, i+1):
        sum+=j
print(sum)
```

# 35.  斐波那契数列

![[Pasted image 20260326171534.png]]
## 正确答案

### 思路1：循环

```
import sys

def fabi(n):
    if n <= 2:
        return 1
    a , b = 1,1
    for _ in range(n-2):
        a ,b = b,a+b
    return b

a=保留上一轮的b的值，b 保留上一轮的 ab的和

for line in sys.stdin:
    a = int(line.strip())
    print(fabi(a))
```


### 思路2：递归

```
n=int(input())
def cal_f(x):
    if x==1:
        return 1
    elif x==2:
        return 1
    else:
        return cal_f(x-1)+cal_f(x-2)
print(cal_f(n))
```