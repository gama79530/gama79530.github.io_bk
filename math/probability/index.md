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
     1. 用"向量"表示 : $(x_{1}, \cdots, x_{r})_{L}$
   - 重要特性
     1. 計數 : $n_{1} \times \cdots \times n_{r}$ (乘法原理)
     1. 重視順序

1. Permutation
   - model
     1. $n$個選擇分配到$r$個位置
     1. 用"向量"表示 : $(x_{1}, \cdots, x_{r})_{P}$
   - 重要特性
     1. 計數 : $P(n,r) = \frac{n!}{(n - r)!} = \binom{n}{r} \times r!$
     1. 重視順序
     1. 可以視作增加額外限制條件的List (選擇不重複)
     1. 可以與combination做對應 ($()_{P} \equiv \\{\\} \times \text{factor}$)

1. Combination
   - model
     1. $n$個選擇選出$r$個
     1. 用"集合"表示 : $\\{x_{1}, \cdots, x_{r}\\}$
   - 重要特性
     1. 計數 : $\binom{n}{r} = \frac{n!}{(r!)(n - r)!} = \frac{\binom{n}{r}}{r!}$
     1. 忽視順序 (通常是用在把選擇分類)
     1. 可以與permutation做對應 ($\\{\\} \equiv \frac{()_{P}}{\text{factor}}$)

1. Partition
   - model
     1. $n$個選擇分成$r$類，每一類分別有$n_{i}$個選擇
     1. 符號表示 : $\left\(Z_{1}, \cdots, Z_{r}\right\)_{L}$
        - $\bigcup_{i = 1}^{r}Z_{i} = Z$
        - $Z_{i} \bigcap Z_{j} = \phi$, for all $1 \leq i, j \leq r$
   - 重要特性
     1. 計數 : $\frac{n!}{n_{1}! \cdots n_{r}!}$
     1. 重視子集合的順序
   - 乎視順序的分割
     1. 要忽視順序則的前提是每個子集的元素數量要相等
     1. 符號表示 : $\left\\{Z_{1}, \cdots, Z_{r}\right\\}$
   - 重要特性
     1. 計數 : $\left\(\frac{1}{r!}\right\)\left\(\frac{n!}{n_{1}! \cdots n_{r}!}\right\)$

1. The number of integer solutions (NIS)
   - model
     1. $x_{1} + \cdots + x_{r} = n$的非負整數解個數
   - 重要特性
     1. 計數 : $\binom{n + r - 1}{r - 1}$
     1. 可視為將"重視順序"的所有Partition的方法數做總和
     1. 可以藉由換變數的手法調整$x_{i}$的範圍
     1. 可以藉由增加變數來解決不等式問題  
     $x_{1} + \cdots + x_{r} \leq n \equiv x_{1} + \cdots + x_{r} + x_{r + 1} = n$

## 重要範例
1. Tournament
   - $n = 2^{m}$ 個人進行單循環淘汰賽
   - 第一輪共有幾種組合 ?
     1. model : $\\{()\_{P}, \cdots, ()\_{P}\\}$
     1. $\left\(\frac{1}{(n / 2)!}\right\)\left\(\frac{n!}{2^{(n / 2)}}\right\)\left\(2^{\frac{n}{2}}\right\) = \frac{n!}{(n / 2)!}$
   - 整個比完共有幾種組合 ? 
     1. model : $(\\{()\_{P}, \cdots, ()\_{P}\\}, \cdots, \\{()\_{P}, \cdots, ()\_{P}\\})_{L}$
     1. $\frac{n!}{\(n / 2\)!} \times \frac{(n / 2)!}{(n /4)!} \times \cdots \frac{2}{1} = n!$
     1. 另外一種解法，第$1$個位置代表冠軍，之後的第$i$個位置代表的是因為輸給第$i - 2^{\lfloor \lg (i - 1) \rfloor}$個位置的人而被淘汰的人，因此可以把問題轉換成排列問題，所以答案為$n!$

## 課本習題 
### 解題心得
1. 各個model經常對應到的問題類型
   - List : 選擇可重複
   - Permutation : 排列問題、配對問題
   - Combination : 選擇問題
   - Partition : 分類問題
   - NIS : 
1. 使用怎樣的標記作為選擇的區分編碼會影響對問題類型的判斷
1. 可以試著用遞迴的方式思考解法

### PROBLEMS
1-(a)
- model : $()\_{L}$
- 假如不區分大小寫 : $(26)^{2}(10)^5$
- 假如區分大小寫 : $(52)^{2}(10)^5$

1-(b)
- model : $(()\_{P}, ()\_{P})\_{L}$
- 假如不區分大小寫 : $P(26,2) \times P(10, 5) = 26 \times 25 \times 10 \times 9 \times 8 \times 7 \times 6$
- 假如區分大小寫 : $P(26,2) \times P(10, 5) = 52 \times 51 \times 10 \times 9 \times 8 \times 7 \times 6$

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
- model : $\\{\\} - (\\{\\}, \\{\\})_{L}$
- $\binom{8}{5} - \binom{2}{1}\binom{6}{4}$

26
- $\sum_{t_{1} + t_{2} + t_{3} = 4}\binom{4}{t_{1}, t_{2}, t_{3}}(x_{1})^{t_{1}}(2x_{2})^{t_{2}}(3x_{3})^{t_{3}} = $  
$(x_{1}^{4} + 16x_{2}^{4} + 81x_{3}^{4}) + $  
$(4)(2x_{1}^{3}x_{2} + 8x_{1}x_{2}^{3} + 3x_{1}^{3}x_{3} + 27x_{1}x_{3}^{3} + 24x_{2}^{3}x_{3} + 54x_{2}x_{3}^{3}) + $  
$(6)(4x_{1}^{2}x_{2}^{2} + 9x_{1}^{2}x_{3}^{2} + 36x_{2}^{2}x_{3}^{2}) + $  
$(12)(6x_{1}^{2}x_{2}x_{3} + 12x_{1}x_{2}^{2}x_{3} + 18x_{1}x_{2}x_{3}^{2})$

32-1st ?
- model : the number of integer solutions
- $\binom{8 + 7 - 1}{7 - 1} = \binom{14}{6}$

32-2nd ?
- model : $(\text{NIS}, \text{ NIS})\_{L}$
- $\binom{5 + 7 - 1}{7 - 1}\binom{3 + 7 - 1}{7 - 1} = \binom{11}{6}\binom{9}{6}$

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
- 將從$1, \cdots, n$中選$k$個數的方法根據選到的數的最大值做分類
  1. 最大值為$i$的方法計數 : $\binom{i - 1}{k - 1}$
  1. 最大值的範圍 : $k \leq i \leq n$
  1. 因此$\binom{n}{k} = \sum_{i = k}^{n}\binom{i - 1}{k - 1}$

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
- 根據冠軍的數量將淘汰賽的結果做分類
  1. 冠軍有$i$個人的結果計數 : $\binom{n}{i}N(n - i)$
  1. 冠軍人數的範圍 $1 \leq i \leq n$
  1. 因此$N(n) = \sum_{i = 1}^{n}\binom{n}{i}N(n - i)$

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
- model : NIS
- $\binom{k - n + n + 1 - 1}{n + 1 - 1} = \binom{k}{n}$ 
- 另一種解法  
$\sum_{i=n}^{k}\binom{i - 1}{n - 1} = \binom{n - 1}{n - 1} + \binom{n}{n - 1} + \cdots + \binom{k - 1}{n - 1} = $  
$\binom{n}{n} + \binom{n}{n - 1} + \cdots + \binom{k - 1}{n - 1} = $  
$\binom{n+1}{n} + \binom{n + 1}{n - 1} + \cdots + \binom{k - 1}{n - 1} = \cdots = \binom{k}{n}$

15
- model : $()\_{P}$
- $\sum_{k=0}^{n}P(n, k) = \sum_{k=0}^{n}\binom{n}{k}P(k, k)$ 

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
     $P(\bigcup_{i=1}^{n}A_{i}) = \sum_{i = 1}^{n}\left\[\sum_{1 \leq t_{1} < \cdots < t_{i} \leq n}(-1)^{i+1}P(\bigcap_{j=1}^{i} A_{t_{j}})\right\]$
  1. 若$A_{1}, A_{2}, \cdots$是一組$\Omega$的分割(partition)，即$\bigcup_{i = 1}^{\infty}A_{i} = \Omega$且$A_{1}, A_{2}, \cdots$兩倆互斥，則$P(A) = \sum_{i = 1}^{\infty}P(A \cap A_{i})$
  
## 離散型樣本空間測度
- 定義
  1. $\Omega = \\{\omega_{1}, \omega_{2}, \cdots\\}$
  1. 給定一個函數$p(\omega) \geq 0$, for all $\omega \in \Omega$ 以及 $\sum_{\omega \in \Omega}p(\omega) = 1$
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

## 解題心得
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
- $100000 \times (0.08 + 0.02 + 0.04 - 2 \times 0.01) = 12000$

13-(c)
- $100000 \times (0.08 + 0.04 - 0.01) = 11000$

13-(d)
- $100000 \times (1 - 0.1 - 0.3 - 0.05 + 0.08 + 0.02 + 0.04 - 0.01) = 68000$

13-(e)
- $100000 \times (0.08 + 0.04 - 2 \times 0.01) = 10000$

27
- $\frac{P(7, 0)\binom{3}{1}P(9, 9)}{P(10, 10)} + \frac{P(7, 2)\binom{3}{1}P(7, 7)}{P(10, 10)} + \frac{P(7, 4)\binom{3}{1}P(5, 5)}{P(10, 10)} + \frac{P(7, 6)\binom{3}{1}P(3, 3)}{P(10, 10)}$

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
$\\{\\{1, 2, 3\\}, \\{4\\}\\}, \\{\\{1, 2, 4\\}, \\{3\\}\\}, \\{\\{1, 3, 4\\}, \\{2\\}\\}, \\{\\{2, 3, 4\\}, \\{1\\}\\}$  
$\\{\\{1, 2\\}, \\{3, 4\\}\\}, \\{\\{1, 3\\}, \\{2, 4\\}\\}, \\{\\{1, 4\\}, \\{2, 3\\}\\}$  
$\\{\\{1, 2\\}, \\{3\\}, \\{4\\}\\}, \\{\\{1, 3\\}, \\{2\\}, \\{4\\}\\}, \\{\\{1, 4\\}, \\{2\\}, \\{3\\}\\},$  
$\\{\\{2, 3\\}, \\{1\\}, \\{4\\}\\}, \\{\\{2, 4\\}, \\{1\\}, \\{3\\}\\}, \\{\\{3, 4\\}, \\{1\\}, \\{2\\}\\}$   
$\\{\\{1\\}, \\{2\\}, \\{3\\}, \\{4\\}\\}$

8-(b)
- 對於任意的分割，我們可以根據$n + 1$所在的子集合做分類
  1. $n + 1$所在的子集合有$n + 1$個元素
  1. $n + 1$所在的子集合有$t$個元素($1 \leq t \leq n$)  
  每一個分類的計數 : $\binom{n}{t - 1}T_{n + 1 - t}$
  1. $T_{n + 1} = 1 + \sum_{t = 1}^{n}\binom{n}{t - 1}T_{n + 1 - t}$
  1. 令$k = n + 1 - t$，則$t = n + 1 - k \Rightarrow 1 \leq n + 1 - k \leq n \Rightarrow 1 \leq k \leq n$  
  1. 因此$T_{n + 1} = 1 + \sum_{k = 1}^{n}\binom{n}{n - k}T_{k} = 1 + \sum_{k = 1}^{n}\binom{n}{k}T_{k}$  
  
11
- $1 \geq P(E \cup F) = P(E) + P(F) - P(EF) \Rightarrow P(EF) \geq P(E) + P(F) - 1$
- $P(EF) \geq 0.9 + 0.8 - 1 = 0.7$

19
- $\left\[\frac{1}{(m + n)!}\right\]\left\[\binom{n}{r - 1}\binom{m}{k - r}P(k - 1, k - 1)\right\]\left\[\binom{n - r + 1}{1}\right\]\left\[P(m + n - k, m + n - k)\right\] = $  
$\frac{r\binom{m}{k - r}\left\[\frac{n!}{r!(n - r)!}\right\]}{k\left\[\frac{(m + n)!}{k!(m + n - k)!}\right\]} = \frac{r\binom{n}{r}\binom{m}{k - r}}{k\binom{m + n}{k}}$

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

# Chapter 3
## 條件機率
1. 任意事件的機率值應該要隨著新資訊的獲得而改變
1. 數學定義 : 給定兩個事件$A, B \subseteq \Omega$，在給定事件A之下發生B的條件機率為$P(B &#124; A) = \frac{P(AB)}{P(A)}$
1. 數學定義 : 給定兩個事件$A, B \subseteq \Omega$，在事件A發生之下發生B的條件機率為$P(B &#124; A) = \frac{P(AB)}{P(A)}$
   - 必要條件$P(A) \neq 0$
   - 傳統方法 : $P(B &#124; A) = \frac{(\\# AB) / (\\# \Omega)}{(\\# A) / (\\# \Omega)} = \frac{\\# AB}{\\# A}$
1. 在給定事件A發生的狀況下
1. 在事件A發生的狀況下
   - 樣本空間$\Omega \rightarrow A$
   - 事件$B \rightarrow AB$
1. 條件機率$P(\cdot &#124; A)$可以視作是一個定義在$2^{\Omega}$上的機率測度
   - 滿足機率3公理
   - 滿足所有第二章推導出來的機率測度的重要特性

## 條件機率公式
1. $P(AB) = P(A)P(B &#124; A)$
1. $P(B) = P(A)P(B &#124; A) + P(A^{c})P(B &#124; A^{c})$
1. $P(A &#124; B) = \frac{P(A)P(B &#124; A)}{P(A)P(B &#124; A) + P(A^{c})P(B &#124; A^{c})}$
1. 若$P(A) = P(B)$，則$P(A &#124; B) = P(B &#124; A)$
1. $P(\bigcap_{i = 1}^{m}A_{i}) = P(A_{1})P(A_{2} &#124; A_{1})P(A_{3} &#124; A_{1}A_{2})\cdots P(A_{m} &#124; A_{1}A_{2}\cdots A_{m - 1})$
1. 給定一組樣本空間的分割$A_{1}, \cdots, A_{m}$，則$P(B) = \sum_{i = 1}^{m}P(A_{i})P(B &#124; A_{i})$
1. 貝氏定理 : 給定一組樣本空間的分割$A_{1}, \cdots, A_{m}$，則$P(A_{j} &#124; B) = \frac{P(A_{j})P(B &#124; A_{j})}{\sum_{i = 1}^{m}P(A_{i})P(B &#124; A_{i})}$

## 貝氏方法
1. 事前機率$P(A_{j})$ : 通過假設得到(主觀機率)
1. 事後機率$P(A_{j} &#124; B)$ : 蒐集數據之後透過貝氏定理得到
1. 貝氏定理告訴我們在得到一些新資訊之後要如何更新最初假設的主觀機率

## 重要範例
1. Diagnostic Test
   - $D$表示得病的事件
   - $E$表示檢測過後顯示得病的事件
   - 假設$P(D) = 0.001, P(E &#124; D) = 0.98, P(E &#124; D^{c}) = 0.01$
     1. $P(E) = P(D)P(E &#124; D) + P(D^{c})P(E &#124; D^{c}) = 0.01097$
     1. $P(D &#124; E) = \left\(\frac{P(D)}{P(E)}\right\)P(E &#124; D) \approx 0.0893$
     1. 因為病本身很罕見所以即便$P(E &#124; D) = 0.98$與$P(E &#124; D^{c})$看起來都不錯但是減設有病之後有病的機率還是很低
     1. 即便條件機率看起來依舊很低，但是在得到新資訊之後可能有病的可能性$P(D &#124; E)$與原本的機率$P(D)$相比依舊提升許多
     1. $P(E &#124; D^{c})$稱作偽陽性率(false positive rate)
     1. $P(E^{c} &#124; D)$稱作偽陰性率(false negative rate)

1. Gold coin
   - 問題描述
     1. 有3個盒子
     1. 第1個盒子有2枚銀幣
     1. 第2個盒子有1個金幣1個銀幣
     1. 第3個盒子有2個金幣
     1. 實驗如下 : 先隨機選擇1個盒子，然後隨機選取盒內的硬幣
     1. 假設已知第1個硬幣是金幣的情況下拿到第k個盒子的機率為?
   - $A_{k}$表示第$k$個盒子被選擇到的事件
   - $B$表示拿到的是金幣的事件
   - $P(A_{1} &#124; B) = \frac{(1 / 3) \times 0}{\[0 + (1 / 2) + 1\] \times (1 / 3)} = 0$
   - $P(A_{2} &#124; B) = \frac{(1 / 3) \times (1 / 2)}{\[0 + (1 / 2) + 1\] \times (1 / 3)} = \frac{1}{3}$
   - $P(A_{1} &#124; B) = \frac{(1 / 3) \times 1}{\[0 + (1 / 2) + 1\] \times (1 / 3)} = \frac{2}{3}$

## 課本習題 
### 解題心得
### PROBLEMS
### THEORETICAL EXERCISES
### SELF-TEST PROBLEMS AND EXERCISES

# Chapter 4
# Chapter 5
# Chapter 6
# Chapter 7

## 重要範例
## 課本習題 
### 解題心得
### PROBLEMS
### THEORETICAL EXERCISES
### SELF-TEST PROBLEMS AND EXERCISES