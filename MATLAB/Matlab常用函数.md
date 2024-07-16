# Matlab常用函数

## 1、求组合数

通过MATLAB计算排列数与组合数以及使输出结果为分数的命令分别为：

![{C_n^k}](https://private.codecogs.com/gif.latex?%7BC_n%5Ek%7D)——`nchoosek(n,k)`

![{A_n^k}](https://private.codecogs.com/gif.latex?%7BA_n%5Ek%7D)——`factorial(n)/factorial(n-k)`

fotmat rat——输出结果为分数

例：nchoosek(4,2) = 6.

## 2、求阶乘

 ![n!](https://private.codecogs.com/gif.latex?n%21)——`factional(n)`或`prod(1:n)`

求n!.则输入：

`Factorial(n)`.

例：factorial(5) = 120.

## 3、求全排列

perms(x).

例：求x = [1,2,3];

```matlab
Perms(x)，输出结果为：

 

ans =

 

3 2 1

 

3 1 2

 

2 3 1

 

2 1 3

 

1 2 3

 

1 3 2
```

## 4、求指数

求a^b：power(a,b) ;

例：求2^3 ;

Ans = pow(2,3) ;

## 5、求行列式

求矩阵A的行列式：det(A);

例：A=[1 2;3 4] ;

则det(A) = -2 ;

## 6、求矩阵的转置

求矩阵A的转置矩阵：A’

转置符号为单引号.

```matlab
>>A=[1 2;3 4]

>>A =

     1     2
     3     4
>>A'

>>ans =

     1     3
     2     4
```



## 7、求向量的指数

求向量p=[1 2 3 4]'的三次方：p.^3

例：

p=[1 2 3 4]'

A=[p,p.^2,p.^3,p.^4]

```matlab
p=[1 2 3 4]'...

A=[p,p.^2,p.^3,p.^4]

p =

     1
     2
     3
     4


A =

     1     1     1     1
     2     4     8    16
     3     9    27    81
     4    16    64   256
```



> 注意：在p与符号”^”之间的”.”不可少.

## 8、求自然对数

求ln(x)：Log(x)

例：log(2) = 0.6931

```matlab
log(2)

ans =

    0.6931
```



## 9、求矩阵的逆矩阵

求矩阵A的逆矩阵：inv(A)

```matlab
>> A1=[1 2 2;2 1 -2;2 -2 1]

 

A1 =

 

     1     2     2

     2     1    -2

     2    -2     1

 

 

>> A2=inv(A1)

 

A2 =

 

    0.1111    0.2222    0.2222

    0.2222    0.1111   -0.2222

    0.2222   -0.2222    0.1111

 

 

>> A3=[-3 -6 -6;-6 -3 6;-6 6 -3]

 

A3 =

 

    -3    -6    -6

    -6    -3     6

    -6     6    -3

 

>> A4=-(1./27)*A3

 

A4 =

 

    0.1111    0.2222    0.2222

    0.2222    0.1111   -0.2222

    0.2222   -0.2222    0.1111

 

>> 
```

## 10、多项式的乘法运算

函数**conv(p1,p2)**用于求多项式p1和p2的乘积。这里，p1、p2是两个多项式系数向量。

例：求多项式和的乘积。

命令如下：

```matlab
p1=[1 8 0 0 -10];
>> p2=[2,-1,3];
>> c=conv(p1,p2)

c =

  列 1 至 6

     2    15    -5    24   -20    10

  列 7

   -30
```

## 11、多项式除法

函数**[q，r]=deconv(p1，p2)**用于多项式p1和p2作除法运算，其中q返回多项式p1除以p2的商式，r返回p1除以p2的余式。这里，q和r仍是多项式系数向量。

例： 求多项式除以多项式的结果。

命令如下：

```matlab
>> p1=[1,8,0,0,-10];
>> p2=[2,-1,3];
>> [q,r]=deconv(p1,p2)

q =

    0.5000    4.2500    1.3750


r =

  列 1 至 4

         0         0         0  -11.3750

  列 5

  -14.1250
```

## 12、求一个向量的最大值

求一个向量x的最大值的函数有两种调用格式，分别是：

（1）max(x)：返回向量x的最大值，如果x中包含复数元素，则按模取最大值。

（2）[y, i]=max(x)：返回向量x的最大值存入y，最大值的序号存入i，如果x中包含复数元素，则按模取最大值。

求向量x的最小值函数是min(x)，用法与max(x)完全相同。

```matlab
>>max(p1)

ans =

     8

>> [y,i]=max(x)

y =

     3


i =

     3
```



## 13、求矩阵的最大值和最小值

求矩阵A的最大值的函数有三种调用格式，分别是：

（1）max(A)：返回一个行向量，向量的i个元素是矩阵A的第i列的最大值。

（2）[y,u]=max(A)：返回行向量y和u，y纪录A的每列的最大值，u纪录每列最大值的行号。

求矩阵A的最小值的函数min(A)，用法与max(A)完全相同。

## 14、求和与求积

数据序列求和与求积函数是sum和prod，其使用方法类似。设x是一个向量，A是一个矩阵，函数的调用格式为：

- sum(x)：返回向量x各元素之和。

- ```matlab
  sum(p1)
  
  ans =
  
      -1
  ```

  

- Sum(A,1):返回矩阵A的列求和后的行向量。

- Sum(A,2):返回矩阵A的行求和后的列向量。

- ```matlab
  >>A =
  
      9.6294    9.2647    9.9150
      9.8116    8.1951    9.9298
      8.2540    8.5570    8.3152
      9.8268    9.0938    9.9412
  
  >> sum(A,1)
  
  ans =
  
     37.5218   35.1106   38.1012
  
  >> sum(A,2)
  
  ans =
  
     28.8092
     27.9364
     25.1262
     28.8617
  ```

  

- prod(x)：返回向量x各元素的乘积。

- ```matlab
  >> A
  
  A =
  
    4×3 int32 矩阵
  
     10    9    9
      9   10    8
     10   10   10
      8   10   10
  
  >> prod(A)
  
  ans =
  
          7200        9000        7200
  
  ```

  

- sum(A,i)：返回一个行向量，其第i个元素是A的第i列的元素之和。

- ```matlab
  >> sum(A,2)
  
  ans =
  
      28
      27
      30
      28
  ```

  

- prod(A,i)：返回一个行向量，其第i个元素是A的第i列的元素乘积。

- ```matlab
  >> prod(A,2)
  
  ans =
  
           810
           720
          1000
           800
  ```

  

- sum(A，dim)：当dim为1时，该函数等同于sum(A)；当dim为2时，返回一个列向量，其第i个元素是A的第i行的元素之和。

- prod(A，dim)：当dim为1时，该函数等同于prod(A)；当dim为2时，返回一个列向量，其第i个元素是A的第i行的元素乘积。

## 15、平均值、标准方差

MATLAB提供了mean，std函数来计算平均值、标准方差或方差。这些函数的调用方法如下：

- mean(x)：返回向量x的算术平均值。

- std(x)：返回向量x的标准方差。

  ```
  
  ```

  

对于矩阵A，mean函数的一般调用格式为：

```matlab
y=mean(A,dim)
```

这里，dim取1或2。当dim=1时，返回一个行向量y，y的第i个元素是A的第i列元素的平均值；当dim=2时，返回一个列向量y，y的第i个元素是A的第i行元素的平均值。

对于矩阵A，std函数的一般调用格式为：

```matlab
y=std(A,flag,dim)
```

这里，dim取1或2。当dim=1时，求各列元素的标准方差；当dim=2时，求各行元素的标准方差。flag取0或1，当flag=0时，按计算标准方差；当flag=1时，按计算方差。缺省flag=0，dim=1。

## 16、相关系数

对于两组数据序列，其相关系数的计算, MATLAB提供了corrcoef函数来计算相关系数，corrcoef函数的调用格式为：

```bash
r=corrcoef(x,y)
```

| R = corrcoef(A)        | 返回 A 的相关系数的矩阵，其中 A 的列表示随机变量，行表示观测值。 |
| ---------------------- | ------------------------------------------------------------ |
| R = corrcoef(A, B)     | 返回两个随机变量 A 和 B 之间的系数。                         |
| [R, P] = corrcoef(___) | 返回相关系数的矩阵和 p 值矩阵，用于测试观测到的现象之间没有关系的假设（原假设）。 此语法可与上述语法中的任何参数结合使用。 如果 P 的非对角线元素小于显著性水平（默认值为 0.05），则 R 中的相应相关性被视为显著。 如果 R 包含复数元素，则此语法无效。 |

```matlab
XX = 1993 : 2012;

XX = XX';

YY = [20 27 21 22 16 15 14 17 18 16 13 15 14 16 13 10 17 12 15 15]';

ZZ = -0.4481 * XX + 21.005;

[r, p] = corrcoef(YY, ZZ);

 

r =

 

   1.000000000000000   0.685477816431251

   0.685477816431251   1.000000000000000

 

p =

 

   1.000000000000000   0.000850527565975

   0.000850527565975   1.000000000000000
```

## 17、排序

对向量元素的进行排序是一种经常性的操作，MATLAB提供了sort函数对向量x进行排序。

- y=sort(x)：返回一个对x中元素按升序排列后的向量y。
- [y，i]=sort(x)：返回一个对x中的元素按升序排列的向量y，而i记录y中元素在x中的位置。

```matlab
>> a=[1,2,3;4,6,0;0,5,2]

 

a =

 

     1     2     3

     4     6     0

     0     5     2

 

>> sort(a)

 

ans =

 

     0     2     0

     1     5     2

     4     6     3

 

>> sort(a,'descend')

 

ans =

 

     4     6     3

     1     5     2

     0     2     0

 

>> sort(a,'ascend')

 

 ans =

 

     0     2     0

     1     5     2

     4     6     3
```

即matlab中对矩阵默认按列升序排序。

> **降序排序使用sort(a,'descend')**
>
> **升序使用sort(a,'ascend')**

## 18、多项式的求导

对多项式求导数的函数是：

- p=polyder(p1)：求多项式p1的导函数。
- p=polyder(p1,p2)：求多项式p1和p2乘积的导函数。
- [p,q]=polyder(p1,p2)：求多项式p1和p2之商的导函数，p、q是导函数的分子、分母。

例： 求有理分式的导函数。

命令如下：

```bash
p1=[1,-1];

 

p2=[1,-1,3];

 

[p,q]=polyder(p1,p2)
```

## 19、多项式的求值

polyval函数用来求代数多项式的值，其调用格式为：

```bash
y=polyval(p,x)
```

若x为一数值，则求多项式在该点的值；若x为向量，则对向量中的每个元素求其多项式的值。

例： 求多项式在点1，2，3，4的值。

命令如下：

```bash
p=[1,2,1];

 

x=1:4;

 

y=polyval(p,x)

 

y =

 

4 9 16 25
```

## 20、常用的基本数学函数

- abs(x)：纯量的绝对值或向量的长度
- angle(z)：复数z的相角(Phase angle)
- sqrt(x)：开平方
- real(z)：复数z的实部
- imag(z)：复数z的虚部
- conj(z)：复数z的共轭复数
- round(x)：四舍五入至最近整数
- fix(x)：无论正负，舍去小数至最近整数
- floor(x)：地板函数，即舍去正小数至最近整数
- ceil(x)：天花板函数，即加入正小数至最近整数
- rat(x)：将实数x化为分数表示
- rats(x)：将实数x化为多项分数展开
- sign(x)：符号函数 (Signum function)。

> 当x<0时，sign(x)=-1；
>
> 当x=0时，sign(x)=0;
>
> 当x>0时，sign(x)=1。

- rem(x,y)：求x除以y的馀数
- gcd(x,y)：整数x和y的最大公因数
- lcm(x,y)：整数x和y的最小公倍数
- exp(x)：自然指数
- pow2(x)：2的指数
- log(x)：以e为底的对数，即自然对数或
- log2(x)：以2为底的对数
- log10(x)：以10为底的对数

## 21、常用的三角函数

sin(x)：正弦函数

cos(x)：余弦函数

tan(x)：正切函数

asin(x)：反正弦函数

acos(x)：反馀弦函数

atan(x)：反正切函数

atan2(x,y)：四象限的反正切函数

sinh(x)：超越正弦函数

cosh(x)：超越馀弦函数

tanh(x)：超越正切函数

asinh(x)：反超越正弦函数

acosh(x)：反超越馀弦函数

atanh(x)：反超越正切函数

## 22、适用于向量的常用函数

min(x): 向量x的元素的最小值

max(x): 向量x的元素的最大值

mean(x): 向量x的元素的平均值

median(x): 向量x的元素的中位数

std(x): 向量x的元素的标准差

diff(x): 向量x的相邻元素的差

sort(x): 对向量x的元素进行排序（Sorting）

length(x): 向量x的元素个数

norm(x): 向量x的欧氏（Euclidean）长度

sum(x): 向量x的元素总和

prod(x): 向量x的元素总乘积

cumsum(x): 向量x的累计元素总和

cumprod(x): 向量x的累计元素总乘积

dot(x, y): 向量x和y的内积

cross(x, y): 向量x和y的外积

## 23、MATLAB的永久常数

i或j：基本虚数单位（即）

eps：系统的浮点（Floating-point）精确度

inf：无限大， 例如1/0

nan或NaN：非数值（Not a number），例如0/0

pi：圆周率 p（= 3.1415926...）

realmax：系统所能表示的最大数值

realmin：系统所能表示的最小数值

nargin: 函数的输入引数个数

nargout: 函数的输出引数个数

## 24、基本绘图函数

plot: x轴和y轴均为线性刻度（Linear scale）

loglog: x轴和y轴均为对数刻度（Logarithmic scale）

semilogx: x轴为对数刻度，y轴为线性刻度

semilogy: x轴为线性刻度，y轴为对数刻度

## 25、plot绘图函数的参数

| 线型 | 说明       | 标记符 | 说明     | 颜色 | 说明   |
| ---- | ---------- | ------ | -------- | ---- | ------ |
| -    | 实线(默认) | +      | 加号符   | r    | 红色   |
| --   | 双划线     | o      | 空心圆   | g    | 绿色   |
| :    | 虚线       | *      | 星号     | b    | 蓝色   |
| :.   | 点划线     | .      | 实心圆   | c    | 青绿色 |
|      |            | x      | 叉号符   | m    | 洋红色 |
|      |            | s      | 正方形   | y    | 黄色   |
|      |            | d      | 菱形     | k    | 黑色   |
|      |            | ^      | 上三角形 | w    | 白色   |
|      |            | v      | 下三角形 |      |        |
|      |            | >      | 右三角形 |      |        |
|      |            | <      | 左三角形 |      |        |
|      |            | p      | 五角星   |      |        |
|      |            | h      | 六边形   |      |        |

显示详细信息

> 需要说明的是，LineSpec中设置曲线线型、标识符和颜色三项属性时，控制符的顺序不受限制并可以省略或者部分省略。也就是说'r-.*'、'-.r*'、'*-.r'等形式是等效的，都表示使用红色点划线连接各个节点，各节点使用“*”标识。

## 26、注解

xlabel('Input Value'); % x轴注解

ylabel('Function Value'); % y轴注解

title('Two Trigonometric Functions'); % 图形标题

legend('y = sin(x)','y = cos(x)'); % 图形注解

grid on; % 显示格线

## 27、二维绘图函数

bar 长条图

errorbar 图形加上误差范围

fplot 较精确的函数图形

polar 极座标图

hist 累计图

rose 极座标累计图

stairs 阶梯图

stem 针状图

fill 实心图

feather 羽毛图

compass 罗盘图

quiver 向量场图

## 28、特殊变量与常数

ans 计算结果的变量名

computer 确定运行的计算机

eps 浮点相对精度

Inf 无穷大

I 虚数单位

inputname 输入参数名

NaN 非数

nargin 输入参数个数

nargout 输出参数的数目

pi 圆周率

nargoutchk 有效的输出参数数目

realmax 最大正浮点数

realmin 最小正浮点数

varargin 实际输入 的参量

varargout 实际返回的参量

操作符与特殊字符

\+ 加 - 减

\* 矩阵乘法 .* 数组乘（对应元素相乘）

^ 矩阵幂 .^ 数组幂（各个元素求幂）

\ 左除或反斜杠 / 右除或斜面杠

./ 数组除（对应元素除）

kron Kronecker张量积

: 冒号 () 圆括

[] 方括 . 小数点

.. 父目录 ... 继续

, 逗号（分割多条命令） ; 分号（禁止结果显示）

% 注释 ! 感叹号

' 转置或引用 = 赋值

== 相等 <> 不等于

& 逻辑与 | 逻辑或

~ 逻辑非 xor 逻辑异或

## 29、基本矩阵和矩阵操作

blkding 从输入参量建立块对角矩阵

eye 单位矩阵

linespace 产生线性间隔的向量

logspace 产生对数间隔的向量

numel 元素个数

ones 产生全为1的数组

rand 均匀颁随机数和数组

randn 正态分布随机数和数组

zeros 建立一个全0矩阵 colon) 等间隔向量

cat 连接数组

diag 对角矩阵和矩阵对角线

fliplr 从左自右翻转矩阵

flipud 从上到下翻转矩阵

repmat 复制一个数组

reshape 改造矩阵

roy90 矩阵翻转90度

tril 矩阵的下三角

triu 矩阵的上三角

dot 向量点集

cross 向量叉集

ismember 检测一个集合的元素

intersect 向量的交集

setxor 向量异或集

setdiff 向是的差集

union 向量的并集

## 30、数值分析和傅立叶变换

cumprod 累积

cumsum 累加

cumtrapz 累计梯形法计算数值微分

factor 质因子

inpolygon 删除多边形区域内的点

max 最大值

mean 数组的均值

mediam 中值

min 最小值

perms 所有可能的转换

polyarea 多边形区域

primes 生成质数列表

prod 数组元素的乘积

rectint 矩形交集区域

sort 按升序排列矩阵元素

sortrows 按升序排列行

std 标准偏差

sum 求和

trapz 梯形数值积分

var 方差

del2 离散拉普拉斯

diff 差值和微分估计

gradient 数值梯度

cov 协方差矩阵

corrcoef 相关系数

conv2 二维卷积

conv 卷积和多项式乘法

filter IIR或FIR滤波器

deconv 反卷积和多项式除法

filter2 二维数字滤波器

cplxpair 将复数值分类为共轭对

fft 一维的快速傅立叶变换

fft2 二维快速傅立叶变换

fftshift 将FFT的DC分量移到频谱中心

ifft 一维快速反傅立叶变换

ifft2 二维傅立叶反变换

ifftn 多维快速傅立叶变换

ifftshift 反FFT偏移

nextpow2 最靠近的2的幂次

unwrap 校正相位角

## 31、多项式与插值

conv 卷积和多项式乘法

roots 多项式的根

poly 具有设定根的多项式

polyder 多项式微分

polyeig 多项式的特征根

polyfit 多项式拟合

polyint 解析多项式积分

polyval 多项式求值

polyvalm 矩阵变量多项式求值

residue 部分分式展开

interp1 一维插值

interp2 二维插值

interp3 三维插值

interpft 使用FFT的一维插值

interpn 多维插值

meshgrid 为3维点生成x和y的网格

ndgrid 生成多维函数和插值的数组

pchip 分段3次Hermite插值多项式

ppval 分段多项式的值

spline 3次样条数据插值

## 32、绘图函数

bar 竖直条图

barh 水平条图

hist 直方图

histc 直方图计数

hold 保持当前图形

loglog x,y对数坐标图

pie 饼状图

plot 绘二维图

polar 极坐标图

semilogy y轴对数坐标图

semilogx x轴对数坐标

subplot 绘制子图

bar3 数值3D竖条图

bar3h 水平3D条形图

comet3 3D慧星图

cylinder 圆柱体

fill3 填充的3D多边形

plot3 3维空间绘图

quiver3 3D震动（速度）图

slice 体积薄片图

sphere 球

stem3 绘制离散表面数据

waterfall 绘制瀑布

trisurf 三角表面

clabel 增加轮廓标签到等高线图中

datetick 数据格式标记

grid 加网格线

gtext 用鼠标将文本放在2D图中

legend 图注

plotyy 左右边都绘Y轴

title 标题

xlabel X轴标签

ylabel Y轴标签

zlabel Z轴标签

contour 等高线图

contourc 等高线计算

contourf 填充的等高线图

hidden 网格线消影

meshc 连接网格/等高线

mesh 具有参考轴的3D网格

peaks 具有两个变量的采样函数

surf 3D阴影表面图

surface 建立表面低层对象

surfc 海浪和等高线的结合

surfl 具有光照的3D阴影表面

trimesh 三角网格图

## 33、信源函数

randerr 产生比特误差样本

randint 产生均匀分布的随机整数矩阵

randsrc 根据给定的数字表产生随机矩阵

wgn 产生高斯白噪声

信号分析函数

biterr 计算比特误差数和比特误差率

eyediagram 绘制眼图

scatterplot 绘制分布图

symerr 计算符号误差数和符号误差率

## 34、信源编码

compand mu律/A律 压缩/扩张

dpcmdeco DPCM（差分脉冲编码调制）解码

dpcmenco DPCM编码

dpcmopt 优化DPCM参数

lloyds Lloyd法则优化量化器参数

quantiz 给出量化后的级和输出值

## 35、误差控制编码

bchpoly 给出二进制BCH码的性能参数和产生多项式

convenc 产生卷积码

cyclgen 产生[循环码](http://zhidao.baidu.com/search?word=循环码&fr=qb_search_exp&ie=utf8)的[奇偶校验](http://zhidao.baidu.com/search?word=奇偶校验&fr=qb_search_exp&ie=utf8)阵和生成矩阵

cyclpoly 产生[循环码](http://zhidao.baidu.com/search?word=循环码&fr=qb_search_exp&ie=utf8)的生成[多项式](http://zhidao.baidu.com/search?word=多项式&fr=qb_search_exp&ie=utf8)

decode 分组码解码器

encode 分组码[编码器](http://zhidao.baidu.com/search?word=编码器&fr=qb_search_exp&ie=utf8)

gen2par 将[奇偶校验](http://zhidao.baidu.com/search?word=奇偶校验&fr=qb_search_exp&ie=utf8)阵和生成矩阵互相转换

gfweight 计算线性分组码的最小距离

hammgen 产生[汉明码](http://zhidao.baidu.com/search?word=汉明码&fr=qb_search_exp&ie=utf8)的[奇偶校验](http://zhidao.baidu.com/search?word=奇偶校验&fr=qb_search_exp&ie=utf8)阵和生成矩阵

rsdecof 对Reed-Solomon编码的[ASCII文件](http://zhidao.baidu.com/search?word=ASCII文件&fr=qb_search_exp&ie=utf8)解码

rsencof 用Reed-Solomon码对[ASCII文件](http://zhidao.baidu.com/search?word=ASCII文件&fr=qb_search_exp&ie=utf8)编码

rspoly 给出Reed-Solomon码的生成[多项式](http://zhidao.baidu.com/search?word=多项式&fr=qb_search_exp&ie=utf8)

syndtable 产生伴随解码表

vitdec 用Viterbi法则解[卷积码](http://zhidao.baidu.com/search?word=卷积码&fr=qb_search_exp&ie=utf8)

## 36、调制与[解调](http://zhidao.baidu.com/search?word=解调&fr=qb_search_exp&ie=utf8)

ademod 模拟通带[解调器](http://zhidao.baidu.com/search?word=解调器&fr=qb_search_exp&ie=utf8)

ademodce 模拟[基带](http://zhidao.baidu.com/search?word=基带&fr=qb_search_exp&ie=utf8)[解调器](http://zhidao.baidu.com/search?word=解调器&fr=qb_search_exp&ie=utf8)

amod 模拟通带[调制器](http://zhidao.baidu.com/search?word=调制器&fr=qb_search_exp&ie=utf8)

amodce 模拟[基带](http://zhidao.baidu.com/search?word=基带&fr=qb_search_exp&ie=utf8)[调制器](http://zhidao.baidu.com/search?word=调制器&fr=qb_search_exp&ie=utf8)

apkconst 绘制圆形的复合ASK-PSK[星座图](http://zhidao.baidu.com/search?word=星座图&fr=qb_search_exp&ie=utf8)

ddemod 数字通带[解调器](http://zhidao.baidu.com/search?word=解调器&fr=qb_search_exp&ie=utf8)

ddemodce 数字[基带](http://zhidao.baidu.com/search?word=基带&fr=qb_search_exp&ie=utf8)[解调](http://zhidao.baidu.com/search?word=解调&fr=qb_search_exp&ie=utf8)器

dmod 数字通带[调制器](http://zhidao.baidu.com/search?word=调制器&fr=qb_search_exp&ie=utf8)

dmodce 数字基带调制器

modmap 把[数字信号](http://zhidao.baidu.com/search?word=数字信号&fr=qb_search_exp&ie=utf8)映射到[模拟信号](http://zhidao.baidu.com/search?word=模拟信号&fr=qb_search_exp&ie=utf8)[星座图](http://zhidao.baidu.com/search?word=星座图&fr=qb_search_exp&ie=utf8)（以供调制）

qaskdeco 从方形的QASK星座图反映射到[数字信号](http://zhidao.baidu.com/search?word=数字信号&fr=qb_search_exp&ie=utf8)

qaskenco 把数字信号映射到方形的QASK星座图

## 37、专用[滤波器](http://zhidao.baidu.com/search?word=滤波器&fr=qb_search_exp&ie=utf8)

hank2sys 把一个Hankel矩阵转换成一个线性[系统模型](http://zhidao.baidu.com/search?word=系统模型&fr=qb_search_exp&ie=utf8)

hilbiir 设计一个[希尔伯特变换](http://zhidao.baidu.com/search?word=希尔伯特变换&fr=qb_search_exp&ie=utf8)IIR[滤波器](http://zhidao.baidu.com/search?word=滤波器&fr=qb_search_exp&ie=utf8)

rcosflt 升余弦[滤波器](http://zhidao.baidu.com/search?word=滤波器&fr=qb_search_exp&ie=utf8)

rcosine 设计一个升余弦器

## 38、专用滤波器的低级函数

rcosfir 设计一个升余弦[FIR滤波器](http://zhidao.baidu.com/search?word=FIR滤波器&fr=qb_search_exp&ie=utf8)

rcosiir 设计一个升余弦IIR滤波器

## 39、伽罗域计算

gfadd [伽罗](http://zhidao.baidu.com/search?word=伽罗&fr=qb_search_exp&ie=utf8)域上的多项式加法

gfconv [伽罗](http://zhidao.baidu.com/search?word=伽罗&fr=qb_search_exp&ie=utf8)域上的多项式乘法

gfcosets 生成伽罗域的分圆[陪集](http://zhidao.baidu.com/search?word=陪集&fr=qb_search_exp&ie=utf8)

gfdeconv 伽罗域上的[多项式除法](http://zhidao.baidu.com/search?word=多项式除法&fr=qb_search_exp&ie=utf8)

gfdiv 伽罗域上的元素除法

gffilter 在质伽罗域上用多项式过滤数据

gflineq 在至伽罗域上求Ax=b的一个特解

gfminpol 求伽罗域上元素的最小多项式

gfmul 伽罗域上的元素乘法

gfplus GF（2^m）上的元素加法

gfpretty 以通常方式显示多项式

gfprimck 检测多项式是否是基本多项式

gfprimdf 给出伽罗域的MATLAB默认的基本多项式

gfprimfd 给出伽罗域的基本多项式

gfrank 伽罗域上矩阵求秩

gfrepcov GF（2）上多项式的表达方式转换

gfroots 质伽罗域上的多项式求根

gfsub 伽罗域上的多项式[减法](http://zhidao.baidu.com/search?word=减法&fr=qb_search_exp&ie=utf8)

gftrunc 使多项式的表达最简化

gftuple 简化或转换伽罗域上元素的形式

## 40、工具函数

bi2de 把二进制向量转换成[十进制数](http://zhidao.baidu.com/search?word=十进制数&fr=qb_search_exp&ie=utf8)

de2bi 把[十进制数](http://zhidao.baidu.com/search?word=十进制数&fr=qb_search_exp&ie=utf8)转换成二进制向量

erf [误差函数](http://zhidao.baidu.com/search?word=误差函数&fr=qb_search_exp&ie=utf8)

erfc 余[误差函数](http://zhidao.baidu.com/search?word=误差函数&fr=qb_search_exp&ie=utf8)

istrellis 检测输入是否MATLAB的trellis结构（structure）

marcumq 通用Marcum Q 函数

oct2dec [八进制数](http://zhidao.baidu.com/search?word=八进制数&fr=qb_search_exp&ie=utf8)转[十进制数](http://zhidao.baidu.com/search?word=十进制数&fr=qb_search_exp&ie=utf8)

poly2trellis 把[卷积码](http://zhidao.baidu.com/search?word=卷积码&fr=qb_search_exp&ie=utf8)多项式转换成MATLAB的trellis描述

vec2mat 把向量转换成矩阵

——————————————————————————————————————————————————

## A a

abs 绝对值、模、字符的ASCII码值

acos [反余弦](http://zhidao.baidu.com/search?word=反余弦&fr=qb_search_exp&ie=utf8)

acosh 反双曲余弦

acot 反[余切](http://zhidao.baidu.com/search?word=余切&fr=qb_search_exp&ie=utf8)

acoth 反双曲[余切](http://zhidao.baidu.com/search?word=余切&fr=qb_search_exp&ie=utf8)

acsc 反[余割](http://zhidao.baidu.com/search?word=余割&fr=qb_search_exp&ie=utf8)

acsch 反双曲[余割](http://zhidao.baidu.com/search?word=余割&fr=qb_search_exp&ie=utf8)

align 启动图形对象几何位置排列工具

all 所有元素非零为真

angle [相角](http://zhidao.baidu.com/search?word=相角&fr=qb_search_exp&ie=utf8)

ans 表达式计算结果的[缺省](http://zhidao.baidu.com/search?word=缺省&fr=qb_search_exp&ie=utf8)变量名

any 所有元素非全零为真

area 面域图

argnames 函数M文件宗量名

asec 反正割

asech 反双曲正割

asin [反正弦](http://zhidao.baidu.com/search?word=反正弦&fr=qb_search_exp&ie=utf8)

asinh 反双曲正弦

assignin 向变量赋值

atan 反正切

[atan2](http://zhidao.baidu.com/search?word=atan2&fr=qb_search_exp&ie=utf8) [四象限](http://zhidao.baidu.com/search?word=四象限&fr=qb_search_exp&ie=utf8)反正切

atanh 反双曲正切

autumn 红黄调秋色图阵

axes 创建轴对象的低层指令

axis 控制轴刻度和风格的高层指令

## B b

bar 二维[直方图](http://zhidao.baidu.com/search?word=直方图&fr=qb_search_exp&ie=utf8)

bar3 三维[直方图](http://zhidao.baidu.com/search?word=直方图&fr=qb_search_exp&ie=utf8)

bar3h 三维水平[直方图](http://zhidao.baidu.com/search?word=直方图&fr=qb_search_exp&ie=utf8)

barh 二维水平直方图

base2dec X[进制转换](http://zhidao.baidu.com/search?word=进制转换&fr=qb_search_exp&ie=utf8)为[十进制](http://zhidao.baidu.com/search?word=十进制&fr=qb_search_exp&ie=utf8)

bin2dec [二进制转换](http://zhidao.baidu.com/search?word=二进制转换&fr=qb_search_exp&ie=utf8)为[十进制](http://zhidao.baidu.com/search?word=十进制&fr=qb_search_exp&ie=utf8)

blanks 创建空格串

bone 蓝色调黑白色图阵

box 框状[坐标轴](http://zhidao.baidu.com/search?word=坐标轴&fr=qb_search_exp&ie=utf8)

break while 或for 环中断指令

brighten 亮度控制

## C c

capture （3版以前）捕获当前图形

cart2pol [直角坐标](http://zhidao.baidu.com/search?word=直角坐标&fr=qb_search_exp&ie=utf8)变为极或柱坐标

cart2sph [直角坐标](http://zhidao.baidu.com/search?word=直角坐标&fr=qb_search_exp&ie=utf8)变为球坐标

cat 串接成高[维数](http://zhidao.baidu.com/search?word=维数&fr=qb_search_exp&ie=utf8)组

caxis 色[标尺](http://zhidao.baidu.com/search?word=标尺&fr=qb_search_exp&ie=utf8)刻度

cd 指定当前目录

cdedit 启动用户菜单、控件[回调函数](http://zhidao.baidu.com/search?word=回调函数&fr=qb_search_exp&ie=utf8)设计工具

cdf2rdf 复数[特征值](http://zhidao.baidu.com/search?word=特征值&fr=qb_search_exp&ie=utf8)[对角阵](http://zhidao.baidu.com/search?word=对角阵&fr=qb_search_exp&ie=utf8)转为实数块[对角阵](http://zhidao.baidu.com/search?word=对角阵&fr=qb_search_exp&ie=utf8)

ceil 向[正无穷](http://zhidao.baidu.com/search?word=正无穷&fr=qb_search_exp&ie=utf8)取整

cell 创建[元胞数组](http://zhidao.baidu.com/search?word=元胞数组&fr=qb_search_exp&ie=utf8)

cell2struct [元胞数组](http://zhidao.baidu.com/search?word=元胞数组&fr=qb_search_exp&ie=utf8)转换为构架数组

celldisp 显示[元胞数组](http://zhidao.baidu.com/search?word=元胞数组&fr=qb_search_exp&ie=utf8)内容

cellplot 元胞数组内部[结构图](http://zhidao.baidu.com/search?word=结构图&fr=qb_search_exp&ie=utf8)示

char 把数值、符号、内联类转换为字符对象

chi2cdf 分布累计概率函数

chi2inv 分布逆累计概率函数

chi2pdf 分布[概率密度函数](http://zhidao.baidu.com/search?word=概率密度函数&fr=qb_search_exp&ie=utf8)

chi2rnd 分布[随机数](http://zhidao.baidu.com/search?word=随机数&fr=qb_search_exp&ie=utf8)发生器

chol Cholesky分解

clabel [等位线](http://zhidao.baidu.com/search?word=等位线&fr=qb_search_exp&ie=utf8)标识

cla 清除当前轴

class 获知对象类别或创建对象

clc 清除指令窗

clear 清除[内存变量](http://zhidao.baidu.com/search?word=内存变量&fr=qb_search_exp&ie=utf8)和函数

clf 清除图对象

clock 时钟

colorcube 三浓淡多彩交叉色图矩阵

colordef 设置色彩[缺省值](http://zhidao.baidu.com/search?word=缺省值&fr=qb_search_exp&ie=utf8)

colormap 色图

colspace 列空间的基

close 关闭指定窗口

colperm 列排序置换向量

comet 彗星状轨迹图

comet3 三维彗星轨迹图

compass 射线图

compose 求[复合函数](http://zhidao.baidu.com/search?word=复合函数&fr=qb_search_exp&ie=utf8)

cond （逆）[条件数](http://zhidao.baidu.com/search?word=条件数&fr=qb_search_exp&ie=utf8)

condeig 计算[特征值](http://zhidao.baidu.com/search?word=特征值&fr=qb_search_exp&ie=utf8)、[特征向量](http://zhidao.baidu.com/search?word=特征向量&fr=qb_search_exp&ie=utf8)同时给出[条件数](http://zhidao.baidu.com/search?word=条件数&fr=qb_search_exp&ie=utf8)

condest 范 -1[条件数](http://zhidao.baidu.com/search?word=条件数&fr=qb_search_exp&ie=utf8)估计

conj 复数[共轭](http://zhidao.baidu.com/search?word=共轭&fr=qb_search_exp&ie=utf8)

contour [等位线](http://zhidao.baidu.com/search?word=等位线&fr=qb_search_exp&ie=utf8)

contourf 填色[等位线](http://zhidao.baidu.com/search?word=等位线&fr=qb_search_exp&ie=utf8)

contour3 三维等位线

contourslice [四维](http://zhidao.baidu.com/search?word=四维&fr=qb_search_exp&ie=utf8)切片等位线图

conv 多项式乘、卷积

cool 青紫调[冷色](http://zhidao.baidu.com/search?word=冷色&fr=qb_search_exp&ie=utf8)图

copper [古铜](http://zhidao.baidu.com/search?word=古铜&fr=qb_search_exp&ie=utf8)调色图

cos 余弦

cosh 双曲余弦

cot [余切](http://zhidao.baidu.com/search?word=余切&fr=qb_search_exp&ie=utf8)

coth 双曲余切

cplxpair 复数[共轭](http://zhidao.baidu.com/search?word=共轭&fr=qb_search_exp&ie=utf8)成对排列

csc [余割](http://zhidao.baidu.com/search?word=余割&fr=qb_search_exp&ie=utf8)

csch 双曲余割

cumsum 元素累计和

cumtrapz 累计梯形积分

cylinder 创建圆柱

## D d

dblquad 二重[数值积分](http://zhidao.baidu.com/search?word=数值积分&fr=qb_search_exp&ie=utf8)

deal 分配宗量

deblank 删去串尾部的[空格符](http://zhidao.baidu.com/search?word=空格符&fr=qb_search_exp&ie=utf8)

dec2base 十[进制转换](http://zhidao.baidu.com/search?word=进制转换&fr=qb_search_exp&ie=utf8)为X进制

[dec2bin](http://zhidao.baidu.com/search?word=dec2bin&fr=qb_search_exp&ie=utf8) 十[进制转换](http://zhidao.baidu.com/search?word=进制转换&fr=qb_search_exp&ie=utf8)为二进制

dec2hex [十进制](http://zhidao.baidu.com/search?word=十进制&fr=qb_search_exp&ie=utf8)转换为[十六进制](http://zhidao.baidu.com/search?word=十六进制&fr=qb_search_exp&ie=utf8)

deconv 多项式除、解卷

delaunay Delaunay [三角剖分](http://zhidao.baidu.com/search?word=三角剖分&fr=qb_search_exp&ie=utf8)

del2 离散Laplacian差分

demo Matlab演示

det [行列式](http://zhidao.baidu.com/search?word=行列式&fr=qb_search_exp&ie=utf8)

diag 矩阵对角元素提取、创建[对角阵](http://zhidao.baidu.com/search?word=对角阵&fr=qb_search_exp&ie=utf8)

diary Matlab指令窗文本内容记录

diff 数值差分、符号[微分](http://zhidao.baidu.com/search?word=微分&fr=qb_search_exp&ie=utf8)

digits [符号计算](http://zhidao.baidu.com/search?word=符号计算&fr=qb_search_exp&ie=utf8)中设置符号数值的精度

dir 目录列表

disp 显示数组

display 显示对象内容的[重载函数](http://zhidao.baidu.com/search?word=重载函数&fr=qb_search_exp&ie=utf8)

dlinmod [离散系统](http://zhidao.baidu.com/search?word=离散系统&fr=qb_search_exp&ie=utf8)的[线性化](http://zhidao.baidu.com/search?word=线性化&fr=qb_search_exp&ie=utf8)模型

dmperm 矩阵Dulmage-Mendelsohn 分解

dos 执行DOS 指令并返回结果

double 把其他类型对象转换为双精度数值

drawnow 更新事件[队列](http://zhidao.baidu.com/search?word=队列&fr=qb_search_exp&ie=utf8)强迫Matlab刷新屏幕

dsolve [符号计算](http://zhidao.baidu.com/search?word=符号计算&fr=qb_search_exp&ie=utf8)解[微分方程](http://zhidao.baidu.com/search?word=微分方程&fr=qb_search_exp&ie=utf8)

## E e

echo M文件被执行指令的显示

edit 启动M文件编辑器

eig 求[特征值](http://zhidao.baidu.com/search?word=特征值&fr=qb_search_exp&ie=utf8)和[特征向量](http://zhidao.baidu.com/search?word=特征向量&fr=qb_search_exp&ie=utf8)

eigs 求指定的几个特征值

end [控制流](http://zhidao.baidu.com/search?word=控制流&fr=qb_search_exp&ie=utf8)FOR等[结构体](http://zhidao.baidu.com/search?word=结构体&fr=qb_search_exp&ie=utf8)的结尾元素下标

eps [浮点](http://zhidao.baidu.com/search?word=浮点&fr=qb_search_exp&ie=utf8)相对精度

error 显示出错信息并中断执行

errortrap 错误发生后程序是否继续执行的控制

erf [误差函数](http://zhidao.baidu.com/search?word=误差函数&fr=qb_search_exp&ie=utf8)

erfc 误差补函数

erfcx 刻度误差补函数

erfinv 逆误差函数

errorbar 带误差限的曲线图

etreeplot 画消去树

eval 串演算指令

evalin 跨空间串演算指令

exist 检查变量或函数是否已定义

exit 退出Matlab环境

exp [指数函数](http://zhidao.baidu.com/search?word=指数函数&fr=qb_search_exp&ie=utf8)

expand [符号计算](http://zhidao.baidu.com/search?word=符号计算&fr=qb_search_exp&ie=utf8)中的展开操作

expint [指数积分](http://zhidao.baidu.com/search?word=指数积分&fr=qb_search_exp&ie=utf8)函数

expm 常用矩阵[指数函数](http://zhidao.baidu.com/search?word=指数函数&fr=qb_search_exp&ie=utf8)

expm1 Pade法求矩阵指数

expm2 Taylor法求矩阵指数

expm3 特征值分解法求矩阵指数

eye [单位阵](http://zhidao.baidu.com/search?word=单位阵&fr=qb_search_exp&ie=utf8)

ezcontour 画等位线的简捷指令

ezcontourf 画填色等位线的简捷指令

ezgraph3 画表面图的通用简捷指令

ezmesh 画网线图的简捷指令

ezmeshc 画带等位线的网线图的简捷指令

ezplot 画二维曲线的简捷指令

ezplot3 画三维曲线的简捷指令

ezpolar 画[极坐标](http://zhidao.baidu.com/search?word=极坐标&fr=qb_search_exp&ie=utf8)图的简捷指令

ezsurf 画表面图的简捷指令

ezsurfc 画带等位线的表面图的简捷指令

## F f

factor 符号计算的[因式分解](http://zhidao.baidu.com/search?word=因式分解&fr=qb_search_exp&ie=utf8)

feather 羽毛图

feedback 反馈连接

feval 执行由串指定的函数

fft 离散Fourier变换

fft2 二维离散Fourier变换

fftn 高维离散Fourier变换

fftshift [直流分量](http://zhidao.baidu.com/search?word=直流分量&fr=qb_search_exp&ie=utf8)对中的谱

fieldnames 构架域名

figure 创建图形窗

fill3 三维[多边形](http://zhidao.baidu.com/search?word=多边形&fr=qb_search_exp&ie=utf8)填色图

find 寻找非零元素下标

findobj 寻找具有指定属性的[对象图](http://zhidao.baidu.com/search?word=对象图&fr=qb_search_exp&ie=utf8)柄

findstr 寻找短串的起始字符下标

findsym 机器确定内存中的符号变量

finverse 符号计算中求[反函数](http://zhidao.baidu.com/search?word=反函数&fr=qb_search_exp&ie=utf8)

fix 向零取整

flag [红白蓝](http://zhidao.baidu.com/search?word=红白蓝&fr=qb_search_exp&ie=utf8)黑交错色图阵

fliplr 矩阵的左右翻转

flipud 矩阵的上下翻转

flipdim 矩阵沿指定维翻转

floor 向负无穷取整

flops [浮点运算](http://zhidao.baidu.com/search?word=浮点运算&fr=qb_search_exp&ie=utf8)次数

flow Matlab提供的演示数据

fmin 求单变量非[线性函数](http://zhidao.baidu.com/search?word=线性函数&fr=qb_search_exp&ie=utf8)极小值点（旧版）

fminbnd 求单变量非[线性函数](http://zhidao.baidu.com/search?word=线性函数&fr=qb_search_exp&ie=utf8)极小值点

fmins [单纯形法](http://zhidao.baidu.com/search?word=单纯形法&fr=qb_search_exp&ie=utf8)求多变量函数极小值点（旧版）

fminunc [拟牛顿法](http://zhidao.baidu.com/search?word=拟牛顿法&fr=qb_search_exp&ie=utf8)求多变量函数极小值点

fminsearch [单纯形法](http://zhidao.baidu.com/search?word=单纯形法&fr=qb_search_exp&ie=utf8)求多变量函数极小值点

fnder 对[样条函数](http://zhidao.baidu.com/search?word=样条函数&fr=qb_search_exp&ie=utf8)求导

fnint 利用[样条函数](http://zhidao.baidu.com/search?word=样条函数&fr=qb_search_exp&ie=utf8)求积分

fnval 计算[样条函数](http://zhidao.baidu.com/search?word=样条函数&fr=qb_search_exp&ie=utf8)区间内任意一点的值

fnplt 绘制样条函数图形

fopen 打开外部文件

for 构成for环用

format 设置输出格式

fourier Fourier 变换

fplot 返函绘图指令

fprintf 设置显示格式

fread 从文件读[二进制数](http://zhidao.baidu.com/search?word=二进制数&fr=qb_search_exp&ie=utf8)据

fsolve 求[多元函数](http://zhidao.baidu.com/search?word=多元函数&fr=qb_search_exp&ie=utf8)的零点

full 把[稀疏矩阵](http://zhidao.baidu.com/search?word=稀疏矩阵&fr=qb_search_exp&ie=utf8)转换为非稀疏阵

funm 计算一般[矩阵函数](http://zhidao.baidu.com/search?word=矩阵函数&fr=qb_search_exp&ie=utf8)

funtool 函数计算器[图形用户界面](http://zhidao.baidu.com/search?word=图形用户界面&fr=qb_search_exp&ie=utf8)

fzero 求单变量非[线性函数](http://zhidao.baidu.com/search?word=线性函数&fr=qb_search_exp&ie=utf8)的零点

## G g

gamma 函数

gammainc 不完全 函数

gammaln 函数的对数

gca 获得当前轴[句柄](http://zhidao.baidu.com/search?word=句柄&fr=qb_search_exp&ie=utf8)

gcbo 获得正执行"回调"的对象[句柄](http://zhidao.baidu.com/search?word=句柄&fr=qb_search_exp&ie=utf8)

gcf 获得当前图对象[句柄](http://zhidao.baidu.com/search?word=句柄&fr=qb_search_exp&ie=utf8)

gco 获得当前对象句柄

geomean [几何平均值](http://zhidao.baidu.com/search?word=几何平均值&fr=qb_search_exp&ie=utf8)

get 获知对象属性

getfield 获知构架数组的域

getframe 获取影片的帧画面

ginput 从图形窗获取数据

global 定义[全局变量](http://zhidao.baidu.com/search?word=全局变量&fr=qb_search_exp&ie=utf8)

gplot 依[图论](http://zhidao.baidu.com/search?word=图论&fr=qb_search_exp&ie=utf8)法则画图

gradient 近似[梯度](http://zhidao.baidu.com/search?word=梯度&fr=qb_search_exp&ie=utf8)

gray [黑白灰](http://zhidao.baidu.com/search?word=黑白灰&fr=qb_search_exp&ie=utf8)度

grid 画分格线

griddata 规则化数据和[曲面](http://zhidao.baidu.com/search?word=曲面&fr=qb_search_exp&ie=utf8)[拟合](http://zhidao.baidu.com/search?word=拟合&fr=qb_search_exp&ie=utf8)

gtext 由鼠标放置注释文字

guide 启动[图形用户界面](http://zhidao.baidu.com/search?word=图形用户界面&fr=qb_search_exp&ie=utf8)[交互设计](http://zhidao.baidu.com/search?word=交互设计&fr=qb_search_exp&ie=utf8)工具

## H h

harmmean [调和平均值](http://zhidao.baidu.com/search?word=调和平均值&fr=qb_search_exp&ie=utf8)

help 在线帮助

helpwin 交互式在线帮助

helpdesk 打开超[文本形式](http://zhidao.baidu.com/search?word=文本形式&fr=qb_search_exp&ie=utf8)用户指南

hex2dec [十六进制转换](http://zhidao.baidu.com/search?word=十六进制转换&fr=qb_search_exp&ie=utf8)为十进制

hex2num [十六进制转换](http://zhidao.baidu.com/search?word=十六进制转换&fr=qb_search_exp&ie=utf8)为[浮点数](http://zhidao.baidu.com/search?word=浮点数&fr=qb_search_exp&ie=utf8)

hidden 透视和消隐开关

hilb Hilbert矩阵

hist [频数](http://zhidao.baidu.com/search?word=频数&fr=qb_search_exp&ie=utf8)计算或[频数](http://zhidao.baidu.com/search?word=频数&fr=qb_search_exp&ie=utf8)直方图

histc 端点定位[频数](http://zhidao.baidu.com/search?word=频数&fr=qb_search_exp&ie=utf8)直方图

histfit 带正态[拟合](http://zhidao.baidu.com/search?word=拟合&fr=qb_search_exp&ie=utf8)的频数直方图

hold 当前图上重画的切换开关

horner 分解成嵌套形式

hot 黑红黄白色图

hsv 饱和色图

## I i

if-else-elseif 条件[分支结构](http://zhidao.baidu.com/search?word=分支结构&fr=qb_search_exp&ie=utf8)

ifft 离散Fourier反变换

ifft2 二维离散Fourier反变换

ifftn 高维离散Fourier反变换

ifftshift [直流分量](http://zhidao.baidu.com/search?word=直流分量&fr=qb_search_exp&ie=utf8)对中的谱的反操作

ifourier Fourier反变换

i, j [缺省](http://zhidao.baidu.com/search?word=缺省&fr=qb_search_exp&ie=utf8)的"虚单元"变量

ilaplace Laplace反变换

imag 复数虚部

image 显示图象

imagesc 显示亮度图象

imfinfo 获取图形文件信息

imread 从文件读取图象

imwrite 把imwrite 把图象写成文件

[ind2sub](http://zhidao.baidu.com/search?word=ind2sub&fr=qb_search_exp&ie=utf8) 单下标转变为多下标

inf [无穷大](http://zhidao.baidu.com/search?word=无穷大&fr=qb_search_exp&ie=utf8)

info MathWorks公司网点地址

inline 构造[内联函数](http://zhidao.baidu.com/search?word=内联函数&fr=qb_search_exp&ie=utf8)对象

inmem 列出内存中的函数名

input 提示用户输入

inputname 输入宗量名

int 符号积分

[int2str](http://zhidao.baidu.com/search?word=int2str&fr=qb_search_exp&ie=utf8) 把整数数组转换为串数组

interp1 一维[插值](http://zhidao.baidu.com/search?word=插值&fr=qb_search_exp&ie=utf8)

interp2 二维[插值](http://zhidao.baidu.com/search?word=插值&fr=qb_search_exp&ie=utf8)

interp3 三维[插值](http://zhidao.baidu.com/search?word=插值&fr=qb_search_exp&ie=utf8)

interpn N维插值

interpft 利用FFT插值

intro Matlab自带的入门引导

inv 求矩阵逆

invhilb Hilbert矩阵的准确逆

ipermute 广义反转置

isa 检测是否给定类的对象

ischar 若是字符串则为真

isequal 若两数组相同则为真

isempty 若是空阵则为真

isfinite 若全部元素都有限则为真

isfield 若是构架域则为真

isglobal 若是[全局变量](http://zhidao.baidu.com/search?word=全局变量&fr=qb_search_exp&ie=utf8)则为真

ishandle 若是图形句柄则为真

ishold 若当前图形处于保留状态则为真

isieee 若计算机执行IEEE规则则为真

isinf 若是无穷数据则为真

isletter 若是英文字母则为真

islogical 若是逻辑数组则为真

ismember 检查是否属于指定集

isnan 若是非数则为真

isnumeric 若是数值数组则为真

isobject 若是对象则为真

isprime 若是[质数](http://zhidao.baidu.com/search?word=质数&fr=qb_search_exp&ie=utf8)则为真

isreal 若是实数则为真

isspace 若是空格则为真

issparse 若是[稀疏矩阵](http://zhidao.baidu.com/search?word=稀疏矩阵&fr=qb_search_exp&ie=utf8)则为真

isstruct 若是构架则为真

isstudent 若是Matlab学生版则为真

iztrans 符号计算Z反变换

## J j , K k

jacobian 符号计算中求Jacobian 矩阵

jet 蓝头红尾饱和色

jordan 符号计算中获得 [Jordan标准型](http://zhidao.baidu.com/search?word=Jordan标准型&fr=qb_search_exp&ie=utf8)

keyboard 键盘获得控制权

kron Kronecker乘法规则产生的数组

## L l

laplace Laplace变换

lasterr 显示最新出错信息

lastwarn 显示最新警告信息

leastsq 解[非线性](http://zhidao.baidu.com/search?word=非线性&fr=qb_search_exp&ie=utf8)最小二乘问题（旧版）

legend 图形[图例](http://zhidao.baidu.com/search?word=图例&fr=qb_search_exp&ie=utf8)

lighting 照明模式

line 创建线对象

lines 采用plot 画线色

linmod 获连续系统的[线性化](http://zhidao.baidu.com/search?word=线性化&fr=qb_search_exp&ie=utf8)模型

linmod2 获连续系统的[线性化](http://zhidao.baidu.com/search?word=线性化&fr=qb_search_exp&ie=utf8)精良模型

linspace 线性等分向量

ln 矩阵[自然对数](http://zhidao.baidu.com/search?word=自然对数&fr=qb_search_exp&ie=utf8)

load 从MAT文件读取变量

log [自然对数](http://zhidao.baidu.com/search?word=自然对数&fr=qb_search_exp&ie=utf8)

[log10](http://zhidao.baidu.com/search?word=log10&fr=qb_search_exp&ie=utf8) [常用对数](http://zhidao.baidu.com/search?word=常用对数&fr=qb_search_exp&ie=utf8)

log2 底为2的对数

loglog 双对数刻度图形

logm 矩阵对数

logspace 对数分度向量

lookfor 按关键字搜索M文件

lower 转换为[小写字母](http://zhidao.baidu.com/search?word=小写字母&fr=qb_search_exp&ie=utf8)

lsqnonlin 解[非线性](http://zhidao.baidu.com/search?word=非线性&fr=qb_search_exp&ie=utf8)最小二乘问题

lu LU分解

## M m

mad 平均绝对值偏差

magic [魔方阵](http://zhidao.baidu.com/search?word=魔方阵&fr=qb_search_exp&ie=utf8)

maple &nb, sp; 运作 Maple格式指令

mat2str 把数值数组转换成输入形态串数组

material 材料反射模式

max 找向量中最大元素

mbuild 产生EXE文件编译环境的预设置指令

mcc 创建MEX或EXE文件的编译指令

mean 求向量元素的平均值

median 求[中位数](http://zhidao.baidu.com/search?word=中位数&fr=qb_search_exp&ie=utf8)

menuedit 启动设计用户菜单的交互式编辑工具

mesh 网线图

meshz [垂帘](http://zhidao.baidu.com/search?word=垂帘&fr=qb_search_exp&ie=utf8)网线图

meshgrid 产生"格点"矩阵

methods 获知对指定类定义的所有方法函数

mex 产生MEX文件编译环境的预设置指令

mfunlis 能被mfun计算的MAPLE经典函数列表

mhelp 引出 Maple的在线帮助

min 找向量中最小元素

mkdir 创建目录

mkpp 逐段多项式数据的明晰化

mod [模运算](http://zhidao.baidu.com/search?word=模运算&fr=qb_search_exp&ie=utf8)

more 指令窗中内容的分页显示

movie 放映影片动画

moviein 影片帧画面的内存预置

mtaylor 符号计算多变量Taylor级数展开

## N n

ndims 求数组[维数](http://zhidao.baidu.com/search?word=维数&fr=qb_search_exp&ie=utf8)

NaN 非数（预定义）变量

nargchk 输入宗量数验证

nargin 函数输入宗量数

nargout 函数输出宗量数

ndgrid 产生高维格点矩阵

newplot 准备新的[缺省](http://zhidao.baidu.com/search?word=缺省&fr=qb_search_exp&ie=utf8)图、轴

nextpow2 取最接近的较大2次幂

nnz 矩阵的非零元素总数

nonzeros 矩阵的非零元素

norm 矩阵或[向量范数](http://zhidao.baidu.com/search?word=向量范数&fr=qb_search_exp&ie=utf8)

normcdf [正态分布](http://zhidao.baidu.com/search?word=正态分布&fr=qb_search_exp&ie=utf8)累计[概率密度函数](http://zhidao.baidu.com/search?word=概率密度函数&fr=qb_search_exp&ie=utf8)

normest 估计矩阵2[范数](http://zhidao.baidu.com/search?word=范数&fr=qb_search_exp&ie=utf8)

norminv [正态分布](http://zhidao.baidu.com/search?word=正态分布&fr=qb_search_exp&ie=utf8)逆累计[概率密度函数](http://zhidao.baidu.com/search?word=概率密度函数&fr=qb_search_exp&ie=utf8)

normpdf [正态分布](http://zhidao.baidu.com/search?word=正态分布&fr=qb_search_exp&ie=utf8)[概率密度](http://zhidao.baidu.com/search?word=概率密度&fr=qb_search_exp&ie=utf8)函数

normrnd 正态[随机数](http://zhidao.baidu.com/search?word=随机数&fr=qb_search_exp&ie=utf8)发生器

notebook 启动Matlab和Word的集成环境

null [零空间](http://zhidao.baidu.com/search?word=零空间&fr=qb_search_exp&ie=utf8)

[num2str](http://zhidao.baidu.com/search?word=num2str&fr=qb_search_exp&ie=utf8) 把非整数数组转换为串

numden 获取最小[公分母](http://zhidao.baidu.com/search?word=公分母&fr=qb_search_exp&ie=utf8)和相应的分子表达式

nzmax 指定存放非零元素所需内存

## O o

ode1 非Stiff [微分方程](http://zhidao.baidu.com/search?word=微分方程&fr=qb_search_exp&ie=utf8)变步长解算器

ode15s Stiff [微分方程](http://zhidao.baidu.com/search?word=微分方程&fr=qb_search_exp&ie=utf8)变步长解算器

ode23t 适度Stiff [微分](http://zhidao.baidu.com/search?word=微分&fr=qb_search_exp&ie=utf8)方程解算器

ode23tb Stiff [微分](http://zhidao.baidu.com/search?word=微分&fr=qb_search_exp&ie=utf8)方程解算器

[ode45](http://zhidao.baidu.com/search?word=ode45&fr=qb_search_exp&ie=utf8) 非Stiff 微分方程变步长解算器

odefile ODE 文件模板

odeget 获知ODE 选项设置参数

odephas2 ODE 输出函数的二维相[平面图](http://zhidao.baidu.com/search?word=平面图&fr=qb_search_exp&ie=utf8)

odephas3 ODE 输出函数的三维[相空间](http://zhidao.baidu.com/search?word=相空间&fr=qb_search_exp&ie=utf8)图

odeplot ODE 输出函数的时间轨迹图

odeprint 在Matlab指令窗显示结果

odeset 创建或改写 ODE选项构架参数值

ones 全1数组

optimset 创建或改写优化[泛函](http://zhidao.baidu.com/search?word=泛函&fr=qb_search_exp&ie=utf8)指令的选项参数值

orient 设定图形的排放方式

orth 值空间正交化

## P p

pack 收集Matlab内存碎块扩大内存

pagedlg 调出图形排版对话框

patch 创建块对象

path 设置Matlab搜索路径的指令

pathtool 搜索路径管理器

pause 暂停

pcode 创建预解译P码文件

pcolor 伪彩图

peaks Matlab提供的典型三维[曲面](http://zhidao.baidu.com/search?word=曲面&fr=qb_search_exp&ie=utf8)

permute 广义转置

pi （预定义变量）[圆周率](http://zhidao.baidu.com/search?word=圆周率&fr=qb_search_exp&ie=utf8)

pie 二维饼图

pie3 三维饼图

pink 粉红色图矩阵

pinv 伪逆

plot 平面线图

plot3 三维线图

plotmatrix 矩阵的[散点图](http://zhidao.baidu.com/search?word=散点图&fr=qb_search_exp&ie=utf8)

plotyy 双纵坐标图

poissinv [泊松分布](http://zhidao.baidu.com/search?word=泊松分布&fr=qb_search_exp&ie=utf8)逆累计[概率分布函数](http://zhidao.baidu.com/search?word=概率分布函数&fr=qb_search_exp&ie=utf8)

poissrnd [泊松分布](http://zhidao.baidu.com/search?word=泊松分布&fr=qb_search_exp&ie=utf8)[随机数](http://zhidao.baidu.com/search?word=随机数&fr=qb_search_exp&ie=utf8)发生器

pol2cart 极或柱坐标变为[直角坐标](http://zhidao.baidu.com/search?word=直角坐标&fr=qb_search_exp&ie=utf8)

polar [极坐标](http://zhidao.baidu.com/search?word=极坐标&fr=qb_search_exp&ie=utf8)图

poly 矩阵的[特征多项式](http://zhidao.baidu.com/search?word=特征多项式&fr=qb_search_exp&ie=utf8)、根集对应的多项式

poly2str 以习惯方式显示多项式

poly2sym 双精度多项式系数转变为[向量符号](http://zhidao.baidu.com/search?word=向量符号&fr=qb_search_exp&ie=utf8)多项式

polyder 多项式导数

polyfit 数据的多项式[拟合](http://zhidao.baidu.com/search?word=拟合&fr=qb_search_exp&ie=utf8)

polyval 计算多项式的值

polyvalm 计算矩阵多项式

pow2 2的幂

ppval 计算分段多项式

pretty 以习惯方式显示[符号表](http://zhidao.baidu.com/search?word=符号表&fr=qb_search_exp&ie=utf8)达式

print 打印图形或SIMULINK模型

printsys 以习惯方式显示有理[分式](http://zhidao.baidu.com/search?word=分式&fr=qb_search_exp&ie=utf8)

prism [光谱](http://zhidao.baidu.com/search?word=光谱&fr=qb_search_exp&ie=utf8)色图矩阵

procread 向MAPLE输送计算程序

profile 函数文件性能评估器

propedit 图形对象属性编辑器

pwd 显示当前工作目录

## Q q

quad 低阶法计算[数值积分](http://zhidao.baidu.com/search?word=数值积分&fr=qb_search_exp&ie=utf8)

quad8 高阶法计算[数值积分](http://zhidao.baidu.com/search?word=数值积分&fr=qb_search_exp&ie=utf8)(QUADL)

quit 推出Matlab 环境

quiver 二维方向箭头图

quiver3 三维方向箭头图

## R r

rand 产生[均匀分布](http://zhidao.baidu.com/search?word=均匀分布&fr=qb_search_exp&ie=utf8)随机数

randn 产生正态分布随机数

randperm 随机置换向量

range 样本[极差](http://zhidao.baidu.com/search?word=极差&fr=qb_search_exp&ie=utf8)

rank [矩阵的秩](http://zhidao.baidu.com/search?word=矩阵的秩&fr=qb_search_exp&ie=utf8)

rats 有理输出

rcond 矩阵倒条件数估计

real 复数的实部

reallog 在实数域内计算[自然对数](http://zhidao.baidu.com/search?word=自然对数&fr=qb_search_exp&ie=utf8)

realpow 在实数域内计算[乘方](http://zhidao.baidu.com/search?word=乘方&fr=qb_search_exp&ie=utf8)

realsqrt 在实数域内计算[平方根](http://zhidao.baidu.com/search?word=平方根&fr=qb_search_exp&ie=utf8)

realmax 最大正[浮点数](http://zhidao.baidu.com/search?word=浮点数&fr=qb_search_exp&ie=utf8)

realmin 最小正[浮点数](http://zhidao.baidu.com/search?word=浮点数&fr=qb_search_exp&ie=utf8)

rectangle 画"长方框"

rem 求余数

repmat 铺放模块数组

reshape 改变数组[维数](http://zhidao.baidu.com/search?word=维数&fr=qb_search_exp&ie=utf8)、大小

residue [部分分式](http://zhidao.baidu.com/search?word=部分分式&fr=qb_search_exp&ie=utf8)展开

return 返回

ribbon 把二维曲线画成三维彩带图

rmfield 删去构架的域

roots 求多项式的根

rose 数[扇形图](http://zhidao.baidu.com/search?word=扇形图&fr=qb_search_exp&ie=utf8)

[rot90](http://zhidao.baidu.com/search?word=rot90&fr=qb_search_exp&ie=utf8) 矩阵旋转90度

rotate 指定的原点和方向旋转

rotate3d 启动[三维图形](http://zhidao.baidu.com/search?word=三维图形&fr=qb_search_exp&ie=utf8)视角的交互设置功能

round 向最近整数圆整

rref 简化矩阵为梯形形式

rsf2csf 实数块对角阵转为复数特征值对角阵

rsums Riemann

## S s

save 把[内存变量](http://zhidao.baidu.com/search?word=内存变量&fr=qb_search_exp&ie=utf8)保存为文件

scatter [散点图](http://zhidao.baidu.com/search?word=散点图&fr=qb_search_exp&ie=utf8)

scatter3 三维[散点图](http://zhidao.baidu.com/search?word=散点图&fr=qb_search_exp&ie=utf8)

sec 正割

sech 双曲正割

semilogx X轴对数刻度坐标图

semilogy Y轴对数刻度坐标图

series 串联连接

set 设置图形对象属性

setfield 设置构架数组的域

setstr 将ASCII码转换为字符的旧版指令

sign 根据符号取值函数

signum 符号计算中的符号取值函数

sim 运行SIMULINK模型

simget 获取SIMULINK模型设置的仿真参数

simple 寻找最短形式的符号解

simplify 符号计算中进行简化操作

simset 对SIMULINK模型的仿真参数进行设置

simulink 启动SIMULINK模块库浏览器

sin 正弦

sinh 双曲正弦

size 矩阵的大小