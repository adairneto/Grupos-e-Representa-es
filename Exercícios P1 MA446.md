---
title: MA446 Grupos e Representações - Exercícios
author: Adair Neto
date: \today
header-includes:
   - \usepackage[brazilian]{babel}
   - \usepackage[left=2cm,right=2cm,top=2cm,bottom=2cm]{geometry}
   - \setlength{\parindent}{1.5em}
   - \setlength{\parskip}{0.5em}
   - \usepackage{indentfirst}
   - \usepackage{helvet}
   - \usepackage[bitstream-charter]{mathdesign}
   - \usepackage[T1]{fontenc}
   - \usepackage{textcomp}
   - \usepackage[frenchmath]{mathastext}
---

## Lista 1

### Exercício 1

**Questão:** Seja $G$ um grupo e $a,b \in G$. Demonstre que 

1. Os elementos $b^{-1}ab$ e $a$ têm a mesma ordem.

2. Os elementos $ab$ e $ba$ têm a mesma ordem.

**Resolução:** 

1. 
    - Sabemos que 
    $$
    |a| = \min \{ z \in \mathbb{Z} : a^z = 1_G \}
    $$
    - Seja $m = |a|$ e $n = |b^{-1}ab|$.
    - Note que
    $$
    (b^{-1}ab)^m = b^{-1}a^m b = b^{-1}1_G b = b^{-1}b = 1_G
    $$
    - Ou seja, $m \geq n$. 
    - Por outro lado, 
    $$
    1_G = (b^{-1} a b)^n = b^{-1} a^n b \iff b^{-1} a^n = b^{-1} \iff a^n = b b^{-1} = 1_G
    $$
    - Assim, $n \geq m$ e, portanto, $n = m$.
2. Pelo item anterior, $ba$ e $b^{-1}(ba)b = (b^{-1}b)ab = ab$ têm a mesma ordem.

### Exercício 3

**Questão:** Seja $G$ um grupo.

1. Demonstre que se para todo $g \in G$ temos $g^{-1} = g$, então $G$ é abeliano.

2. Demonstre que se para todos $a,b \in G$ temos $(ab)^2 = a^2b^2$, então $G$ é abeliano.

**Resolução:** 

1. 
    - Lembre que
    $$
    (ab)^{-1} = b^{-1} a^{-1}
    $$
    - Como $g^{-1} = g$, para todo $g \in G$, segue que
    $$
    ab = (ab)^{-1} = b^{-1} a^{-1} = ba
    $$
2. Basta notar que
    $$
    abab = (ab)^2 = a^2 b^2 = a a b b \iff bab = abb \iff ba = ab
    $$

### Exercício 5

**Questão:** Sejam $p$ primo e 
$$
G = \left\{ \begin{pmatrix} a & b \\ c & d \end{pmatrix} : a,b,c,d \in \mathbb{Z}_p, ~ad-bc \neq 0 \text{ em } \mathbb{Z}_p \right\}
$$
Demonstre que $G$ é grupo com respeito à multiplicação de matrizes e calcule a ordem de $G$.

**Resolução:** 

1. Verificar que é grupo.
    - Elemento neutro: matriz identidade
    - Inversa: $$ \frac{1}{ad-bc} \begin{pmatrix} d & -b \\ -c & a \end{pmatrix} $$
    - Associatividade: segue da associatividade das matrizes e de $\mathbb{Z}_p$.
2. Ordem $|G|$.
    - Para montar uma base de $G$, temos $(p^2-1)$ opções para a primeira coluna e $(p^2 - p)$ para a segunda, pois queremos eliminar possíveis combinações lineares da primeira.
    - Logo, 
    $$
    |G| = (p^2 - 1)(p^2 - p) = (p^2-1)(p-1)p
    $$

### Exercício 6

**Questão:** Seja $G$ um grupo.

1. Sejam $H \leq G$ e $N \lhd G$. Mostre que $H \cap N \lhd H$.

2. Sejam $N, ~M$ ambos subgrupos normais de $G$ tais que $M \cap N = 1$. Mostre que, para $m \in M$ e $n \in N$, temos $mn = nm$.

**Resolução:** 

1. 
    - Queremos mostrar que, para todo $h \in H$ temos que
    $$
    h (H \cap N) h^{-1} \subseteq H \cap N
    $$
    - Por um lado, como $N \lhd G$ e $h \in G$, 
    $$
    h (H \cap N) h^{-1} \subseteq h N h^{-1} \subseteq N
    $$
    - Por outro,
    $$
    h (H \cap N) h^{-1} \subseteq h H h^{-1} = H
    $$
    - Logo, $h (H \cap N) h^{-1} \subseteq H \cap N$.
2. 
    - Pela normalidade de $N$ e $M$, temos
    $$
    N \lhd G \implies mN = Nm, \quad \forall ~m \in M \subseteq G
    $$
    e
    $$
    M \lhd G \implies nM = Mn, \quad \forall ~n \in N \subseteq G
    $$
    - Assim, temos que
    $$
    m^{-1}(nm)n^{-1} \in m^{-1} NmN = Nm^{-1}mN = N
    $$
    e
    $$
    m^{-1}(nm)n^{-1} \in MnMn^{-1} = Mnn^{-1}M = M
    $$
    - Isto é, $m^{-1}(nm)n^{-1} \in M \cap N = 1$. 
    - Logo,
    $$
    m^{-1}(nm)n^{-1} = 1 \iff m^{-1} n m = n \iff nm = mn
    $$

### Exercício 7

**Questão:** Seja $\mathbb{Z}$ o grupo cíclico infinito com operação $+$ e $G = \mathbb{Z}/n\mathbb{Z} = \mathbb{Z}_n$. 

1. Ache o número de geradores de $G$ como função de $n$.
2. Ache todos os elementos de ordem $36$ em $\mathbb{Z}_{36}$.
3. Ache a ordem do elemento $20+36\mathbb{Z}$ em $\mathbb{Z}_{36}$.
4. Ache todos os elementos em $\mathbb{Z}_{36}$ de ordem $9$.

**Resolução:** 

1. Geradores de $G$:
    - Seja $g \in G$. Sabemos que a ordem de $g^z$ é $n$ sse. $z$ e $n$ são coprimos, pois
    $$
    |g^z| = \frac{n}{\text{mdc}(n, z)}
    $$

    - Assim, temos $\varphi(n)$ geradores de $G$.
2. Elementos de ordem $36$ em $\mathbb{Z}_{36}$:
    - São todos os elementos coprimos com $36$, i.e., $$ 1, 5, 7, 11, 13, 17, 19, 23, 25, 29, 31, 35 $$
    - Note que são exatamente $\varphi(36)=12$ elementos.
3. Ordem do elemento $20+36\mathbb{Z}$:
    - Podemos calcular na mão, fazendo $20i$, $1 \leq i \leq 35$, e tirando os restos $\mod 36$ até encontrar o primeiro elemento congruente a zero.
    - Ou, simplesmente,
    $$
    \frac{36}{\text{mdc}(36,20)} = \frac{36}{4} = 9
    $$
    - Portanto, a ordem desejada é $9$.
4. Elementos de ordem $9$. 
    <!-- - Queremos encontrar todos os $x \in \mathbb{Z}_{36}$ tais que 
    $$ mx \equiv 0 \mod 36, \quad 1 \leq m \leq 9 $$
    - Ou seja, todos os múltiplos de 
    $$
    \frac{36}{\text{mdc}(36,9)} = \frac{36}{9} = 4
    $$
    - Portanto, os elementos de ordem $9$ são
    $$ 4, 8, 12, 16, 20, 24, 28, 32 $$ -->
    - Como queremos  
    $$
    9 = \frac{36}{\text{mdc}(36,k)} \implies \text{mdc}(36, k) = 4
    $$
    - Temos que os elementos de ordem $9$ são os números $k = 4t$ com $t$ e $9$ coprimos.


### Exercício 8

**Questão:** Seja 
$$
G = \left\{ \begin{pmatrix} a & 0 \\ b & d \end{pmatrix} : a,b,d \in \mathbb{C}, ~ad \neq 0 \right\}
$$
grupo com respeito à multiplicação de matriz e
$$
N = \left\{ \begin{pmatrix} 1 & 0 \\ b & 1 \end{pmatrix} : b \in \mathbb{C} \right\}
$$

Mostre que $N \lhd G$ e $G/N$ é abeliano.

**Resolução:** 

1. Para mostrar que $g N g^{-1} \subseteq N$, basta ver que
    $$
    \begin{pmatrix} a & 0 \\ b & d \end{pmatrix} \begin{pmatrix} 1 & 0 \\ b' & 1 \end{pmatrix} \begin{pmatrix} \frac{1}{a} & 0 \\ \frac{-b}{ad} & \frac{1}{d} \end{pmatrix} = \begin{pmatrix} 1 & 0 \\ \frac{b'd}{a} & 1 \end{pmatrix} \in N
    $$
2. Para mostrar que $G/N$ é abeliano, usaremos o teorema do isomorfismo.
    - Considere
    $$
    \begin{aligned}
    \begin{split}
    \varphi : G &\longrightarrow \mathbb{R}^\ast \times \mathbb{R}^\ast \\
    \begin{pmatrix} a & 0 \\ b & d \end{pmatrix} &\longmapsto (a, d)
    \end{split}
    \end{aligned}
    $$
    - Verifique que $\varphi$ é um homomorfismo.
    - Claramente $\varphi$ é epimorfismo. 
    - Calcule o núcleo:
    $$
    \ker(\varphi) = \{ g \in G : \varphi(g) = (1,1) \} = N
    $$
    pois
    $$
    \begin{pmatrix} a & 0 \\ b & d \end{pmatrix} \in \ker(\varphi) \iff a = 1 = d
    $$
    - Pelo teorema do isomorfismo, temos que
    $$
    G/N \simeq \mathbb{R}^\ast \times \mathbb{R}^\ast
    $$
    - Como $\mathbb{R}^\ast \times \mathbb{R}^\ast$ é abeliano, temos que $G/N$ é abeliano.

### Exercício 11a

**Questão:** Sejam $G$ um grupo e $H \le G$. Demonstre que $\bigcap_{g \in G} g H g^{-1}$ é um subgrupo normal de $G$.

**Resolução:** 

- Seja $t \in G$. Queremos verificar que $t M t^{-1} \subseteq M$, em que $M =  \bigcap_{g \in G} g H g^{-1}$. 
- Para isso, note que
    $$
    t M t^{-1} = t \left( \bigcap_{g \in G} g H g^{-1} \right) t^{-1} = \bigcap_{g \in G} tg H g^{-1}t^{-1}
    $$
- Chamando $s = tg$ temos que $s \in G$ e $g^{-1}t^{-1} = s^{-1} \in G$. 
- Portanto, 
    $$
    \bigcap_{g \in G} tg H g^{-1}t^{-1} = \bigcap_{s \in G} s H s^{-1} = M
    $$
- Logo, $M$ é subgrupo normal de $G$.

### Exercício 11b

**Questão:** Sejam $G$ o grupo $\mathbb{C}^\ast$ com operação multiplicação e $H$ o grupo
$$
H = \left\{ \begin{pmatrix} a & b \\ -b & a \end{pmatrix} : a,b \in \mathbb{R}, ~a^2+b^2 \neq 0 \right\}
$$
com a operação multiplicação de matrizes. Demonstre que existe isomorfismo de grupos $\varphi : G \longrightarrow H$.

**Resolução:** 

- Construa $\varphi$ da seguinte forma
$$
\begin{aligned}
\begin{split}
\varphi : \mathbb{C}^\ast &\longrightarrow H \\
z = a+ib &\longmapsto \begin{pmatrix} a & b \\ -b & a \end{pmatrix}
\end{split}
\end{aligned}
$$
- Verifique que $\varphi$ é homomorfismo.
- $\varphi$ é injetora, pois
$$
\ker(\varphi) = \left\{ z \in \mathbb{C}^\ast : \varphi(z) = \begin{pmatrix} 1 & 0 \\ 0 & 1 \end{pmatrix} \right\}
$$
e
$$
\varphi(z) = \begin{pmatrix} 1 & 0 \\ 0 & 1 \end{pmatrix}\iff z = 1 \implies \ker(\varphi) = 1
$$
- Por fim, $\varphi$ é claramente sobrejetora, pois toda matriz em $H$ com $a^2 + b^2 \neq 0$ é imagem de um elemento $z = a+ib \in \mathbb{C}^\ast$.

### Exercício 12

**Questão:** Seja $G$ um grupo. Mostre que

1. Cada subgrupo característico de $G$ é subgrupo normal de $G$.
2. Se $H$ é subgrupo normal de $G$ e $N$ é subgrupo característico de $H$, então $N$ é subgrupo normal de $G$.

**Resolução:** 

1. 
    - Seja $H$ um subgrupo característico de $G$.
    - Vimos que $\varphi_g : G \longrightarrow G$, dada por $\varphi_g(k) = g k g^{-1}$ é automorfismo.
    - Como $H \blacktriangleleft G$, 
    $$
    \varphi_g(H) = g H g^{-1} \subseteq H \implies H \lhd G
    $$
2. 
    - Como $H \lhd G$, 
    $$
    \varphi_g(H) = gHg^{-1} = H
    $$
    - Defina $\theta = \varphi_g|_H$, i.e., a restrição de $\varphi_g$ a $H$.
    - Note que $\theta$ é:
        - Homomorfismo, pois é restrição de homomorfismo a um subgrupo.
        - Sobrejetora por definição.
        - Injetora, pois $\varphi_g$ é injetora.
    - Assim, $\theta$ é um automorfismo.
    - Como $N \blacktriangleleft H$, 
    $$
    \theta(N) = gNg^{-1} \subseteq N \implies N \lhd G
    $$

### Exercício 13

**Questão:** Seja $p$ um número natural primo. 

1. Demonstre que $S_p$ tem exatamente $(p-1)!$ elementos de ordem $p$.
2. Quantos elementos $x$ tem em $S_{101}$ tais que $x^{101} = 1$?
3. Quantos elementos $x$ tem em $S_9$ tais que $x^9 = 1$?

**Resolução:** 

1. Elementos de ordem $p$:
    - Decomponha $g$, um elemento de ordem $p$, em produto de ciclos independentes:
    $$
    g = g_1 \cdots g_k
    $$
    - Como $p = |g| = \text{mmc}(|g_1|, \ldots, |g_k|)$, temos que $|g_1| = \cdots = |g_k| = p$.
    - Mas $| \text{sup}(g_1)| \ge p$ e $g_i \in S_p$, temos que $k = 1$.
    - Ou seja,
    $$
    g = g_1 = (i_1, i_2, \ldots, i_p) = (1, i_2, \ldots, i_p)
    $$
    - Como $i_2, \ldots, i_p$ é permutação arbitrária de $2, 3, \ldots, p$, temos $(p-1)!$ possibilidades.

2. Elementos em $S_{101}$ tais que $x^{101} = 1$:
    - Note que
        - $p = 101$ é primo
        - $x^{101} = 1 \iff |x| \mid 101$.
    - Assim, $|x| = 101$ ou $|x| = 1$.
    - Caso $|x| = 101$, temos, pelo item anterior, $(101-1)! = 100!$ possibilidades.
    - Caso $|x| = 1$, temos $x = 1_{S_{101}}$.
    - Portanto, temos $100! + 1$ possibilidades.

3. Elementos em $S_9$ tais que $x^9 = 1$:
    - Como $9$ não é primo, refazemos a decomposição em ciclos independentes:
    $$
    x = g_1 \cdots g_k
    $$
    - Temos que
    $$
    |x| = \text{mmc}(|g_1|, \ldots, |g_k|) \quad \text{ e } \quad |x| \mid 9
    $$
    - Assim, temos três possibilidades.
    1. Se $|x| = 1$, então $x = 1_{S_9}$.
    2. Se $|x| = 3$, como $3$ é primo, temos que $|g_1|, \ldots, |g_k| = 3$. 
        - Se $k = 1$, pelo primeiro item temos $(3-1)! = 2$ possibilidades. 
        - Se $k = 2$, i.e., $x = g_1 g_2 = g_2 g_1$, temos o seguinte número de possibilidades:
        $$
        \frac{2 \binom{9}{3} \binom{6}{3}2}{2} = {2 \binom{9}{3} \binom{6}{3}} = 3360
        $$
        - Se $k = 3$, temos o seguinte número de possibilidades:
        $$
        \frac{2 \binom{9}{3} 2 \binom{6}{3} 2 \binom{3}{3}}{3!} = \frac{2 \binom{9}{3} 2 \binom{6}{3}}{3} = 2240
        $$
    3. Se $|x| = 9$, temos $k = 1$ e $|g_1| = 9$. Assim, pelo primeiro item, temos $8!$ possibilidades.
    - Somando todas as possibilidades, temos o seguinte número de possibilidades:
    $$
        1 + 2 + 3360 + 2240 + 8! = 45923
    $$

- *Solução alternativa para elementos de ordem $p$*:
    - Note que os elementos de ordem $p$ são os $p$-ciclos.

    - Como cada $p$-ciclo é uma lista da forma $(a_1 ~ a_2 ~ \cdots ~ a_p)$, $1 \leq a_i \leq p$, temos exatamente $p!$ listas.

    - Porém, um mesmo ciclo pode ser representado em $p$ listas diferentes. 

    - Assim, temos exatamente $\frac{p!}{p} = (p-1)!$ elementos de ordem $p$.

### Exercício 15a

**Questão:** 
1. O ciclo $\begin{pmatrix} 1 & 3 & 2 & 6 \end{pmatrix} \begin{pmatrix} 1 & 4 & 2 \end{pmatrix}$ é elemento de $A_n$? 

2. Escreva os elementos em produto de ciclos independentes e encontre as ordens de todos os elementos.

**Resolução:** 

1. Decomponha $g = \begin{pmatrix} 1 & 3 & 2 & 6 \end{pmatrix} \begin{pmatrix} 1 & 4 & 2 \end{pmatrix}$ em um produto de transposições.
    $$
    \begin{aligned}
    \begin{split}
    \begin{pmatrix} 1 & 3 & 2 & 6 \end{pmatrix} &= \begin{pmatrix} 1 & 6 \end{pmatrix} \begin{pmatrix} 1 & 2 \end{pmatrix} \begin{pmatrix} 1 & 3 \end{pmatrix} \\
    \begin{pmatrix} 1 & 4 & 2 \end{pmatrix} &= \begin{pmatrix} 1 & 2 \end{pmatrix} \begin{pmatrix} 1 & 4 \end{pmatrix}
    \end{split}
    \end{aligned}
    $$
    - Assim, temos 
    $$
    g = \begin{pmatrix} 1 & 6 \end{pmatrix} \begin{pmatrix} 1 & 2 \end{pmatrix} \begin{pmatrix} 1 & 3 \end{pmatrix} \begin{pmatrix} 1 & 2 \end{pmatrix} \begin{pmatrix} 1 & 4 \end{pmatrix}
    $$
    - Como temos cinco transposições, segue que a permutação é ímpar, i.e., não está em $A_n$.
2. Escrever em ciclos independentes.
    $$
    g= \begin{pmatrix} 1 & 4 & 6 \end{pmatrix} \begin{pmatrix} 2 & 3 \end{pmatrix}
    $$
3. Ordem: 
    $$
    |g| = \text{mmc}\left(\left|\begin{pmatrix} 1 & 4 & 6 \end{pmatrix} \right|, ~\left|\begin{pmatrix} 2 & 3 \end{pmatrix}\right|\right) = \text{mmc}(3, 2) = 6
    $$

## Outros

### Pequeno teorema de Fermat

**Teorema.** Se $p$ é primo e $z \in \mathbb{Z}/p\mathbb{Z}$, então $z^{p-1} \equiv 1 \mod p$.

**Demonstração.**

- Aplique o teorema de Lagrange a $G = \mathbb{Z}_p^\times$:
    $$
        |z| \mid |G| = p-1
    $$
- Reescreva $p - 1 = |z|\cdot m$, para algum inteiro $m$.
- Use a definição de ordem:
$$
    z^{|z| m} = (z^{|z|})^m = 1_G^m = 1_G \quad \text{ e } \quad z^{|z| m} = z^{p-1}
$$
- Logo,
$$
    z^{p-1} \equiv 1 \mod p
$$

### Questão 1 (P1 2020)

**Enunciado.**

1. Dê definição de grupo e ordem de elemento de grupo.

2. Seja $\varphi : G \longrightarrow H$ um homomorfismo de grupos. Mostre que $| \varphi(g)| \mid |g|$. Se $|G| = 100$ e $|H| = 81$, mostre que $\text{Im}(\varphi) = 1_H$.

**Solução.**

1. 
    - Um grupo é um conjunto munido de uma operação satisfazendo associatividade, existência de elemento neutro e existência de inversa. 
    - A ordem de um elemento $g$ de grupo $G$ é a ordem do subgrupo gerado pelo elemento, em que esse subgrupo é o menor subgrupo de $G$ que contém o elemento $g$. A ordem de um grupo $G$ é a cardinalidade de $G$ enquanto conjunto.
2.
    1. Vamos mostrar que $| \varphi(g)| \mid |g|$.
        - Seja $|g| = n$ e $k = |\varphi(g)|$.
        - Então $g^n = 1 \implies\varphi(g^n) = 1 = \varphi(g)^n$. 
        - Pelo o algoritmo de Euclides, 
        $$
            n = kq + r, \quad 0 \leq r < k 
        $$
        - Denotando $\varphi(g) = x$,
        $$
        1 = x^n = x^{kq + r} = (x^k)^q x^r = 1^q x^r \implies x^r = 1
        $$
        - Como isso contradiz a minimalidade de $k$, temos que $r = 0$.
        - Logo, $n = kq$ e $k \mid n$.
    2. Mostrar que $\text{Im}(\varphi) = 1_H$.
        - Note que
        $$
        |g| \mid |G| = 100 \quad \text{ e } \quad |\varphi(g)| \mid |H| = 81
        $$
        - Como $|\varphi(g)| \mid |g|$, temos que
        $$|\varphi(g)| \mid 81 \quad \text{ e } \quad |\varphi(g)| \mid 100
        $$
        - Mas $\text{mdc}(100,81) = 1$.
        - Portanto, $|\varphi(g)| = 1 \implies \varphi(g) = 1_H$ para todo $g \in G$.
        - Logo, $\text{Im}(\varphi) = 1_H$.

### Questão 2 (P1 2020)

**Enunciado.** Seja $G$ um grupo com dois subgrupos normais $N$ e $M$ tais que $G = NM$ e $N \cap M = 1$.

1. Mostre que $nm = mn$ para todos $n \in N$ e $m \in M$.

2. Mostre que $\varphi : N \times M \longrightarrow G$ dado por $\varphi((n,m)) = nm$ é um isomorfismo de grupos.

**Solução.**

1. Ver exercício 6b.
2. 
    1. $\varphi$ é homomorfismo.
        - Por um lado,
        $$
        \varphi((n_1, m_1)(n_2, m_2)) = \varphi((n_1 n_2, m_1 m_2)) = n_1n_2 m_1 m_2
        $$
        - Por outro,
        $$
        \varphi((n_1, m_1)) \varphi((n_2, m_2)) = n_1 m_1 n_2 m_2 \overset{mn=nm}{=} n_1n_2 m_1m_2
        $$

    2. $\varphi$ é monomorfismo.
        - Note que
        $$
        (n,m) \in \ker(\varphi) \iff \varphi((n,m)) = nm = 1_G 
        $$
        - Como $N \cap M = 1$,
        $$
        nm = 1_g \iff n = 1 = m
        $$

    3. $\varphi$ é epimorfismo.
        - Seja $nm \in G = NM$. 
        - Tomando $(n, m) \in N \times M$, temos que $\varphi(n,m) = nm$. 
        - Logo, $\varphi$ é sobrejetora.

### Questão 3 (P1 2020)

**Enunciado.**

1. Dê as definições dos grupos $S_n$ e $A_n$. Calcule $|S_n|$ e $|A_n|$. Quais dos elementos $\begin{pmatrix} 1 & 2 & 3 \end{pmatrix} \begin{pmatrix} 4 & 5 & 6 \end{pmatrix}$ e $\begin{pmatrix} 1 & 2 \end{pmatrix} \begin{pmatrix} 3 & 4 \end{pmatrix} \begin{pmatrix} 1 & 2 & 3 \end{pmatrix}$ são elementos de $A_6$?

2. Demonstre que $\sigma \begin{pmatrix} i_1 & i_2 & \ldots & i_k \end{pmatrix} \sigma^{-1} = \begin{pmatrix} \sigma(i_1) & \sigma(i_2) & \ldots & \sigma(i_k) \end{pmatrix}$. Ache $\sigma \in S_{10}$ tal que $\sigma \rho \sigma^{-1} = \rho'$ para 
$$
\rho = \begin{pmatrix} 1 & 2 & 3 & 4 & 5 & 6 \\ 3 & 1 & 2 & 4 & 6 & 5 \end{pmatrix}, \quad \rho' = \begin{pmatrix} 1 & 2 & 3 & 4 & 5 & 6 \\ 2 & 1 & 3 & 5 & 6 & 4 \end{pmatrix}
$$

**Solução.**

1. 
    1. Definições de $S_n$ e $A_n$:
        - Seja $X = \{ 1, 2, \ldots, n \}$. Então $S_n = \{ f : X \longrightarrow X : f \text{ é bijetora} \}$ é chamado grupo simétrico, em que a operação é a composição de funções.
        - $A_n = \{ \sigma \in S_n : \sigma \text{ é par} \}$, i.e., $\sigma$ é produto de um número par de transposições.
    2. Ordens:
        - $|S_n| = n!$ pois existem $n!$ possibilidades de permutar os elementos $1, 2, \ldots, n$.
        - $|A_n| = \frac{n!}{2}$ pois $[S_n : A_n] = 2$.
            - De fato, supondo $n \geq 2$, tome $\tau \in S_n$ uma permutação ímpar.
            - Assim, $S_n = A_n \cup \tau A_n$. 
            - Vamos verificar que $\tau A_n$ é o conjunto de todas as permutações ímpares.
            - Por um lado, todos os elementos de $\tau A_n$ são ímpares, pois são o produto de uma permutação ímpar com uma permutação par em $A_n$.
            - Por outro, se $\sigma$ é permutação ímpar, $\tau^{-1} \sigma$ é par.
            - Ou seja, toda permutação ímpar está em $\tau A_n$:
            $$
            \tau^{-1} \sigma \in A_n \iff \sigma \in \tau A_n
            $$
    3. Elementos de $A_6$:
        - Como $\begin{pmatrix} 1 & 2 & 3 \end{pmatrix} \begin{pmatrix} 4 & 5 & 6 \end{pmatrix} = \begin{pmatrix} 1 & 3 \end{pmatrix} \begin{pmatrix} 1 & 2 \end{pmatrix} \begin{pmatrix} 4 & 6 \end{pmatrix} \begin{pmatrix} 4 & 5 \end{pmatrix}$ é produto de um número par de transposições, temos que esse elemento pertence a $A_6$.
        - Como $\begin{pmatrix} 1 & 2 \end{pmatrix} \begin{pmatrix} 3 & 4 \end{pmatrix} \begin{pmatrix} 1 & 2 & 3 \end{pmatrix} = \begin{pmatrix} 1 & 2 \end{pmatrix} \begin{pmatrix} 3 & 4 \end{pmatrix} \begin{pmatrix} 1 & 3 \end{pmatrix} \begin{pmatrix} 1 & 2 \end{pmatrix}$ é produto de um número par de transposições, esse elemento pertence a $A_6$.
2.
    1. Mostrar que $\sigma \begin{pmatrix} i_1 & i_2 & \ldots & i_k \end{pmatrix} \sigma^{-1} = \begin{pmatrix} \sigma(i_1) & \sigma(i_2) & \ldots & \sigma(i_k) \end{pmatrix}$.
        - Calculado em $\sigma(i_j)$,
        $$
        \sigma \begin{pmatrix} i_1 & i_2 & \ldots & i_k \end{pmatrix} \sigma^{-1} (\sigma(i_j)) = \sigma \begin{pmatrix} i_1 & i_2 & \ldots & i_k \end{pmatrix}(i_j) = \sigma(i_{j+1})
        $$
        - Ou seja, $\sigma(i_j) \longrightarrow \sigma(i_{j+1})$, o que mostra a igualdade desejada.
    2. Achar $\sigma \in S_{10}$ tal que $\sigma \rho \sigma^{-1} = \rho'$.
        - Note que $\sigma \begin{pmatrix} 1 & 3 & 2 \end{pmatrix} \begin{pmatrix} 5 & 6 \end{pmatrix} \sigma^{-1} = \begin{pmatrix} 1 & 2 \end{pmatrix} \begin{pmatrix}  4 & 5 & 6 \end{pmatrix}$.
        - Assim, pelo tipo de decomposição, temos que
        $$
            \sigma = \begin{pmatrix}
                1 & 2 & 3 & 4 & 5 & 6 \\
                4 & 6 & 5 & 3 & 1 & 2
            \end{pmatrix}
        $$

### Questão 4 (P1 2020)

**Enunciado.**

1. Enuncie a primeira parte do teorema de isomorfismos.

2. Seja $G = GL_5(\mathbb{R}) = \{ a \in M_5(\mathbb{R}) \mid \det(A) \neq 0 \}$ e $H = SL_5(\mathbb{R}) = \{ A \in GL_5(\mathbb{R}) \mid \det(A) = 1 \}$. Demonstre que $H$ é um subgrupo normal de $G$ e $G/H$ é um grupo abeliano.

**Solução.**

1. Seja $\varphi : G \longrightarrow H$ um homomorfismo de grupos. Então existe um único isomorfismo $$\psi : G / \ker(\varphi) \longrightarrow \text{Im}(\varphi)$$ tal que $\varphi = \psi \circ \pi$, em que $\pi : G \longrightarrow G/\ker(\varphi)$ é a projeção canônica. Isto é, $\psi(\ker(\varphi)g) = \varphi(g)$.

2. 
    1. Mostrar que $H \lhd G$, i.e., $g H g^{-1} \subseteq H$, para todo $g \in G$.
        - Seja $g \in G$ e $h \in H$. Então 
        $$
            \det(ghg^{-1}) = \det(g) \det(h) \det(g^{-1}) = \det(h) = 1
        $$
        - Isto é, $g h g^{-1} \in H$ e, portanto, $H \lhd G$.

    2. Mostrar que $G/H$ é abeliano, i.e., $g_1g_2 H = g_1 H g_2 H = g_2 H g_1 H = g_2 g_1 H$.
        - Note que
        $$
        g_1 g_2 (g_2 g_1)^{-1} = g_1 g_2 g_1^{-1} g_2^{-1}
        $$
        - E
        $$
        \det(g_1 g_2 (g_2 g_1)^{-1}) = \det(g_1) \det(g_2) \frac{1}{\det(g_1)} \frac{1}{\det(g_2)} = 1
        $$
        - Assim, temos que $g_1 g_2 (g_2 g_1)^{-1} \in H$.
        - Ou seja,
        $$
        g_2 g_2 H = g_2 g_1 H
        $$
        - Logo, $G/H$ é abeliano.

### Questão 5 (P1 2020)

**Enunciado.** Seja $G = \{ g \in \mathbb{C} \mid g^{36} = 1 \}$ um grupo com respeito à operação produto de números complexos. Mostre que $G$ é um grupo cíclico de ordem $36$. Escreva todos os geradores de $G$. Escreva um elemento de $G$ de ordem $9$.

**Solução.**

1. Mostre que $G$ é um grupo cíclico de ordem $36$.
    - Reescreva
    $$
    G = \{ g \in \mathbb{C} : g^{1/36} \} = \{ g_k = e^{i(2 \pi k/36)} : k \in \mathbb{Z} \}
    $$
    - Note que para $k \geq 36$ temos que os elementos começam a se repetir. Portanto, $|G| = 36$. 
    - Como $<g_1> \subseteq G$, basta verificar que $G \subseteq <g_1>$.
    - De fato, cada $g_k$ pode ser escrito como
    $$
    e^{i(2 \pi k/36)} = \underbrace{e^{i(2 \pi /36)} e^{i(2 \pi /36)} \cdots e^{i(2 \pi /36)}}_{k \text{ vezes}} = (e^{i(2 \pi /36)})^k
    $$
    - Ou seja, todo elemento $g_k \in G$ pode ser escrito como potência de $g_1$, i.e., $G \subseteq <g_1>$.
    - Logo, $G = <g_1>$, de onde segue que $G$ é grupo cíclico de ordem $36$.

2. Escreva todos os geradores de $G$.
    - Note que $g_1^{36} = e^{i 2 \pi} = 1$. 
    - Como $k < 36$ implica que $k/36 < 1$, segue que $2 \pi k/36$ não é múltiplo de $2 \pi$. Assim, $e^{i 2 \pi k/36} \neq 1$ e, portanto, $k = 1$ é o menor inteiro positivo tal que $g_1^{36} = 1$. Ou seja, $|g_1| = 36 = |G|$.
    - Como $G = <g_1>$, todo $a \in G$ pode ser escrito como $g_1^k$.
    - E como
    $$
    |g_1^k| = \frac{|g_1|}{\text{mdc}(k, |g_1|)} = \frac{36}{\text{mdc}(k, 36)}
    $$
    - Temos que $g_1^k$ gera $G$ sse. $|g_1^k| = 36$, i.e., $\text{mdc}(k, 36) =1$. 
    - Assim, queremos os inteiros positivos $k$ coprimos com $36$, que são
    $$
    k \in \{ 1, 5, 7, 11, 13, 17, 19, 23, 25, 29, 31, 35 \}
    $$
    - Ou seja, os geradores de $G$ são os elementos $g_k$ com $k$ descrito acima.

3. Escreva um elemento de $G$ de ordem $9$.
    - Queremos $b = g_1^k$ tal que $|b| = 9$. 
    - Ou seja
    $$
    9 = \frac{36}{\text{mdc}(k, 36)} \implies \text{mdc}(k, 36) = 4
    $$
    - Tomando $k = 4$, temos que $b = e^{i 2 \pi 4/36}$ é elemento de ordem $9$ em $G$.

### Questão 1b (P1 2021)

**Enunciado.** Seja $G = S_3$.

1. Mostre que o subgrupo $N$ gerado por $a = \begin{pmatrix} 1 & 2 & 3 \end{pmatrix}$ é um subgrupo normal de $G$.

2. Seja $B$ o subgrupo de $G = S_3$ gerado por $\begin{pmatrix} 1 & 2 \end{pmatrix}$. Mostre que $B$ não é um subgrupo normal em $G$.

**Solução.**

1. Aplique o Teorema de Lagrange,
$$
[G : N] = \frac{|G|}{|N|} = \frac{6}{3} = 2 \implies N \lhd G
$$

2. Basta considerar
$$
    \begin{pmatrix} 1 & 3 \end{pmatrix} \begin{pmatrix} 1 & 2 \end{pmatrix} \begin{pmatrix} 1 & 3 \end{pmatrix} = \begin{pmatrix} 2 & 3 \end{pmatrix} \notin B \implies B \not\lhd G
$$

### Questão 3b (P1 2021)

**Enunciado.** Seja $G = \mathbb{Z}_{12} \times \mathbb{Z}_{36}$ o produto direto (externo).

1. Existe elemento de $G$ de ordem $432$?

2. É verdade que $\mathbb{Z}_{12} \times \mathbb{Z}_{36} \simeq \mathbb{Z}_{432}$?

**Solução.**

1. Considere $(a,b) \in \mathbb{Z}_{12} \times \mathbb{Z}_{36}$. 
    - Em notação aditiva,
    $$
    36(a,b) = (0_{\mathbb{Z}_{12}}, 0_{\mathbb{Z}_{36}}) \implies |(a,b)| \mid 36
    $$
    - Assim, não existe $(a,b) \in G$ de ordem $432$.
2. Note que $1 + 432\mathbb{Z}$ tem ordem $432$. Logo, $\mathbb{Z}_{432}$ e $\mathbb{Z}_{12} \times \mathbb{Z}_{36}$ não são isomorfos.

### Questão 4 (P1 2021)

**Enunciado.**

1. Defina o subgrupo comutador $G'$ e mostre que $G'$ é normal em $G$ e $G/G'$ é um grupo abeliano.

2. Ache a ordem de $G'$ para $G = S_3$.

**Solução.**

1.
    1. O subgrupo comutador $G'$ é o subgrupo de $G$ gerado por todos os comutadores, i.e.,
    $$
    G' = \{ [a,b] = a^{-1}b^{-1}ab \mid a, b \in G \}
    $$
    2. Vamos mostrar que $G'$ é normal.
        - Tome $g \in G$ e $[a,b] \in G'$. 
        - Então
        $$
        g^{-1}[a,b]g = g^{-1}a^{-1}b^{-1}abg = g^{-1}a^{-1}gg^{-1}b^{-1}gg^{-1}agg^{-1}bg = [g^{-1}ag, g^{-1}bg]
        $$
        - Logo, $G' \lhd G$.
    3. Mostremos que $G/G'$ é abeliano.
        - Considere as classes laterais $g_1G'$ e $g_2 G'$ em $G/G'$.
        - Sabemos que
        $$
            g_1G' g_2G' = g_1g_2 G' \quad \text{ e } \quad g_2G' g_1G' = g_2g_1G'
        $$
        - Observe que
        $$
            g_1g_2(g_2g_1)^{-1} = g_1g_2 g_1^{-1} g_2^{-1} = [g_1^{-1}, g_2^{-1}]
        $$
        - Ou seja, $g_1g_2(g_2g_1)^{-1} \in G'$. 
        - Logo, 
        $$
            g_1g_2G' = g_2g_1G'
        $$
2.
    - Lembre que $|S_n/A_n| = 2$ implica que $S_n/A_n$ é cíclico, ou seja, é abeliano.
    - Assim, $S_3/A_3$ é abeliano e temos que $G' \subseteq A_3$. 
    - Como $|A_3| = 3$ é primo, temos, pelo teorema de Lagrange, que os únicos subgrupos de $A_3$ são $1$ e $A_3$.
    - Mas como $S_3$ não é abeliano, temos que $G' \neq 1$. 
    - Logo, $G' = A_3$ e, portanto, $|G'| = 3$.