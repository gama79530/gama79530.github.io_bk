<script src='https://cdnjs.cloudflare.com/ajax/libs/mathjax/2.7.5/MathJax.js?config=TeX-MML-AM_CHTML'></script>
<script type="text/x-mathjax-config">
    MathJax.Hub.Config({ tex2jax: {inlineMath: [['$','$'], ['\\(','\\)']]} });
</script>

# 學習資源
- [NTHU OCW - 機率論 統計學研究所 鄭少為](https://www.youtube.com/playlist?list=PLMLDTsrwM34CAxnukrPAO9nnx7wlNkDKR)
- A First Course in PROBABILITY (textbook)

# Catalog
1. [Chapter 1](#Chapter&nbsp;1)

# Introduction
1. 機率論是用來處理"不確定性"的理論

# Chapter&nbsp;1
## 符號
1. Factorial : $n!$
   - $0! = 1$
1. Binomial coefficient : $\binom{n}{r}$
   - $\binom{n}{r} = \frac{n!}{r!\left\(n-r\right\)!}$ if $0 \leq r \leq n$
   - $\binom{n}{r} = 0$ otherwise
1. Multinomial coefficient : $\binom{n}{n_{1}, \cdots, n_{r}} = \frac{n!}{n_{1}!\cdots n_{r}!}$

## 公式
1. $(x + y)^{n} = \sum_{r=0}^{n}\binom{n}{r}x^{r}y^{n-r}$
   - set $x = 1$ and $y = 1 \Rightarrow 2^{n} = \sum_{r=0}^{n}\binom{n}{r}$
   - set $x = -1$ and $y = 1 \Rightarrow 0 = \sum_{r=0}^{n}\binom{n}{r}(-1)^{r}$
1. $\binom{n}{r} = \binom{n - 1}{r - 1} + \binom{n - 1}{r}$
1. $(x_{1} + \cdots + x_{r})^{n} = \sum_{n_{1} + \cdots + n_{r}=n}\binom{n}{n_{1}, \cdots, n_{r}}x_{1}^{n_{1}}\cdots x_{r}^{n_{r}}$

## 五種排列組合計數的model
1. List 
   - model
     1. $r$個位置，每個位置有$n_{i}$個選擇
     1. 用"向量"表示 : $\left\(x_{1}, \cdots, x_{r}\right\)$
   - 重要特性
     1. 重視順序
     1. 計數 : $n_{1} \times \cdots \times n_{r}$ (乘法原理)

1. Permutation
   - model
     1. $n$個物件分配到$r$個位置，物件不能重複放
     1. 用"向量"表示 : $\left\(x_{1}, \cdots, x_{r}\right\)$
   - 重要特性
     1. 重視順序
     1. 可以視作增加額外限制條件的List
     1. 計數 : $P(n,r) = \frac{n!}{r!}$

1. Combination
   - model
     1. $n$個物件取出$r$個
     1. 用"集合"表示 : $\left\\{x_{1}, \cdots, x_{r}\right\\}$
   - 重要特性
     1. 忽視順序
     1. 計數 : $\binom{n}{r}$
     1. $P(n,r) = r!\binom{n}{r}$

1. Partition
   - model
     1. $n$個物件分成$r$組，每一組分別有$n_{i}$個物件
     1. 符號表示 : $\left\(Z_{1}, \cdots, Z_{r}\right\)$
        - $\bigcup_{i = 1}^{r}Z_{i} = Z$
        - $Z_{i} \bigcap Z_{j} = \phi$, for all $1 \leq i, j \leq r$
   - 重要特性
     1. 重視順序的Partition可當作是由互斥子集形成的list
     1. 計數 : $\frac{n!}{n_{1}! \cdots n_{r}!}$
     1. 若要計算忽視順序的Partition可先計算重視順序的Partition再除掉重複計算的factor
     1. 計數 : $\left\(\frac{1}{r!}\right\)\left\(\frac{n!}{n_{1}! \cdots n_{r}!}\right\)$
     1. 若要忽視順序則至少每個子集的元素數量要相等

1. The number of integer solutions
   - model
     1. $n$個物件取出$r$個
     1. 用"集合"表示 : $\left\\{x_{1}, \cdots, x_{r}\right\\}$
   - 重要特性
     1. 忽視順序
     1. 計數 : $\binom{n}{r}$

# 重要範例
1. tournament
   - $n = 2^{m}$ 個人進行單循環淘汰賽
   - 第一輪共有幾種組合 ?
     1. 看成$\left\(\left\(\right\), \left\(\right\), \left\(\right\), \left\(\right\)\right\)$後再除掉重複的factor $4!$
     1. 用$\left\\{\right\\}$計算$\left\(\right\)$後再乘上factor
     1. $\left\(\frac{n!}{2^{n/2}}\right\)\left\(2^{n/2}\right\)\left\(\frac{n}{2}\right\)! = \frac{n!}{\left\(\frac{n}{2}\right\)!}$
   - 整個比完共有幾種組合 ?
     1. $\frac{n!}{\left\(\frac{n}{2}\right\)!} \times \frac{\left\(\frac{n}{2}\right\)!}{\left\(\frac{n}{4}\right\)!} \times \cdots \frac{2}{1} = n!$
     1. 另外一種解法，第1個位置代表冠軍，之後的第$i$個位置代表的是因為輸給第$\left\lfloor\frac{i}{2}\right\rfloor$個位置的人而被淘汰的人，因此可以把問題轉換成排列問題，所以答案為$n!$