# zkHackerHouse-binius

[binius](https://gitlab.com/UlvetannaOSS/binius) 是基于在binary field构造的*域扩张(towers of fields)*，构建实现了一个高效的 SNARK 证明系统。在 zkHackerHouse@苏州 期间，对 [binius](https://gitlab.com/UlvetannaOSS/binius) 的底层原理 towers of binary fields 进行了深入的研究，同时研究了 [Succinct Arguments over Towers of Binary Fields](https://eprint.iacr.org/2023/1784) 中 Chapter 3 中 PCS (Polynoimial Commitment Schemes) 的原理。

binius 中比较难理解的原理为域的扩张（见[论文](https://eprint.iacr.org/2023/1784)中2.3 Binary Towers），会涉及抽象代数中相关有限域的知识，但正是利用了域扩张的特定构造，带来了很多好处。域扩张可以写为下面这样的形式：

$$
\mathbb{F}_2 \subset \mathbb{F}_{2^2} \subset \cdots \subset \mathbb{F}_{2^{2^\iota}}.
$$

这样构造的好处有：

1. 在大域中的元素进行运算，可以转换成在小域中的计算，这个过程中利用了域扩张的结构，极大的减少了计算量。
2. 最小的那个域是可以灵活选择的，如这里的 $ \mathbb{F}_2 $ 可以换成从 $\mathbb{F}_{2^{2^4}}$ 开始，递归到最后一步的计算，可以用查表方式得到结果。
3. 由于是在 $\mathbb{F}_{2^k}$ 上进行的域扩张，在这些域上的加法就是因此支持一些原生的位操作，例如可以高效地计算一些哈希函数。

在 [Binius: a Hardware-Optimized SNARK](https://www.ulvetanna.io/news/binius-hardware-optimized-snark) 文章中，提到了这种 binary towers field SNARKs 的三个主要优势：
> First, this approach offers much lower memory usage and computational cost by maximizing the benefits of small fields.
>
> The second benefit is compatibility with standard hash functions.
>
> Finally, the third significant benefit is the very hardware-friendly implementation that binary fields promise.

## 笔记

- 📒 [binius 笔记](/notes/binius-note.pdf)

## 资料

- [binius官网](https://www.ulvetanna.io/news/binius-hardware-optimized-snark)
- Binius论文：[Succinct Arguments over Towers of Binary Fields](https://eprint.iacr.org/2023/1784)
- V神的 Binius 博客文章：[Binius: highly efficient proofs over binary fields](https://vitalik.eth.limo/general/2024/04/29/binius.html)
  - 📒 [笔记](/notes/%20notes%20of%20binius%20blog.pdf)
- Binius 播客访谈：[Episode 303: A Dive into Binius with Ulvetanna](https://zeroknowledge.fm/303-2/)

## 成员

- [Jade](https://github.com/wenjin1997)
- [0xhhh](https://github.com/cyl19970726)
- [啊咪咪小熊](https://github.com/amimibear)
- [Harold](https://github.com/HaroldGin931)
- [小雪](https://github.com/YangXiaoXue205)
