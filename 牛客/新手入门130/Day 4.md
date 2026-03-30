
# 37. 数位之和

![[Pasted image 20260327083353.png]]


## 正确答案


### 思路总体：用字符串做，实现1：字符串做切片

```
a=input()
b=len(a.strip())  
sum=0
for i in range(b):
    sum+=int(a[i])
print(sum)
```


### 实现2：字符串本身可循环

```
number = abs(int(input()))
sum = 0
for i in str(number):
    sum = sum + int(i)
print(sum)
```


### 实现3： 利用列表生成式

```
a=input()
b=len(a.strip()) 
print(sum([int(i) for i in a]))
```


# 38

牛牛在酒桌上玩一个小游戏，第一个人从 11 开始数数，如果遇到数字中含有数字 44 或数字是 44 的倍数，则<mark style="background: #FFB8EBA6;">跳过</mark>这个数字报下一个，谁数错了就要罚酒一杯。

有两种思路：
1. 正常就是跳过其实就是for 里面的continue，满足条件的跳过就行， else 里面执行代码
2. 否则就是条件直接取反

```
a=input()
b=str(a)
n=int(a)
for i in range(1,n+1):
    if (str(4) not in str(i)) and (i%4!=0):
        print(i)
```

## 知识点

```
not in/ in
判断单词里有没有某字母
word = "banana"  
print('a' in word) # True
列表里有没有某元素
arr = [10, 20, 30]
print(20 in arr)     # True
```


# 39. 牛牛学数列6

![[Pasted image 20260327085441.png]]

## 正确答案

```
def cal_An(n):
    if n==1:
        return 0
    elif n==3 or n==2:
        return 1
    else:
        return cal_An(n-3)+2*cal_An(n-2)+cal_An(n-1)
n=int(input())  
print(cal_An(n))
```


# 40. 二维斐波那契数列
![[Pasted image 20260327091100.png]]

## 知识点：二维数组，递归会超时

```

```