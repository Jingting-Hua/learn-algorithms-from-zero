
# 11. 平方根

## 所学内容

![[Pasted image 20260325111944.png]]

```
int(),对于正数来说来说就是直接去掉小数，等于是向下取整
```

```
math模块
1. `math.sqrt()` 求平方根: square root
2. `isqrt(x)`：返回非负整数平方根的整数部分
```


## 正确答案

```
import math
a = abs(int(input()))
b = int(math.sqrt(a))
print(b)
```


# 12. 反向输出4位数


## 正确答案

## 思路1：切割字符串

```
import sys
for line in sys.stdin:
    a = line.split()
    print(a[0][3]+a[0][2]+a[0][1]+a[0][0])
```

## 思路2：取出每一位的数字

```
import sys
for line in sys.stdin:
    a = int(line.split()[0])
    num1=a%10
    num2=a%100//10
    num3=a%1000//100
    num4=a//1000
    print(str(num1)+str(num2)+str(num3)+str(num4))
```

## 思路3： 反向打印

```
print(number[开始:结束:-1])
前开后闭
# 想要取到直接不写
print(number[3::-1])
# 列表的话输入和输出一样的
number = [1, 2, 3, 4]
print(number[::-1])
```


# 13. 简单计算

![[Pasted image 20260325115537.png]]

## 正确答案

```
K=float(input())
F=(K-273.15)*1.8+32
print(format(F,".11f"))
```

# 14. 绕距

![[Pasted image 20260325115912.png]]


## 知识点

```
map函数
map(对每个元素统一的函数,可迭代对象)
输出是map对象，所以需要list()转化成列表然后可以查看
```
## 正确答案

```
import math
x1, y1 = map(int, input().split())
x2, y2 = map(int, input().split())
dE = math.sqrt((x1 - x2) ** 2 + (y1 - y2) ** 2)
dM = abs(x1 - x2) + abs(y1 - y2) 
ans = abs(dM - dE)
print(ans)
```

# 15. 求四位数各个数位之和

![[Pasted image 20260325150850.png]]


## 正确答案

### 正确答案1：字符串的字符逐个取出

```
import sys
for line in sys.stdin:
    a = line.split()
    print(int(a[0][0]) + int(a[0][1])+int(a[0][2])+int(a[0][3]))
```

### 正确答案2：字符串的字符是可迭代对象

```
import sys
for line in sys.stdin:
    a = line.split()
    result=0
    for i in a[0]:
        result+=int(i)
    print(result)
```


# 16. 时间转换
![[Pasted image 20260325152516.png]]
## 正确答案

```
import sys
for line in sys.stdin:
    a = line.split()[0]
    hours=int(a)//3600
    minutes= int(a) % 3600// 60
    seconds=int(a) % 3600 % 60
    print(hours,minutes,seconds)
```

# 17. 计算机内存

![[Pasted image 20260325152757.png]]

## 正确答案

```
import sys
for line in sys.stdin:
    n = int(line.split()[0])
    number=int(n*1024*1024/4)
    print(number)
```

# 18. 计算表面积和体积

![[Pasted image 20260325153249.png]]
## 正确答案

```
import sys
for line in sys.stdin:
    a,b,c = map(int,line.split())
    S=2*(a*b+b*c+c*a)
    V=a*b*c
    print(f"{s}\n{v}")
```


# 19. 算成绩
![[Pasted image 20260325153532.png]]

## 正确答案

```
import sys
for line in sys.stdin:
    a,b,c=map(int,line.split())
    print(int(a*0.2+b*0.3+c*0.5))
```

# 20. 求和符号

![[Pasted image 20260325153857.png]]

## 所学

```
/ 自动产生小数
rang(2) 是0，1
rang(start,end,步长)
结果也需要list，因为是数字序列
和切片一样都是前闭后开
```

## 正确答案

```
import sys
for line in sys.stdin:
    a = line.split()[0]
    b=int(a)
    sum=0
    for i in range(b+1):
        sum+=i
    print(sum)
```

