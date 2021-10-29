---
marp: true
title: Representing biological sequences
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


# test slide

- <span class="highlight">highlight</span>
- <span class="cite">cite</span>
- <span class="dna">dna</span>
- <span class="footnote">footnote</span>




---
<!-- _class: lead -->

# Opportunities and challenges in the sequencing revolution

<span class="highlight">Cheng Soon</span> Ong

---

The bottleneck in genome sequencing is no longer data generation 
-- the computational challenges around data analysis, display and integration are now rate limiting.

<div class="highlight">
    New approaches and methods are required to meet these challenges.
</div>

![bg right:20% 80%](figs-bio/genomics-computation-challenge.jpg)

<div class="cite">
    Green, Guyer and National Human Genome Research Institute
    Charting a course for genomic medicine from base pairs to bedside, Nature 2011.
</div>


---

<!-- _class: lead -->

# A glimpse of molecular biology

---
# Central dogma


- **DNA** written 5' to 3'.
  e.g. <span class="dna">AATCGAAGTTA</span>
- **RNA** T $\Rightarrow$ U
    e.g. <span class="dna">AAUCGAAGUUA</span>
- **Amino acid** 
  - 3 letters of RNA (codon) $\Rightarrow$ amino acid,
  - 20 letter alphabet.

<span class="cite">Lewin, Genes</span>


![bg right:50% 100%](figs-bio/central-dogma.png)

---
<!-- _class: lead -->

# Gene finding

---

# Genes are pure information objects

- no physical structure

---

# Gene finding

---

# Transcription start

---

# Transcription termination

---

# Splice sites

---

# Splice forms

---

# Alternative splicing

---

# Regulation and control

---

# Chromatin structure

---

# Methylation

---

# Glimpse of molecular biology

- **DNA** Positive strand, written 5' to 3'.
      e.g. AATCGAAGTTA
- **RNA** T $\Rightarrow$ U
      e.g. AAUCGAAGUUA
- **Amino acid** 3 letters of RNA (codon) $\Rightarrow$ amino acid
- **Splicing** pre-mRNA to mature mRNA
- **Transcription factor** Regulate expression of gene, 
    through promoters and repressors
- **Epigenetics** Methylation, Chromatin marks


---
<!-- _class: lead -->

# The sequencing revolution

---

# History of sequencing

---

# $1000 human genome

---

<!-- _class: lead -->
DNA sequences: 6 billion reads, each 150 bases, ~$\frac{1}{2}$TB

# So what?

---

# We have a new cheap sensor

---

# DNA sequencing

---

# Cohort

---

# Replication

---

# RNA-seq

---

<div class="container">

<div class="colsmall">

# *-seq

- RNA-seq
- Hi-C-seq
- Sort-seq
- ChIP-seq
$$\vdots$$
- hundreds more

</div>

<div class="colbig">

![](figs-bio/seqcartoon.jpg)
https://liorpachter.wordpress.com/seq/

</div>
</div>

