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
1. $P(\bigcap_{i = 1}^{m}A_{i}) = P(A_{1}) \times P(A_{2} &#124; A_{1}) \times $  
$P(A_{3} &#124; A_{1}A_{2}) \times \cdots \times P(A_{m} &#124; A_{1}A_{2}\cdots A_{m - 1})$
1. 給定一組樣本空間的分割$A_{1}, \cdots, A_{m}$，則$P(B) = \sum_{i = 1}^{m}P(A_{i})P(B &#124; A_{i})$
1. 貝氏定理 : 給定一組樣本空間的分割$A_{1}, \cdots, A_{m}$，則$P(A_{j} &#124; B) = \frac{P(A_{j})P(B &#124; A_{j})}{\sum_{i = 1}^{m}P(A_{i})P(B &#124; A_{i})}$

## 貝氏方法
1. 通過假設得到(主觀機率)事前機率$P(A_{j})$
1. 觀查得到新資訊 - 事件$B$發生
1. 透過理論分析得到條件機率$P(B &#124; A_{j})$與$P(B &#124; A_{j}^{c})$
1. 透過貝氏定理導出事後機率$P(A_{j} &#124; B)$

## 賠率(odds)與條件賠率
1. 事件$A$的賠率的定義 : $o(A) \equiv \frac{P(A)}{P(A^{c})} = \frac{P(A)}{1 - P(A)}$
1. $P(A) = \frac{o(A)}{1 + o(A)}$
1. 條件賠率$o(B &#124; A) \equiv \frac{P(B &#124; A)}{P(B^{c} &#124; A)} = o(B) \times \frac{P(A &#124; B)}{P(A &#124; B^{c})}$

## 獨立事件
1. 定義
   - 若兩個事件$A,B$為獨立事件，則$P(AB) = P(A)P(B)$
1. 重要特性
   - $\[P(B &#124; A) = P(B)\] \equiv \[P(AB) = P(A)P(B)\] $  
   $\equiv \[P(A &#124; B) = P(A)\]$
   - 若兩個事件$A,B$為獨立事件，則事件$A^{c},B$也為獨立事件
   - 若$P(B &#124; A) > P(B)$，則$P(B &#124; A^{c}) < P(B)$
   - $P(B)$一定會介於$P(B &#124; A)$與$P(B &#124; A^{c})$之間
   - 兩個機率值都不為$0$的互斥的事件$A, B$必定是相依事件
1. 對於多個事件$A_{1}, \cdots, A_{n}$的推廣
   - 兩倆(pairwise)獨立 : 對於任意的$1 \leq i < j \leq n$,滿足$P(A_{i}A_{j}) = P(A_{i})P(A_{j})$
   - 相互(mutually)獨立 : 對於任意的$2 \leq k\leq n$與$1 \leq i_{1} < \cdots < i_{k} \leq n$,滿足$P(A_{i_{1}} \cdots A_{i_{k}}) = P(A_{i_{1}}) \cdots P(A_{i_{k}})$
   - 相互獨立的條件 比兩倆獨立更嚴格
   - 給定一系列的事件$A_{1}, \cdots, A_{n}$，以下兩件事等價
     1. $A_{1}, \cdots, A_{n}$是一系列相互獨立的事件
     1. $P(B_{1} \cdots B_{n}) = P(B_{1}) \cdots P(B_{n})$，其中$B_{i}$可以是$A_{i}$或$A_{i}^{c}$
   - 給定一系列的事件$A_{1}, \cdots, A_{n}$且$B_{1}, \cdots, B_{m}$是一系列由互斥子集做交集或聯集所形成的事件序列，則$B_{1}, \cdots, B_{m}$是互相獨立的事件序列
     1. ex : $A_{1}, \cdots, A_{5} \Rightarrow B_{1} = A_{1} \cup A_{2}$, $B_{2} = A_{3}A_{4}A_{5}$
     1. 這個等式最重要的解釋是如果事件是相互獨立，那麼在計算由這些事件做交集或聯集所成的事件的機率時，我們可以先算出局部集合的機率再與其他事件一起計算

## 條件獨立
1. 定義
   - 給定3個事件$A$與$B_{1}, B_{2}$
   - 若$B_{1}$與$B_{2}$在$A$發生的條件下為獨立事件，則$P(B_{1}B_{2} &#124; A) = P(B_{1} &#124; A)P(B_{2} &#124; A)$
   - $\[P(B_{1}B_{2} &#124; A) = P(B_{1} &#124; A)P(B_{2} &#124; A)\] \equiv $  
   $\[P(B_{1}&#124; B_{2} A) = P(B_{1} &#124; A)\]$

## 重要範例
1. Diagnostic Test
   - $D$表示得病的事件
   - $E$表示檢測過後顯示得病的事件
   - 假設$P(D) = 0.001, P(E &#124; D) = 0.98, $  
   $P(E &#124; D^{c}) = 0.01$
     1. $P(E) = P(D)P(E &#124; D) + P(D^{c})P(E &#124; D^{c}) = $  
     $0.01097$
     1. $P(D &#124; E) = \left\(\frac{P(D)}{P(E)}\right\)P(E &#124; D) \approx 0.0893$
     1. 因為病本身很罕見所以即便$P(E &#124; D) = 0.98$與$P(E &#124; D^{c})$看起來都不錯但是減設有病之後有病的機率還是很低
     1. 即便條件機率看起來依舊很低，但是在得到新資訊之後可能有病的可能性$P(D &#124; E)$與原本的機率$P(D)$相比依舊提升許多
     1. $P(E &#124; D^{c})$稱作偽陽性率(false positive rate)
     1. $P(E^{c} &#124; D)$稱作偽陰性率(false negative rate)

1. Gold coin
   - 問題描述
     1. 有$3$個盒子
     1. 第$1$個盒子有$2$枚銀幣
     1. 第$2$個盒子有$1$個金幣$1$個銀幣
     1. 第$3$個盒子有$2$個金幣
     1. 實驗如下 : 先隨機選擇$1$個盒子，然後隨機選取盒內的硬幣
     1. 假設已知第$1$個硬幣是金幣的情況下拿到第k個盒子的機率為?
   - 解法
     1. $A_{k}$表示第$k$個盒子被選擇到的事件
     1. $B$表示拿到的是金幣的事件
     1. $P(A_{1} &#124; B) = \frac{(1 / 3) \times 0}{\[0 + (1 / 2) + 1\] \times (1 / 3)} = 0$
     1. $P(A_{2} &#124; B) = \frac{(1 / 3) \times (1 / 2)}{\[0 + (1 / 2) + 1\] \times (1 / 3)} = \frac{1}{3}$
     1. $P(A_{1} &#124; B) = \frac{(1 / 3) \times 1}{\[0 + (1 / 2) + 1\] \times (1 / 3)} = \frac{2}{3}$

1. Draw one card from a standard deck
   - 問題描述
     1. 從一副標準的撲克牌抽1張卡
     1. 事件$A$ : 抽到黑桃或梅花
     1. 事件$B$ : 抽到愛心或梅花
     1. 事件$C$ : 抽到方塊或梅花
   - 這3個事件兩倆獨立，但不是相互獨立
     1. $P(AB) = P(AC) = P(BC) = $  
     $\frac{1}{4} = \left\(\frac{1}{2}\right\)\left\(\frac{1}{2}\right\) = $  
     $P(A)P(B) = P(A)P(C) = P(B)P(C)$
     1. $P(ABC) = \frac{1}{4} \neq \frac{1}{8} = P(A)P(B)P(C)$

1. Gold coin(Generalization)
   - 問題描述
     1. 有$k + 1$個盒子
     1. 第$i$個盒子有i個金幣與$k - i$枚銀幣($0 \leq i \leq k$)
     1. 實驗如下 : 先隨機選擇$1$個盒子，然後隨機選取盒內的硬幣(抽出要放回去)
     1. 假設已經連續抽出$n$個金幣，下一個仍然抽出金幣的機率為?
   - 解法
     1. $A_{i}$表示挑到第$i$個盒子
     1. $B$代表已經連續抽到$n$個金幣
     1. $C$代表第$n+1$次是抽到金幣
     1. $P(C &#124; B) = \sum_{i = 0}^{k}P(A_{i} &#124; B)P(C &#124; A_{i}B)$
     1. $B$與$C$在$A_{i}$發生的條件下獨立，因此$P(C &#124; A_{i}B) = P(C &#124; A_{i}) = \frac{i}{k}$
     1. $P(A_{i} &#124; B) = \frac{P(A_{i})P(B &#124; A_{i})}{\sum_{j = 0}^{k}P(A_{j})P(B &#124; A_{j})} = $  
     $\frac{\[1 / (k + 1)\](i / k)^{n}}{\sum_{j = 1}^{k} \[1 / (k + 1)\](j / k)^{n}}$
     1. 因此$P(C &#124; B) = \frac{\sum_{i = 0}^{k}(i / k)^{n + 1}}{\sum_{i = 0}^{k}(i / k)^{n}}$

## 心得
1. 善用條件機率是改變樣本空間大小的直覺
1. 等式推導有兩個主要常用的方法
   - 互斥分割
   - 計算過程中大多是使用交集，如果是要計算聯集可使用補集手段做轉換

## 課本習題
### PROBLEMS
2  
- $i = 2$ : $0$  
$i = 3$ : $0$  
$i = 4$ : $0$  
$i = 5$ : $0$  
$i = 6$ : $0$  
$i = 7$ : $\frac{1}{6}$  
$i = 8$ : $\frac{1}{5}$  
$i = 9$ : $\frac{1}{4}$  
$i = 10$ : $\frac{1}{3}$  
$i = 11$ : $\frac{1}{2}$  
$i = 12$ : $1$  

4
- $i = 2$ : $0$  
$i = 3$ : $0$  
$i = 4$ : $0$  
$i = 5$ : $0$  
$i = 6$ : $0$  
$i = 7$ : $\frac{2}{6}$  
$i = 8$ : $\frac{2}{5}$  
$i = 9$ : $\frac{2}{4}$  
$i = 10$ : $\frac{2}{3}$  
$i = 11$ : $\frac{2}{2}$  
$i = 12$ : $1$  

6
- (with replacement) : $\frac{2}{4}$
- (without replacement) : $\frac{2}{4}$

10
- $\frac{11}{50}$

21-(a)
- $\frac{212 + 36}{212 + 36 + 198 + 54} = \frac{248}{500}$

21-(b)
- $\frac{54}{198 + 54} = \frac{54}{252}$

21-(c)
- $\frac{36}{212 + 36} = \frac{36}{248}$

23-(a)
- $W$ : white ball in urn 1 is selected  
$R$ : red ball in urn 1 is selected  
$E$ : select a white ball from urn 2
- $P(E) = P(E &#124; W)P(W) + P(E &#124; R)P(R) = $  
$\left\(\frac{2}{3}\right\)\left\(\frac{1}{3}\right\) + \left\(\frac{1}{3}\right\)\left\(\frac{2}{3}\right\) = \frac{4}{9}$

23-(b)
- $P(W &#124; E) = P(E &#124; W)\left\(\frac{P(W)}{P(E)}\right\) = \left\(\frac{2}{3}\right\)\left\(\frac{1/3}{4/9}\right\) = \frac{2}{4}$

25
- $A$ : a person's age is over 50  
$B$ : a person is walk along street
- According to hint :  
$P(A) = p$, $P(B &#124; A^{c}) = \alpha_{1}$  
$P(B &#124; A) = \alpha_{2}$
- This method get an estimate for $P(A &#124; B)$
- $P(A &#124; B) = \frac{P(B &#124; A)P(A)}{P(B &#124; A)P(A) + P(B &#124; A^{c})P(A^{c})} = \frac{\alpha_{2}p}{\alpha_{2}p + \alpha_{1}(1 - p)}$
- This method hopes $P(A &#124; B) = P(A)$
- $\left\[p = \frac{\alpha_{2}p}{\alpha_{2}p + \alpha_{1}(1 - p)}\right\] \equiv \left\[\alpha_{2} = \alpha_{2}p + \alpha_{1}(1 - p)\right\] \equiv \left\[\alpha_{2} = \alpha_{1}\right\]$

33-(a)
- $1 - [(0.7)(0.3) + (0.3)(0.1)] = 1 - 0.24 = 0.76$

33-(b)
- $\frac{(0.7)(1 - 0.3)}{0.76} = \frac{49}{76}$

36
- $W$ : the person is woman  
$A$ : the resignation person belongs to store A  
$B$ : the resignation person belongs to store B  
$C$ : the resignation person belongs to store C
- According to the problem statement :  
$P(A &#124; W) = P(A)$  
$P(B &#124; W) = P(B)$  
$P(C &#124; W) = P(C)$  
- $P(C &#124; W) = P(C) = \frac{(0.7)(100 / 225)}{(0.5)(50 / 225) + (0.6)(75 / 225) + (0.7)(100 / 225)}$

39
- $A$ : a person is accident prone  
$A_{1}$ : 1st year has accident  
$A_{2}$ : 2nd year has accident
- $P(A_{2} &#124; A_{1}^{c}) = \frac{P(A_{2}A_{1}^{c})}{P(A_{1}^{c})} = \frac{P(A_{2}A_{1}^{c} &#124; A)P(A) + P(A_{2}A_{1}^{c} &#124; A^{c})P(A^{c})}{P(A_{1}^{c} &#124; A)P(A) + P(A_{1}^{c} &#124; A^{c})P(A^{c})} = $  
$\frac{P(A_{2} &#124; A)P(A_{1}^{c} &#124; A)P(A) + P(A_{2} &#124; A^{c})P(A_{1}^{c} &#124; A^{c})P(A^{c})}{P(A_{1}^{c} &#124; A)P(A) + P(A_{1}^{c} &#124; A^{c})P(A^{c})} = $  
$\frac{(0.4)(0.6)(0.3) + (0.2)(0.8)(0.7)}{(0.6)(0.3) + (0.8)(0.7)} = \frac{184}{740}$

40-(a)
- $W_{1}$ : draw white ball at 1st  
$W_{2}$ : draw white ball at 2nd  
$W_{3}$ : draw white ball at 3rd  
$E_{0}$ : $0$ white ball in these 3 sample
- $P(E_{0}) = P(W_{1}^{c}W_{2}^{c}W_{3}^{c}) = P(W_{3}^{c} &#124; W_{1}^{c}W_{2}^{c})P(W_{2}^{c} &#124; W_{1}^{c})P(W_{1}^{c}) = $  
$\left\(\frac{9}{15}\right\)\left\(\frac{8}{13}\right\)\left\(\frac{7}{12}\right\)$

40-(b)
- $E_{1}$ : $0$ white ball in these 3 sample
- $P(E_{1}) = P(W_{1}^{c}W_{2}^{c}W_{3}) + P(W_{1}^{c}W_{2}W_{3}^{c}) + P(W_{1}W_{2}^{c}W_{3}^{c}) = $  
$P(W_{3} &#124; W_{1}^{c}W_{2}^{c})P(W_{2}^{c} &#124; W_{1}^{c})P(W_{1}^{c}) + $  
$P(W_{3}^{c} &#124; W_{1}^{c}W_{2})P(W_{2} &#124; W_{1}^{c})P(W_{1}^{c}) + $  
$P(W_{3}^{c} &#124; W_{1}W_{2}^{c})P(W_{2}^{c} &#124; W_{1})P(W_{1}) = $  
$\left\(\frac{5}{14}\right\)\left\(\frac{8}{13}\right\)\left\(\frac{7}{12}\right\) + \left\(\frac{8}{14}\right\)\left\(\frac{5}{13}\right\)\left\(\frac{7}{12}\right\) + \left\(\frac{8}{14}\right\)\left\(\frac{7}{13}\right\)\left\(\frac{5}{12}\right\)$

40-(c)
- $E_{2}$ : $0$ white ball in these 3 sample
- $P(E_{2}) = P(W_{1}W_{2}W_{3}^{c}) + P(W_{1}W_{2}^{c}W_{3}) + P(W_{1}^{c}W_{2}W_{3}) = $  
$P(W_{3}^{c} &#124; W_{1}W_{2})P(W_{2} &#124; W_{1})P(W_{1}) + $  
$P(W_{3} &#124; W_{1}W_{2}^{c})P(W_{2}^{c} &#124; W_{1})P(W_{1}) + $  
$P(W_{3} &#124; W_{1}^{c}W_{2})P(W_{2} &#124; W_{1}^{c})P(W_{1}^{c}) = $  
$\left\(\frac{7}{14}\right\)\left\(\frac{6}{13}\right\)\left\(\frac{5}{12}\right\) + \left\(\frac{6}{14}\right\)\left\(\frac{7}{13}\right\)\left\(\frac{5}{12}\right\) + \left\(\frac{6}{14}\right\)\left\(\frac{5}{13}\right\)\left\(\frac{7}{12}\right\)$

40-(d)
- $E_{3}$ : $0$ white ball in these 3 sample
- $P(E_{3}) = P(W_{1}W_{2}W_{3}) = P(W_{3} &#124; W_{1}W_{2})P(W_{2} &#124; W_{1})P(W_{1}) = $  
$\left\(\frac{7}{14}\right\)\left\(\frac{6}{13}\right\)\left\(\frac{5}{12}\right\)$

43
- 
48
- 
65
- 
67
- 
69
- 
72
- 
89
- 
### THEORETICAL EXERCISES
1
- 
4
- 
5
- 
9
- 
18
- 
21
- 
### SELF-TEST PROBLEMS AND EXERCISES
5
- 
7
- 
13
- 
12
- 
17
- 
28
- 