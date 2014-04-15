## Octave Tutorial

### Installation Instructions for Windows
请看[这里](http://mind.cog.jhu.edu/courses/680/octave/installingoctave.html)。

### Basic Operations
在Octave的Prompt中可以进行基础的算数运算、幂运算、布尔运算。

false用0表示，true用1表示

- `~=`  不等于
- `&&`  与
- `||`  或
- `xor()`  异或

声明变量后如果希望不立即在终端输出，后面加一个';'。

更复杂的输入操作用`disp()`。

`sprintf()`类似C语言中的sprintf（构造一个字符串）。

```
e.g.
>> disp(sprintf('2 decimals: %0.2f', pi))
>> 2 decimals: 3.14
```

- `format long` 
- `format short`  改变Octave的标准输出和disp函数的format（小数点位数） 

- `v = 1:0.1:2` 生成一个行向量，从1开始，步长为0.1，直到2
- `v = 1:6` 生成一个行向量，步长为默认为1

- `ones(2, 3)` 生成一个2行3列的全1矩阵
- `c = 2 * ones(2, 3)` 对上一个矩阵的每个元素都乘以2（得到一个全2的矩阵）
- `zeros(1, 3)`  生成一个1行3列的全0矩阵
- `rand(1, 3)`  生成一个1行3列的矩阵，每个元素是介于0和1之间的随机数
- `randn(1, 3)`  生成一个1行3列的矩阵，其元素符合高斯分布

- `eye(4)` 生成一个4阶单位阵
- `help eye` 查看eye命令的帮助文档

### Moving Data Around

- `size(A)` 返回矩阵A的行数和列数（以矩阵的形式）
- `size(A, 1)` 返回矩阵A的第一个维度的size（行数）
- `length(A)` 返回A的最长的维度的size，一般被用在向量上

- `pwd` 显示当前Octave所在的路径
- `cd 'C:\Users\'` 更改Octave当前的路径
- `ls`  显示当前路径下的文件或目录

将当前路径下的featuresX.dat load到Octave中。

- `load featuresX.dat`
- `load('featuresX.dat')`

显示在当前的Octave的workspace中有哪些变量

- `who` 
- `whos` 并显示变量的详细信息 

- `clear featuresX` 将当前workspace中的featuresX变量删除，再次输入`who`或者`whos`则没有featuresX这个变量了

将一个变量以文件的形式持久化：

- `v = priceY(1:10)` 将priceY的前10个元素赋值给v（矩阵）
- `save hello.mat v`  将v保存在当前路径下的hello.mat文件中

之后可以通过`load`命令将变量v重新加载进来

- `save hello.txt v -ascii` 持久化为ascii形式

对一个矩阵进行元素索引，可以通过索引获得元素或者给其赋值：

```
>> A = [1 2; 3 4; 5 6]
>> A(3, 2) % A的第3行第2列的元素
>> A(2,:) % A的第2行的所有元素
>> A(:,2) % A的第2列的所有元素
>> A([1 3], :) % A的第1行和第3行的所有元素（[1 2; 5 6]）
>> A = [A, [100; 101; 102]] % 在A后面附加上一个新的列，将值赋给A
>> A(:) % 将A中所有元素放到一个列向量中
```

### Computing on Data
Octave支持矩阵之间的运算（相乘等）。

- `A * B` 计算矩阵A与矩阵B相乘

其同时也支持矩阵元素级的运算。

- `A .* B` 将矩阵A的每个元素乘以相应位置的矩阵B的元素，得到一个新的矩阵
- `A .^ 2` 将矩阵A的每个元素都进行平方之后，得到一个新的矩阵
- `1 ./ A` 将矩阵A的每个元素取倒数后，得到一个新的矩阵
- `log(V)` 将矩阵V的每个元素与对数得到一个新的矩阵
- `exp(V)` 将矩阵V的每个元素进行e次幂吼得到一个新矩阵
- `abs(V)` 将矩阵V的每个元素取绝对值吼得到一个新的矩阵
- `-V` 将V每个元素乘以-1
- `A'` A的转置矩阵
- `max(V)` 返回向量V中最大的元素(V是一个向量)
- `[val, index] = max(V)` val是最大值，index是最大值所在位置的索引
- `A < 3` 返回一个由0和1构成的矩阵，如果一个元素小于3，该位置为1（true），否则为0（false）
- `[row, column] = find(A < 3)`
- `magic(3)` 返回一个3阶矩阵，其中每行每列还有对角线的元素之和都相等
- `sum(a)` 返回a中所有元素的和
- `prod(a)` 返回a中所有元素的积
- `floor(a)` 将a中每个元素做floor运算
- `ceil(a)` 将a中的每个元素做ceil运算
- `max(A, B)` 返回一个矩阵，其中的元素由A和B对应位置上较大的元素构成
- `max(A, [], 1)` 返回一个行向量，每个元素是由A中的**每一列**较大的元素构成
- `max(A, [], 2)` 同上，列向量，**每一行**
- `max(max(A))` 或 `max(A(:))` 返回矩阵A的最大的一个元素
- `sum(A, 1)` 返回一个行向量，每个元素是矩阵A的对应的列的和
- `sum(A, 2)` 同上，列向量，行的和
- `pinv(A)` A的逆


