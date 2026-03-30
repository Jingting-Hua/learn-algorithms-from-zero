
# 41.
![[Pasted image 20260330124609.png]]

## 所学

```
"分隔符".join(可迭代字符串对象)！
```

```
a.pop()会把原来的列表的最后一个删去
当然也可以构造一个空列表，一个一个加跳过==0的情况
```

## 正确答案

```
a=list(map(int,input().split()))
a.pop()
print(" ".join(map(str,a[::-1])))
```


# 42. 左侧严格小于计数

![[Pasted image 20260330143938.png]]


## 正确答案

```
a=int(input())
b=list(map(int,input().split()))
e=[]
for i in range(a):
    c=b[:i+1]
    d=b[i]
    sum=0
    for j in c:
        if j<d:
            sum+=1
    e.append(str(sum))

print(" ".join(e))
```


# 43. 牛牛的数学作业

![[Pasted image 20260330145854.png]]

## 正确答案

```
T = int(input())
for _ in range(T):
    n = int(input())
    a = list(map(int, input().split()))
    c = max(a) - min(a)
    d = sum(a) / len(a)
    e = 0
    for i in a:
        e += (i - d) ** 2
    e = e / len(a)
    print(c, format(e,".3f"))
```

# 44. 数组计数维护

![[Pasted image 20260330151435.png]]

## 正确答案

```
T=int(input())
for _ in range(T):
    S=0
    cnt=0
    a=list(map(int,input().split()))
    n=a[0]
    k=a[1]
    b=list(map(int,input().split()))
    for i in b:
        if i>=k:
            S+=i
        if i==0 and S>=1:
            S-=1
            cnt+=1
    print(cnt)
```

# 45.

![[Pasted image 20260330153416.png]]

## 知识点

```
数一数某个东西出现了几次。
count()函数: 可以用在字符串，也可以在列表
print("hello".count("l"))     # 2
print([1, 1, 2, 3].count(1))  # 2
print("aaaa".count("aa"))     # 2

# 找字符串找内容
find()和index()都会回复第一次出现的下标
find找不到-1，index直接报错
列表用index，没有find方法
```
## 正确答案

### 思路1：将所有的"x"变成单个的字符保留在list里面然后遍历

```
n, x = map(int, input().split())
def cal(n, x):
    sum = 0
    lst = []
    for i in range(1, n + 1):
        if len(str(i)) == 1:
            lst.append(str(i))
        else:
            for j in str(i):
                lst.append(j)
    for i in lst:
        if i == str(x):
            sum += 1
    return sum
print(cal(n, x))
```

### 思路2：统计出现次数

```
n,x=map(int,input().split())
a = [str(i) for i in range(1,n+1)]
b = "".join(a)
print(b.count(str(x)))
```

# 46. 约瑟夫环: 难

![[Pasted image 20260330201637.png]]

这里重要的是找到这个k的变动规律k=(k+m-1)%n

## 所学

```
pop(k) 是可以按照index删除的
remove 按照的是值，而且也是第一个值
```


```
n,k,m=map(int,input().split())  
l=list(range(n))  
while n>=2:  
k=(k+m-1)%n  
l.pop(k)  
n-=1  
print(*l)
```


# 47. 校门外的树 （思想：用数组表示街道树的状态：有树/没有树）

![[Pasted image 20260330180207.png]]

## 正确答案

```
trees,groups=map(int,input().split())
trees=trees+1
c=[1]*trees
for _ in range(groups):
    a,b=map(int,input().split())
    for i in range(a,b+1):
        c[i]=0
print(c.count(1))
```


# 48：单组_二维数组

![[Pasted image 20260330180807.png]]

## 正确答案

```
n,m=map(int,input().split())
sum_=0
for _ in range(n):
    a=list(map(int,input().split()))
    sum_+=sum(a)
print(sum_)
```


# 49. 上三角矩阵判定：关注违规的例子

![[Pasted image 20260330194655.png]]
## 学会了啥

```
exit() 就是直接退出，不运行了
单层 `for` 里，`for/else` 往往更顺手；双层 `for` 里，`exit()` 或“标记 + break”通常更方便。
```

``` 单层for
for i in range(n):
    for j in range(i):
        if 条件成立:
            break
    else:
        ...
```

```
双层for
```

## 正确答案


### 思路1

只要满足！=1，马上输出NO，否则输出YES

```
n=int(input())
lst=[]
for _ in range(n):
    a=list(map(int,input().split()))
    lst.append(a)
for i in range(n):
    for j in range(i):
        if lst[i][j]!=0 and lst[j][i]!=0 and  lst[j][j]!=0:
            print("NO")
            exit()
print("YES")
```


## 思路2：

打标记或者写成方法直接return

```
n = int(input())
lst = []

for _ in range(n):
    lst.append(list(map(int, input().split())))

found = False

for i in range(n):
    for j in range(i):
        if lst[i][j] != 0 and lst[j][i] != 0 and lst[j][j] != 0:
            found = True
            break
    if found:
        break
if found:
    print("NO")
else:
    print("YES")
```

# 50. 矩阵转置

![[Pasted image 20260330201530.png]]

## 正确答案

```
n,m=map(int,input().split())
lst=[]
trans_lst=[]
for _ in range(n):
    lst.append(list(map(int,input().split())))
for i in range(m):
    a=[]
    for j in range(n):
        a.append(lst[j][i])
    trans_lst.append(a)  
for i in trans_lst:
    print(" ".join(map(str,i)))
```