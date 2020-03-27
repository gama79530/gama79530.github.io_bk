<script src='https://cdnjs.cloudflare.com/ajax/libs/mathjax/2.7.5/MathJax.js?config=TeX-MML-AM_CHTML'></script>
<script type="text/x-mathjax-config">
    MathJax.Hub.Config({ tex2jax: {inlineMath: [['$','$'], ['\\(','\\)']]} });
</script>

# 學習資源
- [NTHU OCW - 機率論 統計學研究所 鄭少為](https://www.youtube.com/playlist?list=PLMLDTsrwM34CAxnukrPAO9nnx7wlNkDKR)
- A First Course in PROBABILITY (textbook)

# Catalog
1. [Chapter 1](#chapter-1)
1. [Chapter 2](#chapter-2)
1. [Chapter 3](#chapter-3)
1. [Chapter 4](#chapter-4)
1. [Chapter 5](#chapter-5)
1. [Chapter 6](#chapter-6)
1. [Chapter 7](#chapter-7)


# Chapter 1
## Introduction
1. 機率論是用來處理"不確定性"的理論

## 符號
1. Factorial : $n!$
   - $0! = 1$
1. Binomial coefficient : $\binom{n}{r}$
   - $\binom{n}{r} = \frac{n!}{\left\(r!\right\)\left\(n-r\right\)!}$ if $0 \leq r \leq n$
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
     1. 用"向量"表示 : $(x_{1}, \cdots, x_{r})$
   - 重要特性
     1. 重視順序
     1. 計數 : $n_{1} \times \cdots \times n_{r}$ (乘法原理)

1. Permutation
   - model
     1. $n$個物件分配到$r$個位置，物件不能重複放
     1. 用"向量"表示 : $(x_{1}, \cdots, x_{r})$
   - 重要特性
     1. 重視順序
     1. 可以視作增加額外限制條件的List
     1. 計數 : $P(n,r) = \frac{n!}{(n - r)!} = (r!)\binom{n}{r}$

1. Combination
   - model
     1. $n$個物件取出$r$個
     1. 用"集合"表示 : $\\{x_{1}, \cdots, x_{r}\\}$
   - 重要特性
     1. 忽視順序
     1. 計數 : $\binom{n}{r} = \frac{n!}{(r!)(n - r)!} = \frac{\binom{n}{r}}{r!}$

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
     1. $x_{1} + \cdots + x_{r} = n$的非負整數解個數
   - 重要特性
     1. 可視為將"重視順序"的所有Partition的方法數做總和
     1. 計數 : $\binom{n + r - 1}{r - 1}$

## 重要範例
1. Tournament
   - $n = 2^{m}$ 個人進行單循環淘汰賽
   - 第一輪共有幾種組合 ?
     1. 看成$\left\(\left\(\right\), \left\(\right\), \left\(\right\), \left\(\right\)\right\)$後再除掉重複的factor $4!$
     1. 用$\left\\{\right\\}$計算$\left\(\right\)$後再乘上factor
     1. $\left\(\frac{n!}{2^{n/2}}\right\)\left\(2^{n/2}\right\)\left\(\frac{n}{2}\right\)! = \frac{n!}{\left\(\frac{n}{2}\right\)!}$
   - 整個比完共有幾種組合 ?
     1. $\frac{n!}{\left\(\frac{n}{2}\right\)!} \times \frac{\left\(\frac{n}{2}\right\)!}{\left\(\frac{n}{4}\right\)!} \times \cdots \frac{2}{1} = n!$
     1. 另外一種解法，第1個位置代表冠軍，之後的第$i$個位置代表的是因為輸給第$\left\lfloor\frac{i}{2}\right\rfloor$個位置的人而被淘汰的人，因此可以把問題轉換成排列問題，所以答案為$n!$

## 課本習題 
### PROBLEMS
1-(a)
- model : $()\_{L}$
- $(26)^{2}(10)^5$ if case insensitive.
- $(52)^{2}(10)^5$ if case sensitive.

1-(b)
- model : $()\_{P}$
- $P(26,2) \times P(10, 5) = 26 \times 25 \times 10 \times 9 \times 8 \times 7 \times 6$  if case insensitive.
- $P(26,2) \times P(10, 5) = 52 \times 51 \times 10 \times 9 \times 8 \times 7 \times 6$  if case sensitive.

4-1st ?
- model : $()\_{P}$
- $4!$

4-2nd ?
- model : $(()\_{P}, ()\_{P})\_{L}$
- $2! \times 2!$

20-(a)
- model : $\\{\\} - \\{\\}$ 
- $\binom{8}{5} - \binom{6}{3}$

20-(b)
- model : $\\{\\} - (\\{\\}, \\{\\})$
- $\binom{8}{5} - \binom{2}{1}\binom{6}{4}$

26
- $\sum_{t_{1} + t_{2} + t_{3} = 4}\binom{4}{t_{1}, t_{2}, t_{3}}(x_{1})^{t_{1}}(2x_{2})^{t_{2}}(3x_{3})^{t_{3}} = $  
$(x_{1}^{4} + 16x_{2}^{4} + 81x_{3}^{4}) + $  
$(4)(2x_{1}^{3}x_{2} + 8x_{1}x_{2}^{3} + 3x_{1}^{3}x_{3} + 27x_{1}x_{3}^{3} + 24x_{2}^{3}x_{3} + 54x_{2}x_{3}^{3}) + $  
$(6)(4x_{1}^{2}x_{2}^{2} + 9x_{1}^{2}x_{3}^{2} + 36x_{2}^{2}x_{3}^{2}) + $  
$(12)(6x_{1}^{2}x_{2}x_{3} + 12x_{1}x_{2}^{2}x_{3} + 18x_{1}x_{2}x_{3}^{2})$

32-1st ?
- model : the number of integer solutions
- $\binom{8 + 6 - 1}{6 - 1} = \binom{13}{5}$

32-2nd ?
- model : $()\_{L}$ + the number of integer solutions
- $\binom{5 + 6 - 1}{6 - 1}\binom{3 + 6 - 1}{6 - 1} = \binom{10}{5}\binom{8}{5}$

### THEORETICAL EXERCISES
5
- model : $\\{\\}$
- $\sum_{i = k}^{n}\binom{n}{i}$

7
- $\binom{n}{r} = \frac{n!}{(r!)(n - r)!} = $  
$\left\[\frac{(n - 1)!}{(r - 1)!(n - r - 1)!}\right\]\left\[\frac{n}{r(n-r)}\right\] = $  
$\left\[\frac{(n - 1)!}{(r - 1)!(n - r - 1)!}\right\]\left\[\frac{1}{n - r} + \frac{1}{r}\right\] = $  
$\frac{(n - 1)!}{(r - 1)!(n - r)!} + \frac{(n - 1)!}{(r!)(n - r - 1)!} = \binom{n - 1}{r - 1} + \binom{n - 1}{r}$

11
- We can classify the ways to select $k$ number from $1, \cdots, n$ according to the maximum of selected numbers.
- The number of ways to select $k$ numbers from $1, \cdots, n$ whose maximum is $i$ is equivalent to the number of ways to select $k - 1$ numbers from $1, \cdots, i - 1$
- The range of maximum is $k, \cdots, n$
- Thus $\binom{n}{k} = \sum_{i=k}^{n}\binom{i - 1}{k - 1}$

16-(a)
- $(1, 1, 1)$
  1. $\\{a, b, c\\}$
- (1, 1, 3)
  1. $\\{a, b\\}, \\{c\\}$
  1. $\\{a, c\\}, \\{b\\}$
  1. $\\{b, c\\}, \\{a\\}$
- $(1, 2, 2)$
  1. $\\{a\\}, \\{b, c\\}$
  1. $\\{b\\}, \\{a, c\\}$
  1. $\\{c\\}, \\{a, b\\}$
- $(1, 2, 3)$
  1. $(a, b, c)$
  1. $(a, c, b)$
  1. $(b, a, c)$
  1. $(b, c, a)$
  1. $(c, a, b)$
  1. $(c, b, a)$

16-(b)
- We can classify outcomes according to the number of champions
- The number of outcomes whose number of champions is $i$ is $\binom{n}{i}N(n - i)$
  1. Use model $(\\{\\}, ())$
  1. Choose champions at first
  1. Then ranking the others. 
- The range of the number of champions is $1, \cdots, n$ 
- Thus $N(n) = \sum_{i=1}^{n}\binom{n}{i}N(n - i)$

16-(c)
- $N(n) = \sum_{i = 1}^{n}\binom{n}{i}N(n - i) = $  
$\binom{n}{1}N(n - 1) + \cdots + \binom{n}{n}N(0) = $  
$\binom{n}{0}N(0) + \cdots + \binom{n}{n - 1}N(n - 1) = \sum_{i = 0}^{n - 1}\binom{n}{i}N(i)$

16-(d)
- $N(3) = (1)(1) + (3)(1) + (3)(3) = 13$
- $N(4) = (1)(1) + (4)(1) + (6)(3) + (4)(13) = 75$

### SELF-TEST PROBLEMS AND EXERCISES
3-(a)
- model : $()\_{P}$
- $P(10,3)$

3-(b)
- model : $()\_{P} + (\\{\\}, \\{\\})\_{P}$
- $P(8, 3) + P(3, 3) \times \binom{2}{1}\binom{8}{2}$

3-(c)
- model : $()\_{P} + (\\{\\}, \\{\\})\_{P}$
- $P(8, 3) + P(3, 3) \times \binom{8}{1}$

3-(d)
- model : $(\\{\\}, \\{\\})\_{P} $
- $P(3, 3) \times \binom{9}{2}$

3-(e)
- model : $(\\{\\}, ()\_{P})_{L} + ()\_{p}$
- $P(9,2) + P(9, 3)$

8-(a)
- model : $()\_{L}$
- $10 \times 9^{n-1}$

8-(b)
- model : $(\\{\\}, ()\_{L})\_{L}$
- $\binom{n}{i} \times 9^{n - i}$

14
- model : the number of integer solutions
- $\binom{k - n + n + 1 - 1}{n + 1 - 1} = \binom{k}{n}$ 
- 另一種解法  
$\sum_{i=n}^{k}\binom{i - 1}{n - 1} = \binom{n - 1}{n - 1} + \binom{n}{n - 1} + \cdots + \binom{k - 1}{n - 1} = $  
$\binom{n}{n} + \binom{n}{n - 1} + \cdots + \binom{k - 1}{n - 1} = $  
$\binom{n+1}{n} + \binom{n + 1}{n - 1} + \cdots + \binom{k - 1}{n - 1} = \cdots = \binom{k}{n}$

15
- model : $(\\{\\})\_{P}$
- $\sum_{k=0}^{n}\binom{n}{k}P(k, k)$ 

# Chapter 2
## Introduction
- 機率空間 : 樣本空間 + 事件 + 機率測度
- 機率值的含意
  1. 客觀 : 長期觀測後得到的發生的頻率
  1. 主觀 : 單純反映評估出的可能性的大小

## 樣本空間(Sample space)與事件(Event)
- 樣本空間
  1. 由一個隨機(不可預測的)事件的所有可能結果(outcome)構成的集合
  1. 可能結果的定義受記錄的方式(encoding)影響，紀錄的方式又受收集資料的方法影響
  1. 樣本空間分類
     - 有限或可數的((countable))樣本空間統稱為離散型(discrete)樣本空間
     - 不可數的(uncountable)樣本空間統稱為連續型(continuous)樣本空間

- 事件
  1. 任意一個樣本空間的(可測量的)子集都是一個樣本空間的事件
  1. 所有可能的子集合 : $2^{\Omega}$
  1. 並非每一個樣本空間的子集合都能定義機率，能定義機率的那些子集合稱之為可測量(measurable)的，通常是對於不可數的樣本空間的子集才會需要特別注意是否為可測量的

## 機率測度(Probability measure)
- 測度定義
  1. 測度在"實變數函數論"與"高等機率論"會有嚴謹的定義
  1. 不嚴謹的測度定義
     - 離散型樣本空間 : 一個函數 $f: 2^{\Omega} \rightarrow \[0,1\]$
     - 連續型樣本空間 : 一個函數$f: \sigma \rightarrow \[0,1\]$

- 傳統機率測度定義
  1. 有限的樣本空間$\Omega$
  1. 每一個可能結果發生的機率要相等
  1. 特定事件$A$的機率 : $P(A) = \frac{\\# A}{\\#\Omega}$

- 現代機率測度定義
  1. 一個在樣本空間$\Omega$上的機率測度是一個滿足下列公理的實數函數$f: 2^{\Omega} \rightarrow \mathbb{R}$
     - 非負 : 對任意事件$A$, $P(A) \geq 0$
     - 總合為1 : $P(\Omega) = 1$
     - 加法性 : 對任意兩倆互斥的事件$A_{1}, A_{2}, \cdots$，$P(A_{1} \cup A_{2} \cup \cdots) = P(A_{1}) + P(A_{2})   + \cdots$
  
- 重要特性
  1. 對於任意事件$A$，$P(A^{c}) = 1 - P(A)$
  1. $P(\phi) = 0$
  1. 若事件$A_{1}, \cdots, A_{n}$兩倆互斥, 則$P(A_{1} \cup \cdots \cup A_{n}) = P(A_{1}) + \cdots + P(A_{n})$
  1. 若兩事件$A$, $B$滿足$A \subseteq B$，則$P(A) \leq P(B)$
  1. 對於任意事件$A$，$0 \leq P(A) \leq 1$
  1. 對於任意兩個事件$A$,$B$，$P(A \cup B) = P(A) + P(B) - P(A \cap B)$
  1. 對於事件$A_{1}, \cdots, A_{n}$，$P(A_{1} \cup \cdots \cup A_{n}) \leq P(A_{1}) + \cdots + P(A_{n})$
  1. 排容原理 : 對任意事件$A_{1}, \cdots, A_{n}$  
     $P(A_{1} \cup \cdots \cup A_{n}) = \sum_{i = 1}^{n}\left\[\sum_{1 \leq t_{1} < \cdots < t_{i} \leq n}(-1)^{i+1}P(A_{t_{1}} \cap \cdots \cap A_{t_{i}})\right\]$
  1. 若$A_{1}, A_{2}, \cdots$是一組$\Omega$的分割(partition)，即$\cup_{i = 1}^{\infty}A_{i} = \Omega$且$A_{1}, A_{2}, \cdots$兩倆互斥，則$P(A) = \sum_{i = 1}^{\infty}P(A \cap A_{i})$
  
## 離散型樣本空間測度
- 定義
  1. $\Omega = \\{\omega_{1}, \omega_{2}, \cdots\\}$
  1. 給定一個函數$p(\omega) \geq 0$, for all $\omega \in \Omega$ 以及 $\sum_{\omega \in \Omega}p(\omega) = 1$
  1. 定義$P(A) = \sum_{\omega \in A}p(\omega)$
  1. 這個定義方式把原本需要定義$2^{|\Omega|} -1$個值縮減到只需要定義 $|\Omega|$個值

## 連續型樣本空間測度
- 定義
  1. 遞增(increasing)事件序列$A_{1}, A_{2}, \cdots, A_{n}, \cdots$
     - 定義 : $A_{1} \subseteq A_{2} \subseteq \cdots \subseteq A_{n} \subseteq \cdots \subseteq \Omega$
     - 極限定義 : $\lim_{n \rightarrow \infty}A_{n} = \cup_{i = 1}^{\infty}A_{i}$
  1. 遞減(decreasing)事件序列$A_{1}, A_{2}, \cdots, A_{n}, \cdots$
     - 定義 : $A_{1} \supseteq A_{2} \supseteq \cdots \supseteq A_{n} \supseteq \cdots \supseteq \phi$
     - 極限定義 : $\lim_{n \rightarrow \infty}A_{n} = \cap_{i = 1}^{\infty}A_{i}$
  
- 重要特性
  1. 若事件序列$A_{1}, A_{2}, \cdots$為遞增或遞減事件序列，則$(\lim_{n \rightarrow \infty}A_{n})^{c} = \lim_{n \rightarrow \infty}A_{n}^{c}$
  1. 若事件序列$A_{1}, A_{2}, \cdots$為遞增或遞減的事件序列，則$\lim_{n \rightarrow \infty}P(A_{n}) = P(\lim_{n \rightarrow \infty}A_{n})$
  1. 對於任意事件$A=\\{\omega\\}$，$P(A) = 0$
  1. 對於任意事件$A=\\{\omega_{1}, \omega_{2}, \cdots\\}$，$P(A) = 0$

## 重要範例
- Waiting for success - play roulette until a win
  1. $\Omega = \\{1, 2, \cdots\\}$
  1. 假設單一一次獲勝的機率是$r = \frac{9}{19}$, 輸掉的機率$q = 1 - r = \frac{10}{19}$
  1. 定義$p(n) = q^{n - 1}r$

- Uniform Spinner :
  1. $\Omega = (- \pi, \pi]$
  1. 對任意子區間$(a, b] \subseteq \Omega$，$P((a, b]) = \frac{b - a}{2 \pi}$，這個定義的作用類似於離散型的$p$
  1. $P(\[a, b\]) = P(\cap_{k = 1}^{\infty}(a - \frac{1}{k}, b]) = $  
  $\lim_{k \rightarrow \infty}P((a-\frac{1}{k}, b]) = $  
  $\lim_{k \rightarrow \infty}\left\[\left\(\frac{1}{2 \pi}\right\)\left\(b - a + \frac{1}{k}\right\)\right\] = \frac{b - a}{2 \pi}$

# Chapter 3
# Chapter 4
# Chapter 5
# Chapter 6
# Chapter 7