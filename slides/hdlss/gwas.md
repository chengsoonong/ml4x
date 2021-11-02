---
marp: true
title: High dimension low sample size
author: Cheng Soon Ong
theme: gaia
class: invert
---

<style>
.container{
    display: flex;
}
.colbig{
    flex: 70%;
}
.colsmall{
    flex: 30%;
}
.col{
    flex: 1;
}
.highlight{
    color: lightcoral;
}
.cite{
    color: dodgerblue;
}
.footnote{
    color: dodgerblue;
    font-size: 70%;
}
.dna{
    color: lightseagreen;
    font-family: "Times New Roman", Times, serif;
    font-weight: bold;
    font-size: 120%;
}
</style>



<!-- _class: lead -->

# High dimension low sample size
## (for studying genomes)

<span class="highlight">Cheng Soon</span> Ong


---

## Why we will always have too many features

---

## Fundamental theorem of linear algebra


---

<!-- _class: lead -->

# A glimpse of genomics

http://www.ong-home.my/download/notes-gwas-hypo-test.pdf

---

# Genomics (I)

- **SNP**
    <span class="highlight">Single Nucleotide Polymorphisms</span> or
    single nucleotide variations (SNVs) are mutations on a single
    nucleotide (A,C,T or G) in the genome.
    For example: <span class="dna">AAGC</span> <span class="highlight">C</span> <span class="dna">TA</span> to <span class="dna">AAGC</span> <span class="highlight">T</span> <span class="dna">TA</span>.
- **Alleles**
    There are two <span class="highlight">alleles</span>: e.g. C and T.

---

# Genomics (II)

- **Major/Minor allele**
    The nucleotide that occurs commonly in the population is called the
    <span class="highlight">major allele</span> (denoted by a capital $B$) and the nucleotide
    that occurs more rarely is called the <span class="highlight">minor allele</span> (denoted
    by a small letter $b$).
- **Diploid**
    <span class="highlight">haploid</span> $\Longrightarrow$ one chromosome set
    <span class="highlight">diploid</span> $\Longrightarrow$ two chromosome sets
    <span class="highlight">hexaploid</span> $\Longrightarrow$ six chromosome sets

---

# Genome wide association study

- **Genotype**
    The <span class="highlight">genotype</span> is the specific combination of alleles.
- **Phenotype**
    The <span class="highlight">phenotype</span> is the observable trait or characteristic of an individual, for example whether the individual is healthy or sick.
- **Case-control studies**
    A cohort of sick individuals (<span class="highlight">cases</span>) and healthy individuals (<span class="highlight">controls</span>) are genotyped and their corresponding binary phenotype are recorded.

---

<!-- _class: lead -->

# Statistical hypothesis testing

---

# Why Hypothesis Tests?
- Given a case control study, test whether a particular SNP is associated with the phenotype.
- Look through each SNP one by one, and test to see if there is a difference in the frequency of the alleles seen in cases versus controls.
- If difference is statistically significant
    $\Longrightarrow$
    SNP is associated with the phenotype.

![bg right:30%](figs-hypotest/case-control.png)

---

# General framework (I)
- **null hypothesis $\mathcal{H}_0$**
    genotype is <span class="highlight">independent</span> of the phenotype
- **alternative hypothesis $\mathcal{H}_1$**
    SNP is <span class="highlight">associated</span> with the disease state
- **hypothesis test** can be stated as follows
    $$
    \mathcal{H}_0: \theta \in \Theta_0
    \qquad\mathrm{and}\qquad
    \mathcal{H}_1: \theta \in \Theta_1.
    $$
---

# General framework (II)
- **Important design choices**
    - How to represent intuition as a probabilistic model?
    - How to decide on a test statistic?
    - What is the distribution of the random variable?
    - What is the level of significance ($\alpha$)?

<div class="cite">

- Sinsheimer, Statistics 101 -- A Primer for the Genetics of Complex Human Disease, 2011
- Agresti, Categorical Data Analysis, 2002
- Wasserman, All of Statistics, 2004
</div>

---

# Hypothesis test

- Let $X$ be a random variable with range $\mathcal{X}$.
- $R\subset\mathcal{X}$ called the rejection region
- If $X\in R$ then we reject the null hypothesis, otherwise we do not reject the null hypothesis.
    $$
    R = \left\{ x:T(x) > c \right\}
    $$
    where $T$ is a <span class="highlight">test statistic</span> and $c$ is a critical value.
- The <span class="highlight">p-value</span> is the probability of obtaining a test statistic at least as extreme as the one that was actually observed, assuming that the null hypothesis is true.

--- 

# Outcomes (I)

- **Outcomes of hypothesis tests**

    |        | Accept $\mathcal{H}_0$ | Reject $\mathcal{H}_0$ |
    |:-------|:----------------------:|:----------------------:|
    | $\mathcal{H}_0$ true | correct | type I error |
    | $\mathcal{H}_1$ true | type II error | correct|

- **Significance level**
    The probability of a rejecting $\mathcal{H}_0$ when it is true is called the <span class="highlight">significance level</span>.

![bg right:35% 100%](figs-hypotest/significance-level.jpg)

--- 

# Outcomes (II)

- **p-value vs significance**
    - Reject $\mathcal{H}_0$ when 
        p-value $<$ significance level
    - p-value is computed from observation
    - significance level is chosen by expert

![bg right:35% 100%](figs-hypotest/significance-level.jpg)

---

# Allelic test of association

<div class="container">

<div class="col">

- Single locus, haploid genome
- 200 individuals: 100 cases, 100 controls
- $B$ and $b$ are equally common in the population
- **Null hypothesis**
    <span class="highlight">No association between the allele and the phenotype</span>

</div>
<div class="col">

|        | allele $B$ | allele $b$ |
|:-------|:----------:|:----------:|
| Case | 50 | 50 |
| Control | 50 | 50 |

</div>
</div>

---

# Allelic test of association

<div class="container">

<div class="col">

- Single locus, haploid genome
- 200 individuals: 100 cases, 100 controls
- $B$ and $b$ are equally common in the population
- **Null hypothesis**
    <span class="highlight">No association between the allele and the phenotype</span>

</div>
<div class="col">

|        | allele $B$ | allele $b$ |
|:-------|:----------:|:----------:|
| Case | 50 ($E_{B,1}$) | 50 ($E_{b,1}$) |
| Control | 50 ($E_{B,0}$) | 50 ($E_{b,0}$) |

Let's name the variables
</div>
</div>

---

# Experimental Observation

![bg right:40% 120%](figs-hypotest/case-control.png)

We go out and measure some genotypes, and observe...

|        | allele $B$ | allele $b$ |
|:-------|:----------:|:----------:|
| Case | 23 ($O_{B,1}$) | 77 ($O_{b,1}$) |
| Control | 68 ($O_{B,0}$) | 32 ($O_{b,0}$) |


---

# Pearson $\chi^2$ test of independence

<span class="highlight">Is the expected table ($E_{v,i}$) and the observed table ($O_{v,i}$)
"the same"?</span>

Calculate their normalized distance:
$$
  X^2 = \sum_{i\in \{0,1\}}\sum_{v\in \{B,b\}}\frac{ (O_{v,i}-E_{v,i})^2} {E_{v,i}}.
$$

---

# Chi squared distribution

![bg right:30% 100%](figs-hypotest/chi-square-pdf.png)

$$
  f(x;k) =
  \begin{cases}
    \frac{\displaystyle
      x^{\left(\frac{k}{2}-1\right)}\exp\left(-\frac{x}{2}\right)}{\displaystyle
      2^{\left(\frac{k}{2}\right)}\Gamma\left(\frac{k}{2}\right)},
    &\qquad x\geqslant 0\\
    0&\qquad\mathrm{otherwise}
  \end{cases}
$$

where $k$ is called the degrees of freedom

http://en.wikipedia.org/wiki/Chi-squared_distribution

---

# $\chi^2$ test (I)

<div class="container">

<div class="col">

|        | allele $B$ | allele $b$ |
|:-------|:----------:|:----------:|
| Case | 50 ($E_{B,1}$) | 50 ($E_{b,1}$) |
| Control | 50 ($E_{B,0}$) | 50 ($E_{b,0}$) |

</div>
<div class="col">

|        | allele $B$ | allele $b$ |
|:-------|:----------:|:----------:|
| Case | 23 ($O_{B,1}$) | 77 ($O_{b,1}$) |
| Control | 68 ($O_{B,0}$) | 32 ($O_{b,0}$) |

</div>
</div>

$$
\begin{aligned}
    X^2&=
    \displaystyle\frac{(23-50)^2}{50}+\frac{(77-50)^2}{50}+\frac{(68-50)^2}{50}+\frac{(32-50)^2}{50}\\\\
    &=42.12
\end{aligned}
$$


---

# $\chi^2$ test (II)

<div class="container">

<div class="col">

|        | allele $B$ | allele $b$ |
|:-------|:----------:|:----------:|
| Case | 50 ($E_{B,1}$) | 50 ($E_{b,1}$) |
| Control | 50 ($E_{B,0}$) | 50 ($E_{b,0}$) |

</div>
<div class="col">

|        | allele $B$ | allele $b$ |
|:-------|:----------:|:----------:|
| Case | 23 ($O_{B,1}$) | 77 ($O_{b,1}$) |
| Control | 68 ($O_{B,0}$) | 32 ($O_{b,0}$) |

</div>
</div>

What is the probability of observing a value greater than 42.12 of a
$\chi^2$ random variable given that the null hypothesis is true? <span class="highlight">p-value</span>
$$
    \mathbb{P}(X^2 > 42.12) < 10^{-10}.
$$

---

# The p-value is not ...

- ... the probability that the null hypothesis is true.
-  ... the probability that a finding is ``merely a fluke''.
-  ... the probability of falsely rejecting the
  null hypothesis.
-  ... the probability that a replicating
  experiment would not yield the same conclusion.
-  ... indicating the size or importance of the
  observed effect.
-  The significance level of the test is not determined by the p-value.

---


<div class="container">

<div class="colsmall">

# Jelly beans cause acne?

https://xkcd.com/882/

</div>
<div class="colbig">

![height:250px](figs-hypotest/xkcd-significant-top.png)

![height:300px](figs-hypotest/xkcd-significant-middle.png) &emsp; &emsp; &emsp; &emsp; &emsp;  ![height:300px](figs-hypotest/xkcd-significant-bottom.png)

</div>
</div>

---


# Family wise error rate (FWER)

- **$M$ hypothesis tests**
    $$
    \mathcal{H}_{0m}\qquad\mathrm{versus}\qquad\mathcal{H}_{1m},\qquad m=1,\ldots,M
    $$
    and let $p_1,\ldots,p_M$ denote the $M$ p-values for these tests.
- **Bonferroni Method**  &emsp;  Reject null hypothesis $H_{0m}$ if
    $$
    p_m < \displaystyle\frac{\alpha}{M}.
    $$
- **Outcome**
    The probability of falsely rejecting any null hypothesis is less than
    or equal to $\alpha$.


---

# False discovery proportion


<div class="container">

<div class="col">

Let $M_0$ be the number of null hypotheses that are true.
$$M_1 = M - M_0$$

Define the <span class="highlight">false discovery proportion</span> (FDP)
$$
    \mathrm{FDP} =
    \begin{cases}
        V/R & \mathrm{if~} R>0\\
        0 & \mathrm{if~} R = 0.
    \end{cases}
$$


</div>

<div class="col">



|    | $\mathcal{H}_0$ accepted | $\mathcal{H}_0$ rejected | Total |
|:---|:------------------------:|:------------------------:|:-----:|
| $\mathcal{H}_0$ true | $U$ | <span class="highlight">$V$</span> | $M_0$ |
| $\mathcal{H}_0$ false | $T$ | $S$ | $M_1$ |
| Total | $M - R$ | <span class="highlight">$R$</span> | $M$ |


</div>
</div>

---

# False discovery rate
- **$M$ hypothesis tests**    We order the p-values in increasing order.
- **Benjamini-Hochberg Method**
    1. For a given $\alpha$, find the largest $k$ such that $p_k\leqslant k \frac{\alpha}{M}.$
    2. Then reject all $\mathcal{H}_{0m}$ for $m=1,\ldots,k$.
    3. **Theorem**
        $$
        \mathrm{FDR} = \mathbb{E}(\mathrm{FDP}) \leqslant \frac{M_0}{M}\alpha
        \leqslant \alpha.
        $$
    4. **Outcome** For a given significance level $\alpha$, the Benjamini Hochberg method bounds the false discovery rate.

---

# Multiple testing

Suppose 800 of 500,000 variants are significant at 0.05 level.

- **p-value < 0.05**
    Expect 0.05 * 500000 = 25000 false positives
- **false discovery rate < 0.05**
    Expect 0.05 * 800 = 40 false positives
- **family wise error rate < 0.05**
    The probability of at least 1 false positive < 0.05

---

### The basics of hypothesis testing applied to GWAS

- **Some Genomics Nomenclature**
    GWAS, SNPs, Allele, Diploid, Genotype, Phenotype
- **Hypothesis Testing**
    - $\mathcal{H}_0$ vs $\mathcal{H}_1$
    - Design test statistic and compute p-value
    - Reject $\mathcal{H}_0$ if p-value $<~\alpha$.
- **Multiple Testing Correction**

http://www.ong-home.my/download/notes-gwas-hypo-test.pdf

---

# Epistatic Interactions (I)

- **Genome Wide Interaction Search (GWIS)**
    Consider the association of all pairs of genotypes to phenotypes
- **Large search space**
    * 5000 individuals, 500,000 SNPs
    * Need to tabulate 125 billion contingency tables

![bg right:30% 100%](figs-hypotest/online-mendelian-inheritance-man.png)

---

# Epistatic Interactions (II)

- **Classification based analysis**
    * Focus on SNPs in case control studies
    * New statistical tests
    * Consider specificity and sensitivity
    * Gain over univariate ROC
    * CPU ($\approx$ days) and GPU ($\approx$ hours)

<span class="cite">Goudey et. al. BMC Genomics, 2013</span>
