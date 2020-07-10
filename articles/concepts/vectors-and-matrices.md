---
titre : vecteurs et matrices dans quantum computing Description : Découvrez les principes de base de l’utilisation des vecteurs et des matrices.
Auteur : QuantumWriter UID : Microsoft. Quantum. concepts. vectors ms. Author : nawiebe@microsoft.com ms. Date : 12/11/2017 ms. topic : article No-Loc :
- "$$"
- "$$"
- "$"
- "$"
- "$"
- "$$"
- "\cdots"
- "bmatrix"
- "\ddots"
- "\equiv"
- "\sum"
- "\begin"
- "\end"
- "\sqrt"
- "\otimes"
- "{"
- "}"
- "\text"
- "\phi"
- "\kappa"
- "\psi"
- "\alpha"
- "\beta"
- "\gamma"
- "\delta"
- "\omega"
- "\bra"
- "\ket"
- "\boldone"
- "\\\\"
- "\\"
- "="
- "\frac"
- "\text"
- "\mapsto"
- "\dagger"
- "\to"
- "\begin{cases}"
- "\end{cases}"
- "\operatorname"
- "\braket"
- "\id"
- "\expect"
- "\defeq"
- "\variance"
- "\dd"
- "&"
- "\begin{align}"
- "\end{align}"
- "\Lambda"
- "\lambda"
- "\Omega"
- "\mathrm"
- "\left"
- "\right"
- "\qquad"
- "\times"
- "\big"
- "\langle"
- "\rangle"
- "\bigg"
- "\Big"
- "|"
- "\mathbb"
- "\vec"
- "\in"
- "\texttt"
- "\ne"
- "<"
- ">"
- "\leq"
- "\geq"
- "~~"
- "~"
- "\begin{bmatrix}"
- "\end{bmatrix}"
- "\_"

---

# <a name="vectors-and-matrices"></a>Vecteurs et matrices

Une certaine connaissance des vecteurs et des matrices est essentielle pour comprendre l’informatique quantique. Nous fournissons une brève présentation ci-dessous et les lecteurs intéressés sont recommandés pour lire une référence standard sur l’algèbre linéaire telle que *Strang, G. (1993). Présentation de l’algèbre linéaire (vol. 3). Wellesley, MA : Wellesley-Cambridge Press* ou une référence en ligne telle que [algébrique linéaire](http://joshua.smcvt.edu/linearalgebra/).

Un vecteur de colonne (ou simplement [*Vector*](https://en.wikipedia.org/wiki/Vector_(mathematics_and_physics))) $ v $ de dimension (ou taille) $ n $ est une collection de $ n $ nombres complexes $ (V_1, V_2, \ldots, V_n) $ organisés en tant que colonne :

$$v=\begin{bmatrix}
v_1\\\\
v_2\\\\
\vdots\\\\
v_n\end{bmatrix}$$

La norme d’un vecteur $ v $ est définie comme $ \sqrt { \sum \_ i | v \_ | ^ 2 } $ . Un vecteur est considéré comme une norme d’unité (ou il est également appelé vecteur d' [*unité*](https://en.wikipedia.org/wiki/Unit_vector)) si sa norme est $ 1 $ . Le [*voisin d’un vecteur*](https://en.wikipedia.org/wiki/Adjoint_matrix) $ v $ est désigné $ v ^ \dagger $ et est défini comme étant le vecteur de ligne suivant, où désigne $ \* $ le conjugué complexe.

$$\begin{bmatrix}V_1 \\\\ \vdots \\\\ V_n \end{bmatrix} ^ \dagger = \begin{bmatrix} V_1 ^ * & \cdots & V_n ^ *\end{bmatrix}$$

La méthode la plus courante pour multiplier deux vecteurs ensemble est le [*produit interne*](https://en.wikipedia.org/wiki/Inner_product_space), également connu sous le nom de produit scalaire.  Le produit interne donne la projection d’un vecteur sur un autre et est très utile pour décrire comment exprimer un vecteur comme somme d’autres vecteurs plus simples.  Le produit interne entre $ u $ et $ v $ , désigné $ \left \langle u, v, \right \rangle $ est défini comme

$$
\langleu, v \rangle = u ^ \dagger v = u \_ 1 ^ { \* } V_1 + \cdots + u \_ n ^ { \* } v \_ n.
$$

Cette notation permet également d’écrire la norme d’un vecteur $ v $ sous la forme $ \sqrt { \langle v, v \rangle } $ .

Nous pouvons multiplier un vecteur par un nombre $ c $ pour former un nouveau vecteur dont les entrées sont multipliées par $ c $ . Nous pouvons également ajouter deux vecteurs $ u $ et $ v $ pour former un nouveau vecteur dont les entrées sont la somme des entrées de $ u $ et $ v $ . Ces opérations sont décrites ci-dessous :

$$\mathrm{Si } ~ u=\begin{bmatrix}
u_1\\\\
u_2\\\\
\vdots\\\\
u_n \end{bmatrix} ~ \mathrm { et}~
v=\begin{bmatrix}
    v_1\\\\
    v_2\\\\
    \vdots\\\\
    V_n \end{bmatrix} , ~ \mathrm { puis}~
au + BV=\begin{bmatrix}
au_1 + bv_1\\\\
au_2 + bv_2\\\\
\vdots\\\\
au_n + bv_n \end{bmatrix} .
$$

Une [*matrice*](https://en.wikipedia.org/wiki/Matrix_(mathematics)) de taille $ m \times n $ est une collection de $ mn $ nombres complexes organisés en $ m $ lignes et $ n $ colonnes, comme indiqué ci-dessous :

$$Lecteur= 
\begin{bmatrix}
M_ { 11 } ~~ m_ { 12 } ~~ \cdots ~~ m_ { 1N}\\\\
M_ { 21 } ~~ m_ { 22 } ~~ \cdots ~~ m_ { 2n}\\\\
\ddots\\\\
M_ { M1 } ~~ m_ { m2 } ~~ \cdots ~~ m_ { mn}\\\\
\end{bmatrix}.$$

Notez qu’un vecteur de dimension $ n $ est simplement une matrice de taille $ n \times 1 $ . Comme pour les vecteurs, nous pouvons multiplier une matrice avec un nombre $ c $ pour obtenir une nouvelle matrice où chaque entrée est multipliée par $ c $ , et nous pouvons ajouter deux matrices de même taille pour produire une nouvelle matrice dont les entrées sont la somme des entrées respectives des deux matrices. 

## <a name="matrix-multiplication-and-tensor-products"></a>Produits de multiplication de matrice et tenseur

Nous pouvons également multiplier deux matrices $ m $ de dimension $ m \times n $ et $ n $ de dimension $ n \times p $ pour obtenir une nouvelle matrice $ p $ de dimension $ m \times p $ comme suit :

\begin{align}
&\begin{bmatrix}
    M_ { 11 } ~~ m_ { 12 } ~~ \cdots ~~ m_ { 1N}\\\\
    M_ { 21 } ~~ m_ { 22 } ~~ \cdots ~~ m_ { 2n}\\\\
    \ddots\\\\
    M_ { M1 } ~~ m_ { m2 } ~~ \cdots ~~ m_ { mn}
\end{bmatrix}
\begin{bmatrix}
N_ { 11 } ~~ n_ { 12 } ~~ \cdots ~~ n_ { 1P}\\\\
N_ { 21 } ~~ n_ { 22 } ~~ \cdots ~~ n_ { 2p}\\\\
\ddots\\\\
N_ { N1 } ~~ n_ { N2 } ~~ \cdots ~~ n_ { NP}
\end{bmatrix}=\begin{bmatrix}
P_ { 11 } ~~ P_ { 12 } ~~ \cdots ~~ P_ { 1P}\\\\
P_ { 21 } ~~ P_ { 22 } ~~ \cdots ~~ P_ { 2p}\\\\
\ddots\\\\
{Pack d' } ~~ { } ~~ \cdots ~~ P_ { P_ M1 P_ m2}
\end{bmatrix}
\end{align}

où les entrées de $ P $ sont $ P_ { ik } = \sum _j M_ { IJ } n_ { JK } $ . Par exemple, l’entrée $ P_ { 11 } $ est le produit interne de la première ligne de $ M $ avec la première colonne de $ N $ . Notez que dans la mesure où un vecteur est simplement un cas particulier d’une matrice, cette définition s’étend à la multiplication de vecteurs de matrice. 

Toutes les matrices que nous considérons sont des matrices carrées, où le nombre de lignes et de colonnes est égal, ou vecteurs, qui correspond uniquement à $ 1 $ colonne. Une matrice carrée spéciale est la [*matrice d’identité*](https://en.wikipedia.org/wiki/Identity_matrix), dénotée $ \boldone $ , dont tous les éléments diagonales sont égaux à $ 1 $ et les éléments restants égaux à $ 0 $ :

$$\boldone=\begin{bmatrix}
1 ~~ 0 ~~ 0 \cdots ~~\\\\
0 ~~ 1 ~~ \cdots ~~ 0\\\\
~~ \ddots\\\\
0 ~~ 0 ~~ \cdots ~~ 1 \end{bmatrix} .$$

Pour une matrice carrée $ a $ , nous disons qu’une matrice $ B $ est son [*inverse*](https://en.wikipedia.org/wiki/Invertible_matrix) si $ AB = BA = \boldone $ . L’inverse d’une matrice n’a pas besoin d’exister, mais lorsqu’elle existe, elle est unique et nous la dénotarons $ { en ^-1 } $ . 

Pour n’importe quelle matrice $ m $ , la permutation de voisins ou de conjugués de $ m $ est une matrice $ N $ telle que $ n_ { IJ } = m_ { ji } ^ \* $ . Le voisint de $ m $ est généralement le signe $ m ^ \dagger $ . Nous disons qu’une matrice $ U $ est [*unitaire*](https://en.wikipedia.org/wiki/Unitary_matrix) si $ uu ^ \dagger = u ^ \dagger u = \boldone $ ou équivalent, $ u ^ { -1 } = u ^ \dagger $ .  La propriété la plus importante des matrices unitaires est peut-être qu’elle conserve la norme d’un vecteur.  Cela se produit car 

$$\langlev, v \rangle = v ^ \dagger v v = ^ \dagger u ^ { -1 } U v v = ^ \dagger u ^ u v u v \dagger = \langle , u v \rangle .$$  

Une matrice $ m $ est dite [*Hermitian*](https://en.wikipedia.org/wiki/Hermitian_matrix) si $ m = m ^ \dagger $ .

Enfin, le [*produit tenseur*](https://en.wikipedia.org/wiki/Tensor_product) (ou le produit Kronecker) de deux matrices $ m $ de taille $ m \times n $ et $ n $ de taille $ p \times q $ est une matrice plus grande $ p = m \otimes n $ de taille $ MP \times NQ $ et est obtenue à partir de $ M $ et $ n $ comme suit :

\begin{align}
    M \otimes N&=
    \begin{bmatrix}
        M_ { 11 } ~~ \cdots ~~ m_ { 1N }\\\\
        \ddots\\\\
        M_ { M1 } ~~ \cdots ~~ m_ { mn  }
    \end{bmatrix}
    \otimes
    \begin{bmatrix}
        N_ { 11 } ~~ \cdots ~~ n_ { 1t  }\\\\
        \ddots\\\\
        N_ { P1 } ~~ \cdots ~~ n_ { PQ}
    \end{bmatrix}\\\\
    &=
    \begin{bmatrix}
        M_ { 11 } \begin{bmatrix} n_ { 11 } ~~ \cdots ~~ n_ { 1t } \\\\ \ddots \\\\ n_ { P1 } ~~ \cdots ~~ n_ { PQ } \end{bmatrix} ~~ \cdots  ~~ 
        M_ { 1N } \begin{bmatrix} n_ { 11 } ~~ \cdots ~~ n_ { 1t } \\\\ \ddots \\\\ n_ { P1 } ~~ \cdots ~~ n_ { PQ }  \end{bmatrix}\\\\
        \ddots\\\\
        M_ { M1 } \begin{bmatrix} n_ { 11 } ~~ \cdots ~~ n_ { 1t } \\\\ \ddots \\\\ n_ { P1 } ~~ \cdots ~~ n_ { PQ } \end{bmatrix} ~~ \cdots  ~~ 
        M_ { mn } \begin{bmatrix} n_ { 11 } ~~ \cdots ~~ n_ { 1t } \\\\ \ddots \\\\ n_ { P1 } ~~ \cdots ~~ n_ { PQ }  \end{bmatrix}
    \end{bmatrix}.
\end{align}

Cette solution est mieux illustrée par des exemples :

$$
    \begin{bmatrix}
        a \\\\ b \end{bmatrix} \otimes \begin{bmatrix} c \\\\ \\\\ d \end{bmatrix}=
    \begin{bmatrix}
        \begin{bmatrix}c \\\\ d \\\\ e\end{bmatrix}
        \\\\[1.5 em] b \begin{bmatrix} c \\\\ d \\\\ e\end{bmatrix}
    \end{bmatrix}
    =\begin{bmatrix}un c \\\\ a d \\\\ a e \\\\ b c \\\\ b \\\\ est\end{bmatrix}
$$

et

$$
    \begin{bmatrix}
        a \ b \\\\ c \ d\end{bmatrix}
    \otimes 
    \begin{bmatrix}
        e \ f \\\\ g \ h\end{bmatrix}
     =
    \begin{bmatrix}
    un\begin{bmatrix}
    e \ f \\\\ g \ h\end{bmatrix}
    p\begin{bmatrix}
    e \ f \\\\ g \ h\end{bmatrix}
    \\\\[1em] c\begin{bmatrix}
    e \ f \\\\ g \ h\end{bmatrix}
    e\begin{bmatrix}
    e \ f \\\\ g \ h\end{bmatrix}
    \end{bmatrix}
    =
    \begin{bmatrix}
    AE \ AF \ est \ BF\\\\
    AG \ Ah \ BG \ BH\\\\
    ce \ CF \ de \ DF\\\\
    CG \ ch \ DG \ DH \end{bmatrix} .
$$

La dernière convention de notation utile entourant les produits tenseur est que, pour n’importe quel vecteur $ v $ ou matrice $ m $ , $ v ^ { \otimes n } $ ou $ M ^ { \otimes n } $ est la main pour un $ $ produit tenseur répété à n plis.  Par exemple :

\begin{align}
&\begin{bmatrix}1 \\\\ 0 \end{bmatrix} ^ { \otimes 1 } = \begin{bmatrix} 1 \\\\ 0 \end{bmatrix} , \qquad \begin{bmatrix} 1 \\\\ 0 2 1 0 0 0 \end{bmatrix} ^ { \otimes } = \begin{bmatrix} \\\\ \\\\ \\\\ \end{bmatrix} , \qquad \begin{bmatrix} 1 \\\\ -1 \end{bmatrix} ^ { \otimes 2 } = \begin{bmatrix} 1 \\\\ -1 \\\\ -1 \\\\ 1 \end{bmatrix} ,\\\\
  &\begin{bmatrix}0 & 1 \\\\ 1 & 0 \end{bmatrix} ^ { \otimes 1 } = \begin{bmatrix} 0 & 1 \\\\ 1 & 0 \end{bmatrix} , \qquad \begin{bmatrix} 0 & 1 \\\\ 1 0 & \end{bmatrix} ^ { 2 \otimes } = \begin{bmatrix} & & & \\\\ & & & \\\\ & & & \\\\ & & & \end{bmatrix} 0 0 0 0 1 0 0 1 0 0 1 0 0 1 0 0 0.
\end{align}
