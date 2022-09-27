---
id: iqrxok09sbvykmc3cjsn4me
title: Compare tax on investment VN vs US
desc: ''
updated: 1653524936097
created: 1651971908547
excerpt: >-
  Mô hình so sánh mức thuế trên thu nhập từ đầu tư cổ phiếu giữa hai nước VN và
  US
published: true
---
# Compare tax on investment VN vs US

## Remind of tax policy on investment

### in Vietnam

![[notes.reading.tax-investors-vn#key-takeaway,1:#*]]

### in US

![[notes.reading.tax-investors-us#notes-from-reading,1:#*]]

## Preparations

### Annotations:

- dividend: $D = D_O + D_Q$
    - ordinary dividend: $D_O$
    - qualified dividend: $D_Q$
    - dividend annual rate: $r_d$
- capital gain: $G = V_t-V_0 = \big[(1+r)^t-1\big]V_0$
    - Investment value at year 0 (initial time): $V_0$
    - Investment value at year t (selling time): $V_t=(1+r)^tV_0$
    - annual return: $r$

### Assumptions:

- long term buy and hold strategy only
- Initial investment value $V_0$ is in USD
- portfolio growth is constantly positive
- US tax situation: 
    - Single tax filling, 
    - annual income $90k, 
    - federal income tax rate 24%, 
    - state income tax rate (California) 9.30%, 
    - federal income tax rate for ordinary dividend 24%, 
    - federal income tax rate for qualified dividend 15%
    - no short term capital gain
- constant dividend distribution:
    - qualified dividend: $D_Q = 0.4D$
    - ordinary dividend: $D_O = 0.6D$
- constant dividend annual rate: $r_d = 3\%$
- constant capital annual rate of return: $r = 12\%$

## Formulate the concept

### Dividends

Dividends at:
- Initial: $D_0 = r_dV_0$
- Year 1: $D_1 = r_dV_1 = r_d(1+r)V_0$
- Year 2: $D_2 = r_dV_2 = r_d(1+r)^2V_0$
- Year t: $D_t = r_dV_t = r_d(1+r)^tV_0$

Sum of dividends received at year t:

$$
\begin{align}
D &= \sum_{i=1}^{t}{D_i} \\
&= r_d\Big[1 + (1+r) + ... + (1+r)^t\Big]V_0
\end{align}
$$

Applying the formula of [sum of a geometric series](https://saylordotorg.github.io/text_intermediate-algebra/s12-03-geometric-sequences-and-series.html):

$$
\begin{align}
D &= r_d\Big[\frac{1-(1+r)^t}{1-(1+r)}\Big]V_0 \\
&= \frac{r_d}{r}\Big[(1+r)^t-1\Big]V_0
\end{align}
$$
  
### Tax in Vietnam

$$
\begin{align}
T_{VN} &= 0.05D + 0.001V_t \\
&= 0.05D + 0.001(1+r)^tV_0 \\
&= 0.05\frac{r_d}{r}\Big[(1+r)^t-1\Big]V_0 + 0.001(1+r)^tV_0 \\
&= \Big[0.05(1+r)^t(\frac{r_d}{r}+0.001)-0.05\frac{r_d}{r}\Big]V_0
\end{align}
$$

- Applying the assumption:
    - constant dividend annual rate: $r_d = 3\%$
    - constant capital annual rate of return: $r = 12\%$

$$
\begin{align}
T_{VN} &= (0.0135*1.12^t - 0.0125)V_0 \\
&= 0.0125(1.08*1.12^t - 1)V_0
\end{align}
$$

### Tax in U.S.

#### Federal tax
$$
\begin{align}
T_F &= T_C + T_{DO} + T_{DQ} \\
&= 0.2G + 0.204D
\end{align}
$$

where
- long term capital gain tax: $T_C = 20\%G$
- tax for ordinary dividend: $T_{DO} = 24\%D_O = 0.24*0.6D = 0.144D$
- tax for qualified dividend: $T_{DQ} = 15\%D_Q = 0.15*0.4D = 0.06D$

#### State tax (California) 

$$
\begin{align}
T_S &= 9.3\%(G + D_O + D_Q) \\
&= 0.093(G + D)
\end{align}
$$

#### Total tax bill in US

$$
\begin{align} 
T_{US} &= T_F + T_S \\
&= 0.293G + 0.297D \\
&= 0.293\Big[(1+r)^t-1\Big]V_0 + 0.297\frac{r_d}{r}\Big[(1+r)^t-1\Big]V_0 \\
&= \Big[(1+r)^t-1\Big](0.293 + 0.297\frac{r_d}{r})V_0
\end{align}
$$

- Applying the assumption $r_d = 3\%$, $r = 12\%$

$$
T_{US} = 0.36725(1.12^t-1)V_0
$$

## Comparison

Now we compare the tax bill $T_{US}$ with its equivalent $T_{VN}$ to understand which is more beneficial for investor after how many years ($t$) and with how much initial investment value ($V_0$).

$$
T_{US} = 0.36725(1.12^t-1)V_0
$$

$$
T_{VN} = 0.0125(1.08*1.12^t - 1)V_0
$$

### Visualization

View code and visuals in my [Deepnote](https://deepnote.com/workspace/huy-f7e5bafc-3b5f-4e8e-86f0-50e9b599d9b9/project/comparetax-de6e2d11-321b-4c63-95bb-4cf14b2c868b/%2Fnotebook.ipynb).

As shown in figure below,
- The current Tax VN policy is always better for investor, under the assumption that
    - investment value increases in general
    - investor is lazy with long term buy and hold strategy
- Tax VN = Tax US when
    - initial investment $V_0 = 0$
    - or year $t = -20$

![tax-compare](https://ik.imagekit.io/casa/h7b-dendron/Screenshot_2022-05-18_195315_OajCY9rjFs.jpg?ik-sdk-version=javascript-1.4.3&updatedAt=1652896465225){max-width: 300px, display: block, margin: 0 auto}

## Conclusion

- Surprisingly, with the simple and strict assumption as mentioned above, the tax bill of an investor in VN will be much less than the one in US
- However, my previous statement will be absolutely meaningless (or wrong) if investors trade frequently. Because the VN tax policy does not take into account of investor's loss.