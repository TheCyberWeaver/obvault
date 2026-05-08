# 积分题解：
$$\int \frac{1}{1+x^6}\,dx$$

## 题目
求
$$
I=\int \frac{1}{1+x^6}\,dx
$$

---

## 思路总览
核心是把分母拆开：

$$
1+x^6=(x^2+1)(x^4-x^2+1)
$$

然后利用
$$
\frac{1}{1+x^6}
=
\frac{1}{x^2+1}
-
\frac{x^2}{1+x^6}
$$

把原积分拆成两部分。  
其中第二部分再进一步处理成一个适合换元和部分分式分解的形式。

---

## 第一步：先拆出一个容易积分的部分

设
$$
A=\int \frac{x^4}{1+x^6}\,dx,\qquad
B=\int \frac{1}{1+x^6}\,dx
$$

则

$$
A+B=\int \frac{x^4+1}{x^6+1}\,dx
$$

注意到
$$
x^6+1=(x^2+1)(x^4-x^2+1)
$$

并且
$$
x^4+1=x^4-x^2+1+x^2
$$

所以
$$
A+B
=
\int
\frac{x^4-x^2+1+x^2}{(x^4-x^2+1)(x^2+1)}\,dx
=
\int \frac{1}{x^2+1}\,dx+\int \frac{x^2}{1+x^6}\,dx
$$

整理后，原解法可写成
$$
B
=
\arctan x+\frac13\arctan(x^3)-\int \frac{x^2-1}{x^4-x^2+1}\,dx
$$

下面处理最后这个积分。

---

## 第二步：处理
$$
\int \frac{x^2-1}{x^4-x^2+1}\,dx
$$

先把分子分母同时除以 $x^2$：

$$
\int \frac{x^2-1}{x^4-x^2+1}\,dx
=
\int \frac{1-\frac1{x^2}}{x^2-1+\frac1{x^2}}\,dx
$$

令
$$
u=x+\frac1x
$$

则
$$
du=\left(1-\frac1{x^2}\right)dx
$$

并且
$$
u^2=x^2+2+\frac1{x^2}
\quad\Rightarrow\quad
x^2+\frac1{x^2}=u^2-2
$$

所以分母变成
$$
x^2-1+\frac1{x^2}=u^2-3
$$

于是
$$
\int \frac{x^2-1}{x^4-x^2+1}\,dx
=
\int \frac{du}{u^2-3}
$$

---

## 第三步：对 $$\int \frac{du}{u^2-3}$$ 做部分分式分解

$$
u^2-3=(u-\sqrt3)(u+\sqrt3)
$$

所以
$$
\frac{1}{u^2-3}
=
-\frac{1}{2\sqrt3}\left(\frac{1}{\sqrt3+u}+\frac{1}{\sqrt3-u}\right)
$$

因此
$$
\int \frac{du}{u^2-3}
=
-\frac{1}{2\sqrt3}\int\left(\frac{1}{\sqrt3+u}+\frac{1}{\sqrt3-u}\right)\,du
$$

积分得
$$
\int \frac{du}{u^2-3}
=
-\frac{1}{2\sqrt3}
\ln\left|\frac{\sqrt3+u}{\sqrt3-u}\right|+C
$$

代回
$$
u=x+\frac1x
$$

得到
$$
\int \frac{x^2-1}{x^4-x^2+1}\,dx
=
-\frac{1}{2\sqrt3}
\ln\left|
\frac{\sqrt3+x+\frac1x}{\sqrt3-x-\frac1x}
\right|
+C
$$

---

## 第四步：代回原式

前面已经得到
$$
B
=
\arctan x+\frac13\arctan(x^3)-\int \frac{x^2-1}{x^4-x^2+1}\,dx
$$

代入上一步结果：

$$
B
=
\arctan x+\frac13\arctan(x^3)
-\left(
-\frac{1}{2\sqrt3}
\ln\left|
\frac{\sqrt3+x+\frac1x}{\sqrt3-x-\frac1x}
\right|
\right)+C
$$

即

$$
\boxed{
\int \frac{1}{1+x^6}\,dx
=
\arctan x+\frac13\arctan(x^3)
+\frac{1}{2\sqrt3}
\ln\left|
\frac{\sqrt3+x+\frac1x}{\sqrt3-x-\frac1x}
\right|
+C
}
$$

---

## 最终答案
$$
\boxed{
\int \frac{1}{1+x^6}\,dx
=
\arctan x+\frac13\arctan(x^3)
+\frac{1}{2\sqrt3}
\ln\left|
\frac{\sqrt3+x+\frac1x}{\sqrt3-x-\frac1x}
\right|
+C
}
$$

---

## 备注
这个解法最关键的两步：

1. 利用
   $$
   1+x^6=(x^2+1)(x^4-x^2+1)
   $$
   做拆分。

2. 对
   $$
   \int \frac{x^2-1}{x^4-x^2+1}\,dx
   $$
   使用换元
   $$
   u=x+\frac1x
   $$
   因为它正好产生
   $$
   du=\left(1-\frac1{x^2}\right)dx
   $$
   并把四次式压成二次式 $u^2-3$。