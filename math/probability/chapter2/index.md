<script src='https://cdnjs.cloudflare.com/ajax/libs/mathjax/2.7.5/MathJax.js?config=TeX-MML-AM_CHTML'></script>
<script type="text/x-mathjax-config">
    MathJax.Hub.Config({ tex2jax: {inlineMath: [['$','$'], ['\\(','\\)']]} });
</script>

# 學習資源
- [NTHU OCW - 機率論 統計學研究所 鄭少為](https://www.youtube.com/playlist?list=PLMLDTsrwM34CAxnukrPAO9nnx7wlNkDKR)
- A First Course in PROBABILITY (textbook)

# Catalog
1. [Chapter 1](..\chapter1)
1. [Chapter 2](..\chapter2)
1. [Chapter 3](..\chapter3)
1. [Chapter 4](..\chapter4)
1. [Chapter 5](..\chapter5)
1. [Chapter 6](..\chapter6)
1. [Chapter 7](..\chapter7)

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
     $P(\bigcup_{i=1}^{n}A_{i}) = $  
     $\sum_{i = 1}^{n}\left\[\sum_{1 \leq t_{1} < \cdots < t_{i} \leq n}(-1)^{i+1}P(\bigcap_{j=1}^{i} A_{t_{j}})\right\]$
  1. 若$A_{1}, A_{2}, \cdots$是一組$\Omega$的分割(partition)，即$\bigcup_{i = 1}^{\infty}A_{i} = \Omega$且$A_{1}, A_{2}, \cdots$兩倆互斥，則$P(A) = \sum_{i = 1}^{\infty}P(A \cap A_{i})$
  
## 離散型樣本空間測度
- 定義
  1. $\Omega = $  
  $\\{\omega_{1}, \omega_{2}, \cdots\\}$
  1. 給定一個函數$p(\omega) \geq 0$, for all $\omega \in \Omega$  
  以及 $\sum_{\omega \in \Omega}p(\omega) = 1$
  1. 定義$P(A) = \sum_{\omega \in A}p(\omega)$
  1. 這個定義方式把原本需要定義$2^{\left &#124; \Omega \right &#124;} -1$個值縮減到只需要定義 $\left &#124; \Omega \right &#124;$個值

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

## 心得
1. 善用分割將事件做分類

### PROBLEMS
9
- $0.24 + 0.61 - 0.11 = 0.74$  

11-(a)
- $1 - (0.28 + 0.07 - 0.05) = 0.7$  

11-(b)
- $0.07 - 0.05 = 0.02$

13-(a)
- $100000 \times \[$  
$(0.1 - 0.08 -0.02 + 0.01) + $  
$(0.3 - 0.08 -0.04 + 0.01) + $  
$(0.05 - 0.02 -0.04 + 0.01)$  
$\] = 20000$

13-(b)
- $100000 \times (0.08 + 0.02 + 0.04 - 2 \times 0.01) = $  
$12000$

13-(c)
- $100000 \times (0.08 + 0.04 - 0.01) = 11000$

13-(d)
- $100000 \times \[1 - (0.1 + 0.3 + 0.05) + $  
$(0.08 + 0.02 + 0.04) - 0.01\] = 68000$

13-(e)
- $100000 \times (0.08 + 0.04 - 2 \times 0.01) = 10000$

27
- $\frac{P(7, 0)\binom{3}{1}P(9, 9)}{P(10, 10)} + \frac{P(7, 2)\binom{3}{1}P(7, 7)}{P(10, 10)} + \frac{P(7, 4)\binom{3}{1}P(5, 5)}{P(10, 10)} + $  
$\frac{P(7, 6)\binom{3}{1}P(3, 3)}{P(10, 10)}$

30-(a)
- $\frac{\binom{7}{3}\binom{8}{3}P(3, 3)}{\binom{8}{4}\binom{9}{4}P(4, 4)}$

30-(b)
- $\frac{\binom{7}{3}\binom{8}{3}\left\[P(4, 4) - P(3, 3)\right\]}{\binom{8}{4}\binom{9}{4}P(4, 4)}$

30(c)
- $1 - \frac{\binom{7}{4}\binom{8}{4}P(4, 4)}{\binom{8}{4}\binom{9}{4}P(4, 4)}$

31-(a)
- $\frac{3!}{3^{3}}$

31-(b)
- $\frac{\binom{3}{1}}{3^{3}}$

32
- $\frac{\binom{g}{1}(b + g - 1)!}{(b + g)!}$

39-1st ?
- $\frac{P(5, 3)}{5^{3}}$

39-2nd ?
- 每個人選擇其中一間旅館的機率都相等

41
- $1 - \frac{5^{4}}{6^{4}}$

47
- $\frac{P(12, 12)}{12^{12}}$

51
- $\frac{\binom{n}{m}(N - 1)^{(n - m)}}{N^{n}}$

### THEORETICAL EXERCISES
8-(a)
- $T_{3}$ :  
$\\{\\{1, 2, 3\\}\\}$  
$\\{\\{1, 2\\}, \\{3\\}\\}, \\{\\{1, 3\\}, \\{2\\}\\}, \\{\\{2, 3\\}, \\{1\\}\\}$  
$\\{\\{1\\}, \\{2\\}, \\{3\\}\\}$

- $T_{4}$ :  
$\\{\\{1, 2, 3, 4\\}\\}$  
$\\{\\{1, 2, 3\\}, \\{4\\}\\}, \\{\\{1, 2, 4\\}, \\{3\\}\\}, \\{\\{1, 3, 4\\}, \\{2\\}\\}, $  
$\\{\\{2, 3, 4\\}, \\{1\\}\\}$  
$\\{\\{1, 2\\}, \\{3, 4\\}\\}, \\{\\{1, 3\\}, \\{2, 4\\}\\}, \\{\\{1, 4\\}, \\{2, 3\\}\\}$  
$\\{\\{1, 2\\}, \\{3\\}, \\{4\\}\\}, \\{\\{1, 3\\}, \\{2\\}, \\{4\\}\\}, $  
$\\{\\{1, 4\\}, \\{2\\}, \\{3\\}\\},\\{\\{2, 3\\}, \\{1\\}, \\{4\\}\\}, $  
$\\{\\{2, 4\\}, \\{1\\}, \\{3\\}\\}, \\{\\{3, 4\\}, \\{1\\}, \\{2\\}\\}$   
$\\{\\{1\\}, \\{2\\}, \\{3\\}, \\{4\\}\\}$

8-(b)
- 對於任意的分割，我們可以根據$n + 1$所在的子集合做分類
  1. $n + 1$所在的子集合有$n + 1$個元素
  1. $n + 1$所在的子集合有$t$個元素($1 \leq t \leq n$)  
  每一個分類的計數 : $\binom{n}{t - 1}T_{n + 1 - t}$
  1. $T_{n + 1} = 1 + \sum_{t = 1}^{n}\binom{n}{t - 1}T_{n + 1 - t}$
  1. 令$k = n + 1 - t$，則$t = n + 1 - k \Rightarrow 1 \leq n + 1 - k \leq n \Rightarrow $  
  $1 \leq k \leq n$  
  1. 因此$T_{n + 1} = 1 + \sum_{k = 1}^{n}\binom{n}{n - k}T_{k} = $  
  $1 + \sum_{k = 1}^{n}\binom{n}{k}T_{k}$  
  
11
- $1 \geq P(E \cup F) = P(E) + P(F) - P(EF) \Rightarrow $  
$P(EF) \geq P(E) + P(F) - 1$
- $P(EF) \geq 0.9 + 0.8 - 1 = 0.7$

19
- $\left\[\frac{1}{(m + n)!}\right\]\left\[\binom{n}{r - 1}\binom{m}{k - r}P(k - 1, k - 1)\right\]\left\[\binom{n - r + 1}{1}\right\]$  
$\left\[P(m + n - k, m + n - k)\right\] = \frac{r\binom{m}{k - r}\left\[\frac{n!}{r!(n - r)!}\right\]}{k\left\[\frac{(m + n)!}{k!(m + n - k)!}\right\]} = $  
$\frac{r\binom{n}{r}\binom{m}{k - r}}{k\binom{m + n}{k}}$

21
- 總共$2k$輪 $\Rightarrow$ $k$輪連勝與$k$輪連敗 $\Rightarrow$  
  1. 連勝開始或連敗開始 : $\binom{2}{1}$
  1. $w_{1} + \cdots + w_{k} = n$ 的非負整數解
  1. $l_{1} + \cdots + l_{k} = m$ 的非負整數解
  1. 因此機率$P\\{2k \text{ runs}\\} = \frac{2\binom{n - 1}{k - 1}\binom{m - 1}{k - 1}}{\binom{m + n}{n}}$
- 總共$2k + 1$輪 $\Rightarrow$ $k + 1$輪連勝與$k$輪連敗或$k$輪連勝與$k + 1$輪連敗 $\Rightarrow$  
  1. 連勝開始 
  1. $w_{1} + \cdots + w_{k + 1} = n$ 的非負整數解
  1. $l_{1} + \cdots + l_{k} = m$ 的非負整數解
  1. 連敗開始 
  1. $w_{1} + \cdots + w_{k} = n$ 的非負整數解
  1. $l_{1} + \cdots + l_{k + 1} = m$ 的非負整數解
  1. 因此機率$P\\{2k + 1 \text{ runs}\\} = \frac{\binom{n - 1}{k}\binom{m - 1}{k - 1} + \binom{n - 1}{k - 1}\binom{m - 1}{k}}{\binom{m + n}{n}}$

### SELF-TEST PROBLEMS AND EXERCISES
12
- $\frac{\binom{4}{2}\binom{6}{2}\binom{2}{1}[\binom{4}{2, 2} / P(2, 2)]}{\binom{10}{2, 2, 2, 2, 2} / P(5, 5)}$

13
- $\left\(\frac{2}{7}\right\)\left\(\frac{1}{8}\right\) + \left\(\frac{3}{7}\right\)\left\(\frac{1}{8}\right\) + \left\(\frac{1}{7}\right\)\left\(\frac{0}{8}\right\) + \left\(\frac{1}{7}\right\)\left\(\frac{1}{8}\right\)$

16
- 根據$1$所在的子集將分割做分類
  1. 先將$2, \cdots, n$分割成k個非空子集後再選其中一個子集將$1$加入
  1. 計數 : $\binom{k}{1}T_{k}(n - 1)$
  1. 先將$2, \cdots, n$分割成$k- 1$個子集之後額外加上一個子集$\\{1\\}$
  1. 計數 : $T_{k - 1}(n - 1)$

20
- $\frac{1}{\binom{30}{10, 20}}$