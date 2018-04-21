##### 比较
```
>>> 1.00 == 1
True

```

##### divmod
```
In [15]: help(divmod)
Help on built-in function divmod in module builtins:

divmod(x, y, /)
    Return the tuple (x//y, x%y).  Invariant: div*y + mod == x.
```
##### str.center
```
In [17]: help(str.center)
Help on method_descriptor:

center(...)
    S.center(width[, fillchar]) -> str

    Return S centered in a string of length width. Padding is
    done using the specified fill character (default is a space)

```

##### random 模块
```
import random
random.shuffle(seq)方法将序列的所有元素随机排序。
random.choice(seq)方法返回一个列表，元组或字符串随机选择一个元素。
random.sample(seq,n)方法从列表中随机选择一组元素
random.random()方法生成一个随机的浮点数，范围是在0.0~1.0之间
random.uniform(x,y)方法将随机生成一个实数，在[x,y]范围内。
random.randint(x,y)随机生一个整数int类型，可以指定这个整数的范围在[x,y]
```

##### str.strip
```
>>> 'aaass dddaa sssaaa'.strip("aa")
'ss dddaa sss'
>>> help(str.strip)
Help on method_descriptor:

strip(...)
    S.strip([chars]) -> str

    Return a copy of the string S with leading and trailing
    whitespace removed.
    If chars is given and not None, remove characters in chars instead.
```

##### str.join
```

>>> "-".join('china')
'c-h-i-n-a'
>>>
>>> help(str.join)
Help on method_descriptor:

join(...)
    S.join(iterable) -> str

    Return a string which is the concatenation of the strings in the
    iterable.  The separator between elements is S.

```

##### chr
```
>>> chr(36)
'$'
>>> help(chr)
Help on built-in function chr in module builtins:

chr(i, /)
    Return a Unicode string of one character with ordinal i; 0 <= i <= 0x10ffff.

```


##### PyInstaller 库的使用

将.py源代码转换成无需源代码的可执行文件
`pip install pyinstaller`

`PyInstaller` 库常用参数

```
-h     查看帮助 
--clean 清理打包过程中的临时文件 
-D, --onedir     默认值，生成dist文件夹 
-F, --onefile     在dist文件夹中只生成独立的打包文件 
-i <图标文件名.ico>     指定打包程序使用的图标(icon)文件

pyinstaller –i curve.ico –F SevenDigitsDrawV2.py

```

##### 耦合
```
- 紧耦合：两个部分之间交流很多，无法独立存在
- 松耦合：两个部分之间交流较少，可以独立存在
- 模块内部紧耦合、模块之间松耦合

```


# 文本进度条
import time 
scale = 50 
print("执行开始".center(scale//2, "-")) 
start = time.perf_counter() 
for i in range(scale+1): 
    a = '*' * i 
    b = '.' * (scale - i) 
    c = (i/scale)*100
    dur = time.perf_counter() - start 
    print("\r{:^3.0f}%[{}->{}]{:.2f}s".format(c,a,b,dur),end='') 
    time.sleep(0.1) 


# 计算圆周率
from random import random 
from time import perf_counter 
DARTS = 1000 * 1000 
hits = 0.0 
start = perf_counter() 
for i in range(1, DARTS+1): 
    x, y = random(), random() 
    dist = pow(x ** 2 + y ** 2, 0.5) 
    if dist <= 1.0: 
        hits = hits + 1 
pi = 4 * (hits/DARTS) 
print("圆周率值是: {}".format(pi)) 
print("运行时间是: {:.5f}s".format(perf_counter()-start))












