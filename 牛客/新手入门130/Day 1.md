
# 1. 你需要输出的问候信息为 "Hello Nowcoder!"

```
print("Hello Nowcoder!")
```


# 2. 输入输出相同的整数

![[Pasted image 20260324200655.png]]

## 学习内容
```
# 读取一行的输入
`stdin` 是 标准输入（standard input） 的缩写。
`sys.stdin.readline()` 会读取一行输入（包括换行符）
sys.stdin 的结果是可遍历的str
`.strip()`：去除字符串两端的空白字符（包括换行符、空格等），得到纯数字字符串，如 `"42"`。
`input()` 函数实际上也是从 `sys.stdin` 读取数据，但它会去掉末尾的换行符并返回字符串。
```


```
- `__name__` 就像这个脚本的“身份”。
- 如果脚本是直接运行的，它的身份就是 `"__main__"`（相当于“我是主角”）。
“如果我是主角，那就执行 main()；如果我只是个被导入的配角，就别乱动。
if __name__ == "__main__":
    main()
```
## 正确答案

### 正确答案1

```
import sys

def main():
    # 读取一行输入，去除两端空白，转换为整数
    n = int(sys.stdin.readline().strip())
    # 输出该整数
    print(n)

if __name__ == "__main__":
    main()
```

### 正确答案2

```
print(int(input()))
```

### 正确答案3

```
import sys

print(int(sys.stdin.readline().strip()))
```

# 3. 浮点数，但是有小数的转换

![[Pasted image 20260324202757.png]]
![[Pasted image 20260324203520.png]]
## 学习内容： format输出字符串

```
n = float(input())

# 小数后边保留几位
# 能四舍五入也能增加很多000
print(format(n,'.3f'))
print(format(n, ".3f"))
```


# 4. 字符串的直接输入和输出

# 5. 多行的输入怎么处理

![[Pasted image 20260324210130.png]]

## 学习内容

```
\n 作为换行符
print()自带print(end="\n"),改成print(end="")即可
```

```
如果在 `try` 块中发生错误（如 `float(c)` 转换失败），程序会立即跳转到 `except` 块执行其中的代码，而不会让程序崩溃。

这里要事先知道可能的错误比如ValueError，
```

```
input()
sys.stdin.readline() 会按照顺序读多行的
```
## 正确答案

```
import sys
def main():
    # 读取5行，并去除首尾空白（包括换行符）
    a = sys.stdin.readline().strip()
    b = sys.stdin.readline().strip()
    c = sys.stdin.readline().strip()
    d = sys.stdin.readline().strip()
    e = sys.stdin.readline().strip()
    # 处理第三行：转换为浮点数并保留一位小数
    try:
        c_num = float(c)
        c = format(c_num, '.1f')
    except ValueError:
        # 理论上不会发生，因为输入保证是浮点数
        pass
    # 按顺序输出，每个输出自动换行
    print(a)
    print(b)
    print(c)
    print(d)
    print(e)
if __name__ == "__main__":
    main()
```


# 6. 整数加法
![[Pasted image 20260325110930.png]]

## 学习内容

```
split()表示用空格分隔，split(","),结果是list列表
```

## 正确答案

```
import sys

for line in sys.stdin:

    a = line.split()

    print(int(a[0]) + int(a[1]))
```


# 7. 


![[Pasted image 20260325110821.png]]
## 学习内容: 字符串的拼接？

```
1. print()里面必须要是字符串啊
2. print(+)直接拼接
3. print(，) 空格拼接
4. x = 3.1415926  
print(f"{x:.2f}")
: 表示格式化说明
```

## 正确答案

```
import sys

  

for line in sys.stdin:

    a = line.split()

    print(format(int(a[1])/int(a[0])*100,".3f")+"%")
```


# 8

![[Pasted image 20260325110952.png]]
## 学习内容：整数除法//，和%余数

## 正确答案

```
import sys

for line in sys.stdin:

    n = line.split()

    a=int(n[0])

    b=int(n[1])

    c= a//b

    d= a-c*b

    print(str(c),str(d))
```


# 9. 整数的个位
![[Pasted image 20260325111008.png]]
其实就是绝对值%10

## 所学内容：求绝对值使用内置函数 `abs()`

```
absolute value: abs()
```

# 10. 提取整数的10位

![[Pasted image 20260325110442.png]]
## 所学内容

```
n = int(input())
print(n%100//10)


% 可以理解成保留到哪一位，而且是从个位往前保留
% 10 保留个位
% 100 就是保留10位和个位

// 就是从前往后保留

// 1 就是保留本身
// 10 就是前两位
// 100
```