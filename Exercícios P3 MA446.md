---
title: MA446 Grupos e Representações - Exercícios P3
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

## Lista 3

### Exercício 1

**Questão:** Seja $Q_8$ o grupo $\langle a, b \mid a^4 = 1, b^2 = a^2, bab^{-1} = a^{-1} \rangle$.

1. Mostre que $|Q_8| = 8$.
2. Escreva os caracteres irredutíveis de $Q_8$.

**Resolução:**

1. $|Q_8| = 8$.
   <!-- - Seja $c = ab$. Assim, $$c^2 = (ab)^2 = abab \iff c^2 b^{-1} = abab = aa^{-1}b = b \iff c^2 = b^2$$ -->
   - Note que podemos escrever
   $$
      Q_8 = \langle a^i b^j \mid 0 \le i \le 3, ~0 \le j \le 1 \rangle 
   $$
   - Temos os elementos
   $$
   Q_8 = \{ 1, a, a^2, a^3, b, ab, a^2b, a^3b \}
   $$
   - Assim, $|Q_8| = 8$. Observe que $Q_8 = \{ 1, -1, i, -i, j, -j, k, -k \}$ é o grupo dos quatérnios.

2. Caracteres irredutíveis de $Q_8$.
   - Classes de conjugação de $Q_8$:
      - Como $bab^{-1} = a^3$, temos que $a$ e $a^3$ são conjugados. 
      - Note que $a^2$ é o único elemento de ordem $2$, formando uma classe de conjugação.
      - Como $a^3ba = a^2b$ e $b(ab)b^{-1} = a^3b$ (pois $ba = a^{-1}b$), temos as seguintes classes de conjugação:
      $$
      \{ 1 \}, \{ a^2 \}, \{ a, a^3 \}, \{ ab, a^3b \}, \{ b, a^2 b \}
      $$
      - Como o número de classes de conjugação é o número de representações irredutíveis, temos cinco representações irredutíveis.
   - Representações de grau um:
      - Seja $\rho : Q_8 \longrightarrow \mathbb{C}^\ast$ representação linear.
      - Vejamos que $\rho(1) = \rho(-1) = 1$. Sabemos que $(\rho(-1))^2 = \rho(1) = 1$, ou seja, $\rho(-1) = \pm 1$. Suponha que $\rho(-1) = -1$. Assim, como $ab = -ba$, teríamos $$\rho(ab) = \rho(a)\rho(b) = -\rho(a)\rho(b)$$ o que é absurdo.
      - Como $(\rho(a))^2 = (\rho(b))^2 = 1$, temos as seguintes possibilidades: $\rho(1) = \rho(-1) = 1$, $\rho(a) = \pm 1$, $\rho(b) = \pm 1$.   
      - Assim, temos quatro representações de grau um.
   - Representação de grau dois:
      - Denote por $n_1, \ldots, n_r$ as dimensões das representações irredutíveis não isomorfas entre si de $G$.
      - Como $|G| = n_1^2 + \cdots + n_r^2$ e já sabemos que temos quatro representações de grau um, segue que $r = 5$ e $n_r = 2$. Ou seja, temos uma representação de grau dois.
      - Sejam
      $$
      A = \begin{pmatrix}
      i & 0 \\
      0 & -i
      \end{pmatrix}, \quad
      B = \begin{pmatrix}
      0  & 1 \\
      -1 & 0
      \end{pmatrix}
      $$
      - Observe que $A^4 = I$, $A^2 = B^2$ e $BAB^{-1} = A^{-1}$.
      - Assim, podemos definir o homomorfismo de grupos $\rho_5 : Q_8 \longrightarrow GL_2(\mathbb{C})$ como $\rho_5(a)v = Av$ e $\rho_5(b)v = Bv$ para todo $v \in GL_2(\mathbb{C})$.
      - Como $(\chi_5, \chi_5) = \frac{1}{|G|} \sum_{g \in G} \chi_5(g) \overline{\chi_5(g)} = 1$, segue que $\rho_5$ é irredutível.
   - Tabela de caracteres:

|          | $1$ |  $a$ |  $b$ | $ab$ | $a^2$ |
|:--------:|:---:|:----:|:----:|:----:|:-----:|
| $\chi_1$ | $1$ |  $1$ |  $1$ |  $1$ |  $1$  |
| $\chi_2$ | $1$ |  $1$ | $-1$ | $-1$ |  $1$  |
| $\chi_3$ | $1$ | $-1$ |  $1$ | $-1$ |  $1$  |
| $\chi_4$ | $1$ | $-1$ | $-1$ |  $1$ |  $1$  |
| $\chi_5$ | $2$ |  $0$ |  $0$ |  $0$ | $-2$  |

<!-- **Referências:**

- James & Liebeck.
- [Representations of finite groups; basic examples (2)](https://ysharifi.wordpress.com/2011/02/08/finite-group-representations-basic-examples-3/)
- [Complete set of irreducible representations of small groups (2)](https://ysharifi.wordpress.com/tag/representations-of-quaternion-group-q_8/) -->

### Exercício 2

**Questão:** Sejam $A$ um grupo abeliano finito, $B$ um subgrupo de $A$ e $\varphi$ um caracter irredutível de $B$. Mostre que

1. Existe um caracter irredutível $\psi$ de $A$ tal que $\psi|_B = \varphi$.

2. O número de extensões $\psi$ é $[A: B]$.

**Resolução:**

1. Existência de caracter irredutível.
   - Primeiro mostramos que $\varphi$ pode ser estendido a um subgrupo de $A$ que é maior do que $B$.
   - Tome $x \in A \setminus B$ e $d$ o menor inteiro tal $x^d \in B$. Note que $x^n \in B$ sse. $n$ é múltiplo de $d$.
   - Seja $a \in \mathbb{C}$ tal que $a^d = \varphi(x^d)$ e defina $C = \langle B, x \rangle$. Observe que os elementos de $C$ são da forma $x^n b$, para algum $b \in B$.
   - Podemos definir um caracter $\tilde{\varphi}$ de $C$ como $\tilde{\varphi}(x^n b) = a^n \varphi(b)$. 
      - Se $x^n b = x^m b'$, então $b'b^{-1} = x^{n-m}$. Assim, $n-m = dk$, para algum $k$. Então,
      $$
      \varphi(b')\varphi(b)^{-1} = \varphi(x^{n-m}) = \varphi(x^d)^k = a^dk = a^{n-m}
      $$
      - Isso implica que $a^n \varphi(b) = a^m \varphi(b')$. Portanto, $\tilde{\varphi}$ está bem definido.
      - Claramente, $\tilde{\varphi}$ é homomorfismo de grupos. Portanto, é um caracter.
   - Seja $S$ o conjunto de subgrupos $C \le A$ tais que $B \subseteq C$ e $\varphi$ pode ser estendido a $C$.
   - Como $B \in S$, temos que $S$ é não vazio. Portanto, podemos tomar $K$ como sendo o elemento maximal.
   - Caso $K$ seja um subgrupo próprio de $A$, então a extensão de $\varphi$ a $K$ existe, mas não pode ser estendida a um subgrupo maior, o que contradiz a afirmação acima. Logo, $K = A$ e $\psi$ é a extensão de $\varphi$ a $K$.

2. Número de extensões.
   <!-- - Reciprocidade de Frobenius? Ver notas Dessislava. -->
   - Pela parte 1, sabemos que se $B_0 \le A$, então podemos estender $\varphi$ para um subgrupo $B_1$ de $A$ que é maior do que $B_0$. Isso nos dá uma cadeia $$B_0 \subsetneq B_1 \subsetneq B_2 \subsetneq \cdots \subsetneq B_m = A $$
   - Logo, o número total de extensões é 
   $$
   \prod [B_{i+1} : B_i] = [A : B]
   $$

<!-- **Referências:**

- [Prove that irreducible character of subgroup extends to $[G:H]$
irreducible characters of abelian group](https://math.stackexchange.com/questions/4184936/prove-that-irreducible-character-of-subgroup-extends-to-gh-irreducible-char)
- [Number of extensions of a character in an abelian group](https://math.stackexchange.com/questions/4186652/number-of-extensions-of-a-character-in-an-abelian-group)
- [Characters of Abelian Groups](http://sporadic.stanford.edu/bump/group/gr2_2.html) -->

### Exercício 3

**Questão:** Existe um grupo $G$ finito e um caracer $\chi$ de $G$ tal que $\sum_{g \in G} \chi(g) = 1/2$? 

**Resolução:**

Não, pois $\chi(g)$ é integral sobre $\mathbb{Z}$.

<!-- https://math.stackexchange.com/questions/3762788/is-it-possible-to-have-sum-g-in-g-chig-frac12

https://math.stackexchange.com/questions/243221/proofs-that-the-degree-of-an-irrep-divides-the-order-of-a-group

https://groupprops.subwiki.org/wiki/Degree_of_irreducible_representation_divides_order_of_group -->

### Exercício 4

**Questão:** Sejam $\rho : G \longrightarrow GL(V)$ uma representação linear, $H$ um subgrupo de $G$ e $U$ um subespaço $\rho(H)$-invariante de $V$. Mostre que:

1. A dimensão de menor subespaço linear $\rho(G)$-invariante de $V$ que contém $U$ é menor ou igual a $\dim(U)[G:H]$.

2. Se $\rho$ é irredutível, então $\dim(V) \le m[G:H]$, onde $m$ é a maximal dimensão de representação irredutível de $H$.

**Resolução:**

1. Dimensão de menor subespaço linear.
   - Escreva $G$ como união disjunta de classes laterais:
   $$
   G = \dot{\bigcup_{1 \le i \le k}} g_i H
   $$
   - Como $\rho(H)(U) = U$, definindo $W$ como o subespaço de $V$ gerado por $\rho(G)(U)$, temos que
   $$
   \rho(G)(U) = \bigcup_{1 \le i \le k} \rho(g_i) \underbrace{\rho(H)(U)}_{\subseteq U} \subseteq W
   $$
   - E como $\rho(g)$ é linear, temos que $\rho(g)(\lambda u) = \lambda \rho(g)(u)$, $\lambda \in \mathbb{C}$. E como $\rho(g)(U)$ é subespaço de $V$, temos também
   $$
   \rho(g)(u_1) + \rho(g)(u_2) = \rho(g)(u_1 + u_2)
   $$
   - Note que $\rho(g_1)(u_1) + \rho(g_2)(u_2) \neq \rho(g)(u)$.
   - Com isso, podemos escrever
   $$
   W = \rho(g_1)(U) + \rho(g_2)(U) + \cdots + \rho(g_k)(U)
   $$
   - Observe que $U \subseteq W$ (basta tomar $g_1 = 1_G$). Assim, $W$ é o menor subespaço linear $\rho(G)$-invariante de $V$ que contém $U$.
   - Portanto, como $k = [G:H]$,
   $$
   \dim W \le \sum_{1 \le i \le k} \dim \rho(g_i)(U) = \dim(U) k = \dim(U) [G:H]
   $$

2. $\dim(V) \le m[G:H]$.
   - Considere a restrição $\rho|_H : H \longrightarrow GL(V)$ e escolha $U \neq 0$ um subespaço de $V$ que é $\rho(H)$-invariante. 
   - Como $\rho$ é irredutível, segue que $\rho|_H$ é irredutível e $\dim U \le m$. Portanto,
   $$
   \dim V = \dim W \le \dim U [G:H] \le m [G:H]
   $$

   <!-- - Seja $\chi$ o caracter de $\rho$. Como $\rho$ é irredutível, $(\chi, \chi) = 1$. Por outro lado,
   $$
   \sum_{i=1}^r m_i^2 = (\chi, \chi) = \frac{1}{|G|} \sum_{g \in G} \chi(g) \overline{\chi(g)}
   $$
   - Cuidado: esses $m_i^2$ são as multiplicidades das partes irredutíveis, mas $\chi$ já é irredutível.
   - Ver Prop. 20.5 (p. 214). -->

### Exercício 5

**Questão:** Seja $G$ um $p$-grupo não abeliano de ordem $p^3$. Ache o número de caracteres irredutíveis de $G$ e as dimensões desses caracteres. Dica: $Z(G) = G'$ e $|Z(G)| = p$.

**Resolução:**

- Seja $\rho : G \longrightarrow GL(V)$ representação irredutível. 
- Da lista 2 (exercício 10), sabemos que $G' = Z(G)$. Assim, $|G'| = |Z(G)| = p$ e $[G:G'] = p^2$. I.e., temos $|G/G'| = p^2$ representações de grau um. 
- Como o grau de uma representação divide a ordem do grupo, temos que os possíveis graus para uma representação de $G$ são $\{ 1, p, p^2, p^3 \}$.
- Escreva $Z(G) = \{g_1 = 1_G, g_2, \ldots, g_p \}$. Assim, ${}^G g_i = \{ g_i \}$ para $1 \le i \le p$.
- Sejam $h_1, \ldots, h_{p^2-1} \in G \setminus G'$. Então $h_i G' \neq h_j G'$ se $i \neq j$. 
   - De fato, se $g h_i g^{-1} = h_j$, então $$h_j = h_i h_i^{-1} g h_i g^{-1} \in h_i G'$$ porque $h_i^{-1} g h_i g^{-1} = [h_i, g^{-1}] \in G'$.
   - Isso implica que $h_j G' = h_i G'$, o que é absurdo. Portanto, $h_i G' \neq h_j G'$ para $i \neq j$. 
- Com isso, temos que ${}^G h_i \neq {}^G h_j$ para $1 \le i,j \le p^2 - 1$.
- Ou seja, temos as classes de conjugação $${}^G g_1, {}^G g_2, \ldots, {}^Gg_p, {}^G h_1, \ldots, {}^G h_{p^2-1}$$ todas distintas entre si. Observe que essa lista contém $p^2 + p - 1$ classes de conjugação. Verifiquemos que essas são todas as classes de conjugação:
   $$
   p^3 = |G| = \sum n_i^2 \ge \underbrace{1 + \cdots + 1}_{p^2 \text{ vezes}} + \underbrace{p^2 + \cdots + p^2}_{p-1 \text{ vezes}} = p^2 + (p-1)p^2 = p^3
   $$
- Logo, temos $p^2$ representações de grau um e $(p-1)$ representações de grau $p$.

<!-- **Referências:**

Ver notas do atendimento.

https://math.stackexchange.com/questions/72036/conjugacy-classes-of-non-abelian-group-of-order-p3 -->

### Exercício 6

**Questão:** Existe grupo finito $G$ com oito elementos e caracter $\chi$ com valores $1, -1, 2, 0, 0, -2, 0, 0$?

**Resolução:**

Não, pois
$$
(\chi, \chi) = \frac{1}{8}(1 + 1 + 4 + 4) = \frac{10}{8} \notin \mathbb{Z}
$$

### Exercício 7

**Questão:** Existe um grupo finito $G$ tal que $G$ tem 7 representações irredutíveis, 3 de dimensão 1 e 4 de dimensão 2?

**Resolução:**

- Sabemos que se $n_1, \ldots, n_\alpha$ são as dimensões das representações irredutíveis de $G$, então $|G| = n_1^2 + \cdots + n_\alpha^2$.

- Assim, temos $$|G| = 1^2 + 1^2 + 1^2 + 2^2 + 2^2 + 2^2 + 2^2 = 19$$

- Como $19$ é primo, $G$ é cíclico e, portanto, abeliano.

- Ou seja, $G' = 1_G$. Mas isso implica que todas as representações irredutíveis têm grau um (e teríamos $|G/G'| = |G| = 19$ representações de grau um), o que é absurdo.

### Exercício 8

**Questão:** Seja $\rho : G \longrightarrow GL(V)$ uma representação irredutível onde $|G| = p^3$ e $\dim(V) \neq 1$. Mostre que $\rho$ é injetivo.

**Resolução:**

- Seja $N = \ker \rho = \{ g \in G \mid \rho(g) = \text{id}_V \}$ e suponha $N \neq 1$.
- Como $N \neq 1$ implica que $\dim V = p$, segue que $N \lneqq G$.
- Defina
$$
\begin{aligned}
   \tilde{\rho} : G/N &\longrightarrow GL(V) \\
   gN &\longmapsto \rho(g)
\end{aligned}
$$
- Como $|G/N| < p^3$, temos que $|G/N| \in \{ p, p^2 \}$. Portanto, $G/N$ é abeliano. 
- Sabemos que representação irredutível de grupo abeliano tem grau um, o que implica que $\dim V = 1$, o que contradiz nosso enunciado. 
- Logo, $\ker \rho = 1$ e $\rho$ é injetivo.

### Exercício 9

**Questão:** Seja $\rho$ uma representação irredutível de grau $n$ de um grupo $G$. Seja $\chi$ o caracter de $\rho$. Mostre que 

1. Se $g \in Z(G)$, então o operador linear $\rho(g)$ é múltiplo escalar de $\text{id}_V$, assim, $|\chi(g)| = n$. Dica: Use o Lema de Schur.

2. $n^2 \le |G| / |Z(G)|$.

3. Se $\rho$ é injetivo, então o grupo $Z(G)$ é cíclico.

**Resolução:**

1. Seja $g \in Z(G)$ e mostremos que $\rho(g) = \lambda ~\text{id}_V$ e $|\chi(g)| = n$.
   - Então $\rho(g) \rho(h) = \rho(h) \rho(g)$ e, assim, $\rho(g h) = \rho(h g)$, para todo $h \in G$.
   - Portanto, pelo Lema de Schur, $\rho(g)$ é uma homotetia, i.e.,
   $$
   \rho(g) = \lambda ~\text{id}_V =
   \begin{pmatrix}
   \lambda & & &  \\
   & \lambda & & \\
   & & \ddots & \\
   & & & \lambda
   \end{pmatrix}
   $$
   - $\lambda$ é raiz da unidade.
      - Se $|Z(G)| = k$, então $g^k = 1$. Assim,
      $$
      \text{id}_V = \rho(1) = \rho(g^k) = \rho(g)^k = \begin{pmatrix}
      \lambda^k & &  \\
      & \ddots & \\
      & & \lambda^k
      \end{pmatrix}
      $$
      - Portanto, $\lambda^k = 1$ e, assim, $\lambda$ é raiz da unidade.
   - Portanto, $|\chi(g)| = |n\lambda| = n |\lambda| = n$, como queríamos.

2. $n^2 \le |G| / |Z(G)|$.
   - Como $\rho$ é irredutível, 
   $$
   1 = (\chi, \chi) = \frac{1}{|G|} \sum_{h \in G} \chi(h) \overline{\chi(h)} = \frac{1}{|G|} \sum_{h \in G} |\chi(h)|^2 
   $$
   - Com isso,
   $$
   |G| = \sum_{h \in G} |\chi(h)|^2  \ge \sum_{g \in Z(G)} |\chi(g)|^2 = n^2 |Z(G)| 
   $$
   - Logo, $n^2 \le |G| / |Z(G)|$.

3. Se $\rho$ é injetivo, então o grupo $Z(G)$ é cíclico.
   - Considere a restrição $\rho|_{Z(G)} : Z(G) \longrightarrow GL(V)$ que mapeia $g \longmapsto \rho(g) = \lambda ~\text{id}_V$ e defina 
   $$
   \begin{aligned}
   \theta : Z(G) &\longrightarrow \mathbb{C}^\ast \\
   g &\longmapsto \lambda
   \end{aligned}
   $$
   - Note que como $\rho$ é homomorfismo de grupos, então $\theta$ é homomorfismo de grupos. E como $\rho$ é injetivo, $\theta$ é injetivo. 
   - Assim, temos que $Z(G) \cong \text{Im}(\theta) \le \mathbb{C}^\ast$. Como subgrupo finito de $K^\ast$ é cíclico, temos que $Z(G)$ é cíclico.

   <!-- - Como $\rho(g) = \lambda ~\text{id}_V$ e $\rho$ é injetivo, temos que $\rho|_{Z(G)} : Z(G) \longrightarrow \mathbb{C}^\ast$. 
   - Mas $\rho(Z(G)) \le \mathbb{C}^\ast$ e subgrupos finitos de $\mathbb{C}^\ast$ são cíclicos. Mais ainda, seus elementos são raízes da unidade. 
   - Logo, $Z(G)$ é cíclico. -->

<!-- **Referências:**

- Ver notas do atendimento.
- Serre, Exercício 3.2. -->

### Exercício 10

**Questão:** Seja $V$ um espaço vetorial sobre $\mathbb{C}$ de dimensão finita. E seja $$ \theta : V \otimes V \longrightarrow V \otimes V $$ o operator linear tal que $\theta(v_1 \otimes v_2) = v_2 \otimes v_1$.

Mostre que $V \otimes V = \text{Sym}^2(V) \oplus \text{Alt}^2(V)$ como espaço vetorial.

**Resolução:**

<!-- - Seja $\lambda_{ij} \in \mathbb{C}$. Então
$$
\begin{aligned}
   \theta \left( \sum_{i,j} \lambda_{ij} (v_i \otimes v_j) \right) &= \sum_{i,j} \lambda_{ij} (v_j \otimes v_i) \\
   &= \sum_{i,j} \lambda_{ij} \theta (v_i \otimes v_j)
\end{aligned}
$$
- Ou seja, $\theta$ é um operador linear de $V \otimes V$. 
- Tome $x \in \text{Sym}^2(V)$ e $y \in \text{Alt}^2(V)$. Então
$$
\theta(x) = x \quad \text{ e } \quad \theta(y) = -y
$$ -->
- Se $x \in \text{Sym}^2(V) \cap \text{Alt}^2(V)$, então 
$$
x = \theta(x) = -x \implies x = 0 \implies \text{Sym}^2(V) \cap \text{Alt}^2(V) = \{ 0 \}
$$
- Para todo $x \in V \otimes V$ podemos escrever 
$$
x = \frac{1}{2}(x + \theta(x)) + \frac{1}{2}(x - \theta(x))
$$
- Como $\theta^2$ é a identidade, temos que $\frac{1}{2}(x + \theta(x)) \in \text{Sym}^2(V)$ e $\frac{1}{2}(x - \theta(x)) \in \text{Alt}^2(V)$. 
- Logo, $V \otimes V = \text{Sym}^2(V) \oplus \text{Alt}^2(V)$.

<!-- **Referências:**

- J&L Prop. 19.12 (p. 196)
- Feito em aula.  -->

### Exercício 11

**Questão:** Seja $\rho : G \longrightarrow GL(V)$ uma representação linear.

1. Mostre que $W_1 = \text{Sym}^2(V)$ e $W_2 = \text{Alt}^2$ são $(\rho \otimes \rho)(G)$-invariantes.

2. Calcule os caracteres de subrepresentações $(\rho \otimes \rho)^{W_1}$ e $(\rho \otimes \rho)^{W_2}$ usando o caracter $\chi_\rho$ de $\rho$.

**Resolução:**

1. Queremos verificar que $(\rho \otimes \rho)(g)(W_i) \subseteq W_i$ ($i = 1, 2$) para todo $g \in G$.
   - Temos as seguintes bases para $W_1$ e $W_2$: 
   $$
   \begin{aligned}
   \text{Sym}^2(V) &= \langle \{ v_i \otimes v_i, ~v_i \otimes v_j + v_j \otimes v_i \mid i < j \} \rangle \\
   \text{Alt}^2(V) &= \langle \{ v_i \otimes v_j - v_j \otimes v_i \mid i < j \} \rangle
   \end{aligned}
   $$
   - Abrindo as contas,
   $$
   \begin{aligned}
   (\rho \otimes \rho)(g)(v_i \otimes v_i) &= \rho(g)(v_i) \otimes \rho(g)(v_i) \\
   (\rho \otimes \rho)(g)(v_i \otimes v_j + v_j \otimes v_i) &= \rho(g)(v_i) \otimes \rho(g)(v_j) + \rho(g)(v_j) \otimes \rho(g)(v_i) \\
   (\rho \otimes \rho)(g)(v_i \otimes v_j - v_j \otimes v_i) &= \rho(g)(v_i) \otimes \rho(g)(v_j) - \rho(g)(v_j) \otimes \rho(g)(v_i)
   \end{aligned}
   $$

2. Caracteres de subrepresentações:
   - Denotemos por $\chi^{W_1}$ o caracter de $(\rho \otimes \rho)^{W_1}$ e por $\chi^{W_2}$, o caracter de $(\rho \otimes \rho)^{W_2}$.
   - Tome $v_1, \ldots, v_n$ base de $V$ tal que $g v_i = \lambda_i v_i$, $1 \le i \le n$ e $\lambda_i \in \mathbb{C}$.
   - Com isso, temos que $$g(v_i \otimes v_j - v_j \otimes v_i) = \lambda_i \lambda_j (v_i \otimes v_j - v_j \otimes v_i)$$ para $g \in G$ e $\lambda_i, \lambda_j \in \mathbb{C}$. 
   - Assim, $$\chi^{W_2}(g) = \sum_{i < j} \lambda_i \lambda_j$$
   - Como $g^2 v_i = \lambda_i^2 v_i$, temos
   $$
   \chi_\rho(g) = \sum_{1 \le i \le n} \lambda_i \quad \text{ e } \quad \chi_\rho(g^2) = \sum_{1 \le i \le n} \lambda_i^2
   $$
   - Portanto,
   $$
   \chi_\rho^2(g) = (\chi_\rho(g))^2 = \sum_{1 \le i \le n} \lambda_i^2 + 2 \sum_{i< j} \lambda_i \lambda_j = \chi_\rho(g^2) + 2 \chi^{W_2}(g)
   $$
   - Reordenando, 
   $$
   \chi^{W_2}(g) = \frac{1}{2} (\chi_\rho^2(g) - \chi_\rho(g^2))
   $$
   - Como $\chi_\rho^2 = \chi^{W_1} + \chi^{W_2}$,
   $$
   \chi^{W_1}(g) = \chi_\rho^2(g) - \chi^{W_2}(g) = \frac{1}{2} (\chi_\rho^2(g) + \chi_\rho(g^2))
   $$ 
   - Logo,
   $$
   \chi^{W_1}(g) = \frac{1}{2} (\chi_\rho(g)^2 + \chi_\rho(g^2)) \quad \text{ e } \quad \chi^{W_2} = \frac{1}{2} (\chi_\rho(g)^2 - \chi_\rho(g^2))
   $$

<!-- **Referências:**

- Notas de aula.
- Fulton & Harris, Prop. 2.1 e Exercise 2.2.
- James & Liebeck, Prop. 19.14. -->

### Exercício 12

**Questão:** Sejam $$\rho_1 : G \longrightarrow GL(V_1) \quad \text{ e } \quad \rho_2 : G \longrightarrow GL(V_2)$$ representações lineares com caracteres $\chi_1$ e $\chi_2$. 

Seja $W = \hom(V_1, V_2)$ o espaço vetorial de aplicações lineares $f : V_1 \longrightarrow V_2$. Para $g \in G$ e $f \in W$ definimos $$\rho(g)(f) = \rho_2(g) \circ f \circ \rho_1(g)^{-1} : V_1 \longrightarrow V_2$$ uma aplicação linear, i.e., $\rho(g)(f) \in W$. Mostrar que

1. $\rho : G \longrightarrow GL(W)$ é uma representação linear.

2. O caracter $\chi$ de $\rho$ satisfaz $\chi = \overline{\chi_1} \chi_2$.

**Resolução:**

1. É representação linear.
   - Precisamos mostrar que $\rho$ é homomorfismo de grupos. Sejam $g, h \in G$ e $f \in W$. Então
   $$
   \rho(gh)(f) = \rho_2(gh) \circ f \circ \rho_1(gh)^{-1} = (\rho_2(g) \rho_2(h)) \circ f \circ (\rho_1^{-1}(h) \rho_1^{1}(g)) = (\rho(g)\rho(h))(f)
   $$

2. Caracter de $\rho$.
   - Considere $V_1'$ o espaço dual a $V_1$. Usaremos os seguintes fatos: 
      1. Se $\rho' : G \longrightarrow GL(V')$ é representação linear tal que $$(\rho(g)(v), \rho'(g)(v')) = (v, v')$$ então o caracter de $\rho'$ é igual a $\chi'(g) = \overline{\chi(g)}$.
      2. O caracter de $\rho_1 \otimes \rho_2$ é igual a $\chi_1 \chi_2$.
   - Definamos
   $$
   \begin{aligned}
      \varphi : V_1' \otimes V_2 &\longrightarrow W \\
      v' \otimes v &\longmapsto \varphi(v' \otimes v)
   \end{aligned}
   $$
   - em que 
   $$
   \begin{aligned}
      \varphi(v' \otimes v) : V_1 & \longrightarrow V_2 \\
      x &\longmapsto (v', x) v
   \end{aligned}
   $$
   - Verificar que $\varphi$ é sobrejetora:
      - Escolha bases para $V_1$ e $V_2$ e escreva $f$ em notação matricial. 
   - Como $V_1' \otimes V_2$ e $W$ têm a mesma dimensão, segue que $\varphi$ é isomorfismo. 
   - Afirmação: $\rho(g) \circ \varphi = \varphi \circ (\rho_1'(g) \otimes \rho_2(g))$ para todo $g \in G$. Sejam $x \otimes y \in V_1' \otimes V_2$. 
   $$
   \begin{aligned}
      (\rho(g) \circ \varphi)(x \otimes y) &= \rho_2(g) \circ \varphi(x \otimes y) \circ \rho_1^{-1}(g) \\
      &= \rho_2(g) \circ (x, \rho_1^{-1}(g)) y  \\
      &= \varphi \circ (\rho_1'(g) \otimes \rho_2(g))
   \end{aligned}
   $$
   - Mas
   $$
   \varphi((\rho_1'(g) \otimes \rho_2(g))(x \otimes y)) = \varphi(\rho_1'(g)(x) \otimes \rho_2(g)(y)) = \varphi \circ (\rho_1'(g) \otimes \rho_2(g))
   $$
   - Como essa igualdade vale para $x \otimes y$, ela vale para um elemento qualquer de $V_1' \otimes V_2$. Ou seja, $\rho$ é isomorfa a $\rho_1' \otimes \rho_2$ via $\varphi^{-1}$.
   - Logo, pelos resultados listados acima, temos o que queríamos.

<!-- Serre, Exercício 2.4 -->

### Exercício 13

**Questão:** Completar as contas das tabelas de caracteres irredutíveis de $A_4$ e $S_4$.

**Resolução:**

1. $A_4$
   1. Calcular $G/G'$.
      - Considere o grupo de Klein $K = \{1, (1~2)(3~4), (1~3)(2~4), (1~4)(2~3) \} \lhd A_4$. 
      - Como $|A_4/K| = |A_4|/|K| = 12/4 = 3$, temos que $A_4/K \cong \mathbb{Z}_3$ é cíclico e, portanto, abeliano. Assim, $G' \subseteq K$. Como $G$ não é abeliano, $G'$ é não trivial. 
      - Mostremos que $G' = K$.
         - Suponha que $G' = K$ com $1 \lneqq G' \lneqq K$. Então $G' = 2$ e assim, temos $|G/G'| = |G|/|G'| = 12/2 = 6$ representações de grau $1$.
         - Se $m_1, \ldots, m_k$ são os graus das representações irredutíveis, então
            $$
            |G| = m_1^2 + \cdots + m_k^2 = \underbrace{1+\cdots+1}_{6 \text{ vezes}} + \sum_{m_i \ge 2} m_i^2 \implies 6 = \sum_{m_i \ge 2} m_i^2
            $$
         - O que é absurdo. Logo, $K = G'$.
      - Com isso, temos $$\left| \frac{G}{G'} \right| \frac{|G|}{|G'|} = \frac{12}{4} = 3$$ representações irredutíveis de grau $1$.
      - Mais ainda, $$12 = |G| = 3 + \sum_{m_i \ge 2} m_i^2$$ implica que existe uma única representação de grau maior que $1$ e esse grau é igual a $3$. 
      - Portanto, temos quatro representações irredutíveis e, assim, quatro classes de conjugação.
   
   2. Calcular classes de conjugação.
      - Já temos que $\{1\}$ e $\{ x = (1~2)(3~4), y = (1~3)(2~4), z = (1~4)(2~3) \}$ são classes de conjugação. 
      - Denotando $t = (1~2~3)$, então temos que $\{ t, tx, ty, tz \}$ e $\{ t^2, t^2x, t^2y, t^2z \}$ são classes de conjugação. 
      - Vejamos que $t$ e $t^2$ não são conjugados.
         - Se $gtg^{-1} = t^2$ em $G$, então $\overline{g} \overline{t} \overline{g^{-1}} = \overline{t^2}$ em $G/G'$, em que $\overline{g} = gG'$. 
         - Como $G/G' \cong \mathbb{Z}_3$ é abeliano, temos
         $$
         \overline{t^2} = \overline{g} \overline{t} \overline{g^{-1}} \implies \overline{t} = 1
         $$
         - Mas isso equivale a $t \in G' = K$, o que é absurdo. Logo, $t$ e $t^2$ não são conjugados.

   3. Montar tabela de caracteres irredutíveis.
      - Com isso, podemos escolher $1$, $x$, $t$ e $t^2$ como representantes das classes de conjugação.
      - Como $\langle \overline{t} \rangle \cong \mathbb{Z}^3 \cong G/G'$ e $|t| = 3 = |\overline{t}|$, temos homomorfismos de grupos $\rho_i : G/G' \longrightarrow \mathbb{C}^\ast$ tais que $\chi_i(\overline{t})^3 = \chi_i(\overline{t}^3) = \chi_i(1) = 1$, para $i = 2, 3$.
      - Assim, denotando por $\omega = \cos(2\pi/3) + i \sin(2\pi/3)$, temos que $\chi_i \in \{ 1, \omega, \omega^2 \}$, para $i = 2, 3$.
      - Portanto, temos a seguinte tabela:

         |          | $1$ | $(1~2)(3~4)$ | $(1~2~3)$ | $(1~3~2)$ |
         |:--------:|:---:|:------------:|:---------:|:---------:|
         | $\chi_1$ | $1$ |      $1$     |    $1$    |   $1$     |
         | $\chi_2$ | $1$ |      $1$     | $\omega$  | $\omega^2$|
         | $\chi_3$ | $1$ |      $1$     | $\omega^2$| $\omega$  |
         | $\chi_4$ | $3$ |     $\alpha$ | $\beta$   | $\gamma$  |

      - Pela ortogonalidade das colunas,
      $$
      \begin{aligned}
         \bar{1} \cdot 1 + \bar{1} \cdot 1 + \bar{3} \cdot \alpha = 0 &\implies \alpha = -1 \\
         \bar{1} \cdot 1 + \bar{1} \cdot \omega + \bar{1} \cdot \omega^2 + \bar{3} \cdot \beta = 0 &\implies \beta = 0 \\
         \bar{1} \cdot 1 + \bar{1} \cdot \omega^2 + \bar{1} \cdot \omega + \bar{3} \cdot \gamma = 0 &\implies \gamma = 0
      \end{aligned}
      $$
      - Logo, temos a tabela de caracteres irredutíveis:

         |          | $1$ | $(1~2)(3~4)$ | $(1~2~3)$ | $(1~3~2)$ |
         |:--------:|:---:|:------------:|:---------:|:---------:|
         | $\chi_1$ | $1$ |      $1$     |    $1$    |   $1$     |
         | $\chi_2$ | $1$ |      $1$     | $\omega$  | $\omega^2$|
         | $\chi_3$ | $1$ |      $1$     | $\omega^2$| $\omega$  |
         | $\chi_4$ | $3$ |     $-1$     |    $0$    |   $0$     |

2. $S_4$

   1. Encontrar representantes das classes de conjugação.
      <!-- - Tome $g \in S_4 \setminus \{ 1_g \}$ e escreva $g$ como produto de ciclos independentes $g = \sigma_1 \cdots \sigma_m$ tais que $|\sigma_1| \le |\sigma_2| \le \cdots \le |\sigma_m|$. -->
      - Notemos que os elementos $1$, $a = (1~2)$, $b = (1~2)(3~4)$, $c = (1~2~3)$ e $d = (1~2~3~4)$ nos dão cinco classes de conjugação distintas. 
      - E temos que as representações trivial (com caracter por $\chi_1$) e sinal (com caracter $\chi_2$) são irredutíveis de grau um. Se $m_3$, $m_4$ e $m_5$ são os graus das outras representações irredutíveis, então
      $$
      24 = |G| = 1^2 + 1^2 + m_3^2 + m_4^2 + m_5^2
      $$
      - Mas isso só é possível se $m_3 = 2$ e $m_4 = m_5 = 3$.
      - Ou seja, temos duas representações irredutíveis de grau um e, assim, $|G/G'| = 2$.  
      - Como $|S_4/A_4| = 2$, temos que $S_4/A_4 \cong \mathbb{Z}_2$ é cíclico e, portanto, abeliano. Assim, como $G' \subseteq A_4$, temos que $G' = A_4$. 

   2. Escrever a tabela de caracteres irredutíveis.
      - Podemos escrever 

         |          | $1$ | $(1~2)$ | $(1~2)(3~4)$ | $(1~2~3)$ | $(1~2~3~4)$ |
         |:--------:|:---:|:-------:|:------------:|:---------:|:-----------:|
         | $\chi_1$ | $1$ |   $1$   |      $1$     |    $1$    |     $1$     |
         | $\chi_2$ | $1$ |   $-1$  |      $1$     |    $1$    |    $-1$     |
         | $\chi_3$ | $2$ |         |              |           |             |
         | $\chi_4$ | $3$ |         |              |           |             |
         | $\chi_5$ | $3$ |         |              |           |             |

      - Fato: se $\rho_0$ é representação de grau um e $\rho$ é representação irredutível, então $\rho_0 \otimes \rho$ é representação irredutível de grau igual ao grau de $\rho$.

      - Assim, como $\chi_2$ tem grau um e $\chi_3$ é a única representação irredutível de grau dois, temos que $\chi_2 \chi_3 = \chi_3$. Isso implica que $\chi_3(1~2) = 0$ e $\chi_3(1~2~3~4)=0$.

      - Usando novamente o fato, temos que $\chi_2 \chi_4 = \chi_5$ ou $\chi_2 \chi_4 = \chi_2 \chi_4$ e $\chi_2 \chi_5 = \chi_5$.

      - Suponha que $\chi_2 \chi_4 = \chi_2 \chi_4$ e $\chi_2 \chi_5 = \chi_5$.
      
         - Então $\chi_4(a) = 0 = \chi_5(a)$ e $\chi_4(d) = 0 = \chi_5(d)$.

         - Mas como $\sum_{1 \le i \le k} \overline{\chi_i(g)} \chi_i(g) = \frac{|G|}{c(g)}$ e $c(a) = 6$, temos
            $$
            \frac{|G|}{c(A)} = \frac{24}{6} = 4 \neq 2
            $$
         
         - Assim, esse caso não é possível e, portanto, $\chi_2 \chi_4 = \chi_5$.

      - Sabemos que o grupo de Klein $K$ é subgrupo normal de $S_4$ e, mais ainda $S_4' = A_4$.

      - Como $S_4/K$ é um grupo não abeliano de ordem $24/4 = 6$, existe isomorfismo de grupos $\theta : S_4 / K \longrightarrow S_3$. 

      - Seja $\rho : S_3 \longrightarrow GL(V)$ representação irredutível de $S_3$ de grau $2$. Se $\pi : S_4 \longrightarrow S_4/K$ é a projeção canônica, então $$\rho \circ \theta \circ \pi : S_4 \longrightarrow GL(V)$$ é representação irredutível de $S_4$ de grau $2$.

      - Lembre que a tabela de $S_3$ é:

         |          | $1$ | $(1~2)$ | $(1~2~3)$ |
         |:--------:|:---:|:-------:|:---------:|
         | $\chi_1$ | $1$ |   $1$   |    $1$    |
         | $\chi_2$ | $1$ |   $-1$  |    $1$    |
         | $\chi_3$ | $2$ |   $0$   |    $-1$   |

      - Com isso, $\chi_3(b) = \rho \circ \theta \circ \pi (b) = \rho(1_{S_3}) = 2$. E também $\chi_3(c) = \rho(c) = -1$.

      - Agora considere $\rho : S_4 \longrightarrow GL(V)$ uma representação dada por $\rho(g)(e_i) = e_{g(i)}$, em que $e_1, e_2, e_3, e_4$ formam base de $V$.

      - Como $W = \mathbb{C}(e_1 + e_2 + e_3 + e_4)$ é $\rho(G)$-invariante, pelo teorema de Mashcke existe $W_0$ $\rho(G)$-invariante tal que $V = W \oplus W_0$. Ou seja, $\rho = \rho^W \oplus \rho^{W_0}$ e $\chi = \chi^W + \chi^{W_0}$.

      - Como $\dim(W) = 1$, sabemos que $\rho^W$ é irredutível. Agora como $\chi^{W_0} = \chi - \chi^W$, temos que $(\chi^{W_0}, \chi^{W_0}) = 1$.

      - Assim, $\rho^{W_0}$ é irredutível e podemos definir $\chi_4$ como o caracter de $\rho^{W_0}$ e como $\chi_2 \chi_4 = \chi_5$, podemos completar a tabela como segue.

         |          | $1$ | $(1~2)$ | $(1~2)(3~4)$ | $(1~2~3)$ | $(1~2~3~4)$ |
         |:--------:|:---:|:-------:|:------------:|:---------:|:-----------:|
         | $\chi_1$ | $1$ |   $1$   |      $1$     |    $1$    |     $1$     |
         | $\chi_2$ | $1$ |   $-1$  |      $1$     |    $1$    |    $-1$     |
         | $\chi_3$ | $2$ |   $0$   |      $2$     |    $-1$   |     $0$     |
         | $\chi_4$ | $3$ |   $1$   |     $-1$     |    $0$    |    $-1$     |
         | $\chi_5$ | $3$ |   $-1$  |     $-1$     |    $0$    |     $1$     |

         <!-- |          | $1$ | $(1~2)$ | $(1~2)(3~4)$ | $(1~2~3)$ | $(1~2~3~4)$ |
         |:--------:|:---:|:-------:|:------------:|:---------:|:-----------:|
         | $\chi_1$ | $1$ |   $1$   |      $1$     |    $1$    |     $1$     |
         | $\chi_2$ | $1$ |   $-1$  |      $1$     |    $1$    |    $-1$     |
         | $\chi_3$ | $2$ |   $0$   |      $2$     |    $-1$   |     $0$     |
         | $\chi_4$ | $3$ |         |              |           |             |
         | $\chi_5$ | $3$ |         |              |           |             | -->

   <!-- 1. Calcular $G/G'$.
      - Note que como $|S_4/A_4| = 2$, temos que $S_4/A_4 \cong \mathbb{Z}_2$ é cíclico e, portanto, abeliano. Assim, $G' \subseteq A_4$.
      - Verificar que $G' = A_4$.
         - Suponha que $G' \lneqq A_4 \lneqq G$. Então 
         $$
         2 < |G/G'| \le 5
         $$ -->

<!-- - Tabela de caracteres irredutíveis:

|          | $1$ | $(1~2)$ | $(1~2)(3~4)$ | $(1~2~3)$ | $(1~2~3~4)$ |
|:--------:|:---:|:-------:|:------------:|:---------:|:-----------:|
| $\chi_1$ | $1$ |   $1$   |      $1$     |    $1$    |     $1$     |
| $\chi_2$ | $1$ |   $-1$  |      $1$     |    $1$    |    $-1$     |
| $\chi_3$ | $2$ |   $0$   |      $2$     |    $-1$   |     $0$     |
| $\chi_4$ | $3$ |   $1$   |     $-1$     |    $0$    |    $-1$     |
| $\chi_5$ | $3$ |   $-1$  |     $-1$     |    $0$    |     $1$     | -->

<!-- **Referências:**

- James & Liebeck. 18.1 e 18.2.
- Serre, 5.7 e 5.8. -->

### Exercício 14

**Questão:** Seja $G$ um grupo e $A$ um subgrupo abeliano. Mostre que, para cada representação irredutível $\rho : G \longrightarrow GL(V)$, temos $\dim(\rho) \le [G:A]$.

Dica: para cada subespaço $\rho(A)$-invariante $W$ temos que $W_0 = \sum_{g \in G} \rho(g)(W)$ é um subespaço $\rho(G)$-invariante de $V$.

**Resolução:**

Pelo exercício 4b, $\dim(V) \le m[G:A]$, em que $m$ é a maximal dimensão de representação irredutível de $A$. Como $A$ é abeliano, toda representação irredutível de $A$ tem grau um, i.e., $m = 1$. 

### Exercício 15

**Questão:** Sejam $\rho_1 : G_1 \longrightarrow GL(V_1)$ e $\rho_2 : G_2 \longrightarrow GL(V_2)$ duas representações. E seja $\pi_i : G_1 \times G_2 \longrightarrow G_i$ o homomorfismo de grupos definido por $\pi_i(g_1, g_2) = g_i$. Definimos
$$
\hat{\rho_i} = \rho_i \circ \pi_i : G = G_1 \times G_2 \longrightarrow GL(V_i)
$$

Mostre que

1. Se $\rho_1, \rho_2$ são irredutíveis, então $\hat{\rho_1} \otimes \hat{\rho_2} : G \longrightarrow GL(V_1 \otimes V_2)$ é uma representação irredutível de $G_1 \times G_2$.

2. Cada representação irredutível de $G_1 \times G_2$ é isomorfa a $\hat{\rho_1} \otimes \hat{\rho_2}$ para algumas representações irredutíveis $\rho_1, \rho_2$.

**Resolução:**

1. $\hat{\rho_1} \otimes \hat{\rho_2}$ é irredutível.
   - Denotemos por $\chi_i$ o caracter de $\rho_i$ de $\hat{\chi_i}$ o caracter de $\hat{\rho_i}$. com $i = 1,2$. Note que, se $g_1 \in G_1$ e $g_2 \in G_2$,
   $$
   \hat{\chi_i}((g_1, g_2)) = \text{tr}(\rho_i \circ \pi_i (g_1, g_2)) = \text{tr}(\rho_i(g_i)) = \chi_i(g_i)
   $$
   - E se $\chi_{1,2}$ é o caracter de $\hat{\rho_1} \otimes \hat{\rho_2}$, então $\chi_{1,2} = \hat{\chi_1} \hat{\chi_2}$. Assim,
   $$
   \chi_{1,2}((g_1, g_2)) = \hat{\chi_1}(g_1, g_2) \hat{\chi_2}(g_1, g_2) = \chi_1(g_1) \chi_2(g_2)
   $$
   - Com isso, temos que
   $$
   \begin{aligned}
   (\chi_{1,2}, \chi_{1,2}) &= \frac{1}{|G_1 \times G_2|} \sum_{\substack{g_1 \in G_1 \\ g_2 \in G_2}} \chi_{1,2}(g_1, g_2) \overline{\chi_{1,2} (g_1, g_2)} \\
   &= \frac{1}{|G_1| |G_2|} \sum_{\substack{g_1 \in G_1 \\ g_2 \in G_2}} \chi_1(g_1) \overline{\chi_1(g_1)} \chi_2(g_2) \overline{\chi_2(g_2)} \\
   &= \left( \frac{1}{|G_1|} \sum_{g_1 \in G_1} \chi_1(g_1) \overline{\chi_1(g_1)}\right) \left( \frac{1}{|G_2|} \sum_{g_2 \in G_2} \chi_2(g_2) \overline{\chi_2(g_2)}\right) \\
   &= (\chi_1, \chi_1)_{G_1} (\chi_2, \chi_2)_{G_2}
   \end{aligned}
   $$
   - Mas como $\rho_1$ e $\rho_2$ são irredutíveis, $(\chi_1, \chi_1)_{G_1} = 1$ e $(\chi_2, \chi_2)_{G_2} = 1$.
   - Logo, $\hat{\rho_1} \otimes \hat{\rho_2}$ é irredutível.

2. Isomorfismo.
   - Sejam $\mu_1, \ldots, \mu_k$ as representações irredutíveis de $G_1$ com caracteres $\chi_1, \ldots, \chi_k$ e sejam $\nu_1, \ldots, \nu_s$ as representações irredutíveis de $G_2$ com caracteres $\tilde{\chi}_1, \ldots, \tilde{\chi}_s$.
   - Defina $$A = \{ \hat{\mu}_i \otimes \hat{\nu}_j \mid 1 \le i \le k, ~1 \le j \le s \}$$ e suponha que não há representações isomorfas em $A$. Note que, pelo item anterior, cada $\hat{\mu}_i \otimes \hat{\nu}_j$ é irredutível. Assim, construímos $k\cdot s$ representações irredutíveis.
   - Calculemos o número de classes de conjugação de $G_1 \times G_2$:
      <!-- - Tome $(g_1, g_2) \in G_1 \times G_2$ -->
      - Como podemos escrever
      $$
      G_1 = \dot{\bigcup_{t \in \{ t_1, \ldots, t_k \} }} {}^{G_1}t, \quad G_2 = \dot{\bigcup_{d \in \{ d_1, \ldots, d_s \} }} {}^{G_2}d
      $$
      - Temos
      $$
      G_1 \times G_2 = \dot{\bigcup_{\substack{t \in \{ t_1, \ldots, t_k \} \\ d \in \{ d_1, \ldots, d_s \} }}} {}^{G_1 \times G_2}(t_i, d_j)
      $$
      - Portanto, o número desejado é $k \cdot s$.
   - Assim, resta mostrar que as classes listadas em $A$ não são isomorfas entre si.
      - Seja $\chi_{i,j}$ o caracter de $\hat{\mu}_i \otimes \hat{\nu}_j$. Então
      $$
      \begin{aligned}
      (\chi_{i,j}, \chi_{\alpha, \beta})_{G_1 \times G_2} &= \frac{1}{|G_1 \times G_2|} \sum_{\substack{g_1 \in G_1 \\ g_2 \in G_2}} \chi_{i,j}(g_1, g_2) \overline{\chi_{\alpha, \beta} (g_1, g_2)} \\
      &= \frac{1}{|G_1| |G_2|} \sum_{\substack{g_1 \in G_1 \\ g_2 \in G_2}} \chi_i(g_1) \overline{\chi_\alpha(g_1)} \tilde{\chi}_j(g_2) \overline{\tilde{\chi}_\beta(g_2)} \\
      &= \left( \frac{1}{|G_1|} \sum_{g_1 \in G_1} \chi_i(g_1) \overline{\chi_\alpha(g_1)}\right) \left( \frac{1}{|G_2|} \sum_{g_2 \in G_2} \tilde{\chi}_j(g_2) \overline{\tilde{\chi}_\beta(g_2)}\right) \\
      &= (\chi_i, \chi_\alpha)_{G_1} (\tilde{\chi}_j, \tilde{\chi}_\beta)_{G_2} = \delta_{i \alpha} \delta_{j \beta}
      \end{aligned}
      $$
      - Portanto, $(\chi_{i,j}, \chi_{\alpha, \beta})_{G_1 \times G_2} = 0$ se $(i,j) \neq (\alpha, \beta)$.

<!-- **Referências:**

- Ver Serre, Theorem 10 (p. 27).
- Alternativa: https://math.stackexchange.com/questions/3602001/each-irreducible-representation-of-g-is-of-the-form-rho-1-otimes-rho-2-for -->

## Outro

### Teorema de Maschke

**Questão:** Enuncie o Teorema de Maschke.

**Resolução:** Seja $\rho : G \longrightarrow GL(V)$ uma representação linear e $W$ um subespaço $\rho(G)$-invariante de $V$. Então existe um subespaço $\rho(G)$-invariante $W_0$ tal que $V = W \oplus W_0$.

### Lema de Schur

**Questão:** Enuncie o Lema de Schur.

**Resolução:** Sejam $V_1$ e $V_2$ espaços vetoriais sobre o corpo $K$, $$ \rho_i : G \longrightarrow GL(V_i), \quad i = 1, 2$$ duas representações irredutíveis e $f : V_1 \longrightarrow V_2$ uma transformação linear sobre $K$ tal que, para cada $g \in G$, temos $$\rho_2(g) \circ f = f \circ \rho_1(g) : V_1 \longrightarrow V_2.$$

Então,

1. Se $\rho_1$ e $\rho_2$ não são isomorfos, temos que $f \equiv 0$.

2. Se $\rho_1 = \rho_2$ (e, assim, $V = V_1 = V_2$) e $\dim(V) < \infty$, então existe $\lambda \in \mathbb{C}$ tal que $f = \lambda \text{Id}_V$.

## P3 2021

### Questão 1

**Questão:** Definir o produto escalar no espaço de funções de classe de $G$. Enunciar o teorema de ortogonalidade de caracteres irredutíveis de $G$ (i.e. as condições sobre as linhas da tabela de caracteres irredutíveis). Enunciar as condições de ortogonalidade das colunas de tabela de caracteres irredutíveis.

**Resolução:**

1. Definição do produto escalar.

   Sejam $\varphi, \psi : G \longrightarrow \mathbb{C}$. Definimos
   $$
   (\varphi, \psi) = \frac{1}{|G|} \sum_{g \in G} \varphi(g) \overline{\psi(g)}
   $$

2. Ortogonalidade de caracteres irredutíveis.

   1. Se $\chi$ é o caracter de uma representação irredutível, então $(\chi, \chi) = 1$.

   2. Se $\chi_1, \chi_2$ são caracteres de representações irredutíveis não isomorfas, então $(\chi_1, \chi_2) = 0$.

3. Ortogonalidade das colunas.
   
   Sejam $g \in G$, $c(g) = |g^G|$ e $\chi_1, \ldots, \chi_k$ todos os caracteres irredutíveis não isomorfos entre si. Então:

   1. $\sum_{1 \le i \le k} \overline{\chi_i(g)} \chi_i(g) = \frac{|G|}{c(g)}$.

   2. Se $h \in G$ e $h \notin g^G$, então $\sum_{1 \le i \le k} \overline{\chi_i(g)} \chi_i(h) = 0$.

### Questão 2

**Questão:** Seja $G = P \rtimes Q$ um produto semidireto, em que $P = \mathbb{Z}_7 = \langle b \rangle$ é um subgrupo normal de $G$, $Q = \mathbb{Z}_3 = \langle a \rangle$ e $a b a^{-1} = b^4$.

1. Descrever, a menos de isomorfismo, o grupo $G/G'$.

2. Encontrar os rerpresentantes das classes de conjugação de $G$.

3. Encontrar as dimensões das representações irredutíveis de $G$.

4. Demonstrar que cada representação irredutível de $G$ de grau maior do que $1$ é uma representação induzida por uma representação de grau $1$. Descrever todas essas representações em forma matricial.

5. Descrever a tabela de caracteres de $G$.

**Resolução:**

1. $G/G'$
   - 

### Questão 3

**Questão:** Sejam $\rho : G \longrightarrow GL(V)$ uma representação e $e_1, \ldots, e_n$ uma base de $V$ como espaço vetorial sobre $\mathbb{C}$. Definimos
$$
\mu = \rho \otimes (\rho \otimes \rho) : G \longrightarrow GL(V \otimes V \otimes V)
$$

Para $\sigma \in S_3$, definimos o mapa linear
$$
\theta_\sigma : V \otimes V \otimes V \longrightarrow V \otimes V \otimes V
$$
tal que
$$
\theta_\sigma (v_1 \otimes v_2 \otimes V_3) = v_{\sigma(1)} \otimes v_{\sigma(2)} \otimes v_{\sigma(3)}
$$

E definimos
$$
W = \{ w \in V \otimes V \otimes V \mid \theta_\sigma(w) = w, ~\sigma \in S_3 \}
$$

1. Demonstre que $W$, como espaço vetorial sobre $\mathbb{C}$, tem base 
$$
\left\{ \sum_{\sigma \in S_3} e_{\sigma(i_1)} \otimes e_{\sigma(i_2)} \otimes e_{\sigma(i_3)} \mid 1 \le i_1 \le i_2 \le i_3 \le n \right\}
$$

2. Demonstre que $W$ é $\mu(G)$-invariante.

3. Calcule os caracteres de $\mu$ e de $\mu^W : G \longrightarrow GL(W)$.

**Resolução:**