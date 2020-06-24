---
title: Vecteurs et matrices dans l’informatique quantique
description: Découvrez les principes de base de l’utilisation des vecteurs et des matrices.
author: QuantumWriter
uid: microsoft.quantum.concepts.vectors
ms.author: nawiebe@microsoft.com
ms.date: 12/11/2017
ms.topic: article
no-loc:
- $
- $
- $
- $
- $
- $
- '\cdots'
- bmatrix
- '\ddots'
- '\equiv'
- '\sum'
- '\begin'
- '\end'
- '\sqrt'
- '\otimes'
- '{'
- '}'
- '\text'
- '\phi'
- '\kappa'
- '\psi'
- '\alpha'
- '\beta'
- '\gamma'
- '\delta'
- '\omega'
- '\bra'
- '\ket'
- '\boldone'
- '\\\\'
- '\\'
- =
- '\frac'
- '\text'
- '\mapsto'
- '\dagger'
- '\to'
- "\begin{cases}"
- "\end{cases}"
- '\operatorname'
- '\braket'
- '\id'
- '\expect'
- '\defeq'
- '\variance'
- '\dd'
- '&'
- "\begin{align}"
- "\end{align}"
- '\Lambda'
- '\lambda'
- '\Omega'
- '\mathrm'
- '\left'
- '\right'
- '\qquad'
- '\times'
- '\big'
- '\langle'
- '\rangle'
- '\bigg'
- '\Big'
- '|'
- '\mathbb'
- '\vec'
- '\in'
- '\texttt'
- '\ne'
- <
- '>'
- '\leq'
- '\geq'
- ~~
- "~"
- "\begin{bmatrix}"
- "\end{bmatrix}"
- '\_'
ms.openlocfilehash: f9d4e14742b7d06a6e90af0902b31fbdf17aedab
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/23/2020
ms.locfileid: "85269539"
---
# <a name="vectors-and-matrices"></a>Vecteurs et matrices

Une certaine connaissance des vecteurs et des matrices est essentielle pour comprendre l’informatique quantique. Nous fournissons une brève présentation ci-dessous et les lecteurs intéressés sont recommandés pour lire une référence standard sur l’algèbre linéaire telle que *Strang, G. (1993). Présentation de l’algèbre linéaire (vol. 3). Wellesley, MA : Wellesley-Cambridge Press* ou une référence en ligne telle que [algébrique linéaire](http://joshua.smcvt.edu/linearalgebra/).

Un vecteur de colonne (ou simplement [*Vector*](https://en.wikipedia.org/wiki/Vector_(mathematics_and_physics))) $v $ de dimension (ou taille) $n $ est une collection de $ nombres complexes $n $ (V_1, V_2, \ldots, V_n) $ organisée en tant que colonne :

$ $v = \begin{bmatrix}
v_1\\\\
v_2\\\\
\vdots\\\\
v_n \end{bmatrix}$$

La norme d’un vecteur $v $ est définie sous la forme $ \sqrt { \sum \_ i | v \_ i | 2 } $. Un vecteur est considéré comme une norme d’unité (ou il est également appelé vecteur d' [*unité*](https://en.wikipedia.org/wiki/Unit_vector)) si sa norme est $1 $ . Le [*voisin d’un vecteur*](https://en.wikipedia.org/wiki/Adjoint_matrix) $v $ est indiqué $v ^ \dagger $ et est défini comme étant le vecteur de ligne suivant où $ $ désigne \* le conjugué complexe.

$ $ \begin{ bmatrix } V_1 \\ \\ \vdots \\ \\ V_n \end{ bmatrix } ^ \dagger = \begin{ bmatrix } V_1 ^ * & \cdots & V_n ^ * \end{bmatrix}$$

La méthode la plus courante pour multiplier deux vecteurs ensemble est le [*produit interne*](https://en.wikipedia.org/wiki/Inner_product_space), également connu sous le nom de produit scalaire.  Le produit interne donne la projection d’un vecteur sur un autre et est très utile pour décrire comment exprimer un vecteur comme somme d’autres vecteurs plus simples.  Le produit interne entre $u $ et $v $ , désigné par $ \left \langle u, v, \right \rangle $ est défini comme

$ $ \langle u, v \rangle = u ^ \dagger v = u \_ 1 ^ { \* } V_1 + \cdots + u \_ n ^ { \* } v \_ n.
$$

Cette notation permet également d’écrire la norme d’un vecteur $v $ sous la forme $ \sqrt { \langle v, v \rangle } $.

Nous pouvons multiplier un vecteur par un nombre $c $ pour former un nouveau vecteur dont les entrées sont multipliées par $c $ . Nous pouvons également ajouter deux vecteurs $u $ et $v $ pour former un nouveau vecteur dont les entrées sont la somme des entrées de $u $ et $v $ . Ces opérations sont décrites ci-dessous :

$ $ \mathrm{If } ~ u = \begin{bmatrix}
u_1\\\\
u_2\\\\
\vdots\\\\
u_n \end{ bmatrix } ~ \mathrm{and } ~ v = \begin{bmatrix}
    v_1\\\\
    v_2\\\\
    \vdots\\\\
    V_n \end{ bmatrix } , ~ \mathrm{Then } ~ au + BV = \begin{bmatrix}
au_1 + bv_1\\\\
au_2 + bv_2\\\\
\vdots\\\\
au_n + bv_n \end{ bmatrix } .
$$

Une [*matrice*](https://en.wikipedia.org/wiki/Matrix_(mathematics)) de taille $m \times n $ est une collection de $mn $ nombres complexes organisés en $m $ lignes et $n $ colonnes, comme indiqué ci-dessous :

$ $M = \begin{bmatrix}
M_ {11 } ~ ~ m_ {12 } ~ ~ \cdots ~ ~ m_ {1N } \\ \\ m_ {21 } ~ ~ m_ {22 } ~ ~ \cdots ~ ~ m_ {2n } \\ \\ \ddots\\\\
M_ {M1 } ~ ~ m_ {m2 } ~ ~ \cdots ~ ~ m_ {mn } \\ \\ \end{ bmatrix } . $ $

Notez qu’un vecteur de dimension $n $ est simplement une matrice de taille $n \times 1 $ . Comme pour les vecteurs, nous pouvons multiplier une matrice par un nombre $c $ pour obtenir une nouvelle matrice où chaque entrée est multipliée par $c $ , et nous pouvons ajouter deux matrices de même taille pour produire une nouvelle matrice dont les entrées sont la somme des entrées respectives des deux matrices. 

## <a name="matrix-multiplication-and-tensor-products"></a>Produits de multiplication de matrice et tenseur

Nous pouvons également multiplier deux matrices $M $ de la dimension $m \times n $ et $N $ de dimension $n \times p $ pour obtenir une nouvelle $P de matrice $m $ \times p $ comme suit :

\begin{align}
& \begin{bmatrix}
    M_ {11 } ~ ~ m_ {12 } ~ ~ \cdots ~ ~ m_ {1N } \\ \\ m_ {21 } ~ ~ m_ {22 } ~ ~ \cdots ~ ~ m_ {2n } \\ \\ \ddots\\\\
    M_ {M1 } ~ ~ m_ {m2 } ~ ~ \cdots ~ ~ m_ {mn}
effetbmatrix}
commencerbmatrix}
N_ {11 } ~ ~ n_ {12 } ~ ~ \cdots ~ ~ n_ {1P } \\ \\ n_ {21 } ~ ~ n_ {22 } ~ ~ \cdots ~ ~ n_ {2p } \\ \\ \ddots\\\\
N_ {N1 } ~ ~ n_ {N2 } ~ ~ \cdots ~ ~ n_ {NP}
\end{ bmatrix } = \begin{bmatrix}
P_ {11 } ~ ~ P_ {12 } ~ ~ \cdots ~ ~ P_ {1P } \\ \\ P_ {21 } ~ ~ P_ {22 } ~ ~ \cdots ~ ~ P_ {2p } \\ \\ \ddots\\\\
P_ {M1 } ~ ~ P_ {m2 } ~ ~ \cdots ~ ~ P_ {MP}
effetbmatrix}
\end{align}

où les entrées de $P $ sont $P _ {ik } = \ sum_j m_ {ij} n_ {JK } $. Par exemple, l’entrée $P _ {11 } $ est le produit interne de la première ligne de $M $ avec la première colonne de $N $ . Notez que dans la mesure où un vecteur est simplement un cas particulier d’une matrice, cette définition s’étend à la multiplication de vecteurs de matrice. 

Toutes les matrices que nous considérons sont des matrices carrées, où le nombre de lignes et de colonnes est égal, ou vecteurs, qui correspond uniquement à $1 $ colonne. Une matrice carrée spéciale est la [*matrice d’identité*](https://en.wikipedia.org/wiki/Identity_matrix), dénotée $ \boldone $ , dont tous les éléments diagonales sont égaux à $1 $ et les éléments restants égaux à $0 $ :

$ $ \boldone = \begin{bmatrix}
1 ~ ~ 0 ~ ~ \cdots ~ ~ 0\\\\
0 ~ ~ 1 ~ ~ \cdots ~ ~ 0\\\\
~ ~ \ddots\\\\
0 ~ ~ 0 ~ ~ \cdots ~ ~ 1 \end{ bmatrix } . $ $

Pour un $A de matrice carrée $ , nous disons qu’une matrice $B $ est son [*inverse*](https://en.wikipedia.org/wiki/Invertible_matrix) si $AB = BA = \boldone $ . L’inverse d’une matrice n’a pas besoin d’exister, mais lorsqu’elle existe, elle est unique et nous la dénotarons $A ^ {-1 } $. 

Pour les $M de matrices $ , la transpose de $M voisine ou conjuguée $ est une matrice $N $ telle que $N _ {IJ } = m_ {ji } ^ \* $. Le voisint de $M $ est généralement indiqué $M ^ \dagger $ . Nous disons qu’un $U de matrice $ est [*unitaire*](https://en.wikipedia.org/wiki/Unitary_matrix) si $uu ^ \dagger = U ^ \dagger U = \boldone $ ou équivalent, $U ^ {-1 } = u ^ \dagger $ .  La propriété la plus importante des matrices unitaires est peut-être qu’elle conserve la norme d’un vecteur.  Cela se produit car 

$ $ \langle v, v \rangle = v ^ \dagger v = v ^ \dagger U ^ {-1 } u v = v ^ \Dagger u ^ \Dagger u v = \Langle u v, u v \rangle . $ $  

Une $M de matrice $ est dite [*Hermitian*](https://en.wikipedia.org/wiki/Hermitian_matrix) si $M = M ^ \dagger $ .

Enfin, le [*produit tenseur*](https://en.wikipedia.org/wiki/Tensor_product) (ou le produit Kronecker) de deux matrices $M $ de taille $m \times n $ et $N $ de taille $p \times q $ est une matrice plus grande $P = M \otimes n $ de taille $mp \times nq $ et est obtenue à partir de $M $ et $N $ comme suit :

\begin{align}
    M \otimes N &= \begin{bmatrix}
        M_ {11 } ~ ~ \cdots ~ ~ m_ {1N } \\ \\ \ddots\\\\
        M_ {M1 } ~ ~ \cdots ~ ~ m_ {mn}
    effetbmatrix}
    \otimes \begin{bmatrix}
        N_ {11 } ~ ~ \cdots ~ ~ n_ {1t } \\ \\ \ddots\\\\
        N_ {P1 } ~ ~ \cdots ~ ~ n_ {PQ}
    \end{ bmatrix } \\ \\ &= \begin{bmatrix}
        M_ {11 } \begin{ bmatrix } n_ {11 } ~ ~ \cdots ~ ~ n_ {1t } \\ \\ \ddots \\\\ n_ {P1 } ~ ~ \cdots ~ ~ n_ {PQ } \end{ bmatrix } ~ ~ \cdots ~ ~ m_ {1N } \begin{ bmatrix } n_ {11 } ~ ~ \cdots ~ ~ n_ {1t } \\ \\ \ddots \\\\ n_ {P1 } ~ ~ \cdots ~ ~ n_ {PQ } \end{ bmatrix } \\ \\ \ddots\\\\
        M_ {M1 } \begin{ bmatrix } n_ {11 } ~ ~ \cdots ~ ~ n_ {1t } \\ \\ \ddots \\\\ n_ {P1 } ~ ~ \cdots ~ ~ n_ {PQ } \end{~ ~ bmatrix } \cdots ~ ~ m_ {mn } \begin{ bmatrix } n_ {11 } ~ ~ \cdots ~ ~ n_ {1t } \\ \\ \ddots \\\\ n_ {P1 } ~ ~ \cdots ~ ~ n_ {PQ } \end{bmatrix}
    \end{ bmatrix } .
\end{align}

Cette solution est mieux illustrée par des exemples :

$ $ \begin{bmatrix}
        a \\ \\ b \end{ bmatrix } \otimes \begin{ bmatrix } c \\ \\ d \\ \\ e \end{ bmatrix } = \begin{bmatrix}
        \begin{ bmatrix } c \\ \\ d \\ \\ \end{bmatrix}
        \\\\[1.5 em] b \begin{ bmatrix } c \\ \\ d \\ \\ e\end{bmatrix}
    effetbmatrix}
    = \begin{ bmatrix } a c a \\ \\ d a \\ \\ e \\ \\ b c \\ \\ b \\ \\\end{bmatrix}
$$

et

$ $ \begin{bmatrix}
        a \ b \\ \\ c \ d \end{bmatrix}
    \otimes \begin{bmatrix}
        e \ f \\ \\ v \ h \end{bmatrix}
     = \begin{bmatrix}
    un\begin{bmatrix}
    e \ f \\\\ v \ h \end{bmatrix}
    p\begin{bmatrix}
    e \ f \\\\ v \ h \end{bmatrix}
    \\\\[1em] c\begin{bmatrix}
    e \ f \\\\ v \ h \end{bmatrix}
    e\begin{bmatrix}
    e \ f \\\\ v \ h \end{bmatrix}
    effetbmatrix}
    = \begin{bmatrix}
    AE \ AF \ est \ BF \\ \\ AG \ Ah \ BG \ BH \\ \\ ce \ CF \ de \ DF \\ \\ CG \ ch \ DG \ DH \end{ bmatrix } .
$$

La dernière convention de notation utile entourant les produits tenseur est que, pour n’importe quel vecteur $v $ ou $M de matrice $ , $v ^ {\otimes n } $ ou $M ^ {\otimes n } $ est la main pour un $ produit tenseur répété $n.  Par exemple :

\begin{align}
& \begin{ bmatrix } 1 \\ \\ 0 \end{ bmatrix } ^ {\otimes 1 } = \begin{ bmatrix } 1 \\ \\ 0 \end{ bmatrix } , \qquad \begin{bmatrix} 1 \\ \\ 0 \end{ bmatrix } ^ {\otimes 2 } = \begin{ bmatrix } 1 \\ \\ 0 \\ \\ 0 \\ \\ 0 \end{ bmatrix } , \qquad \begin{bmatrix} 1 \\ \\ -1 \end{ bmatrix } ^ {\otimes 2 } = \begin{ bmatrix } 1 \\ \\ -1 \\ \\ -1 \\ \\ 1 \end{ bmatrix } , \\ \\ & \begin{ bmatrix } 0 & 1 \\ \\ 1 & 0 \end{ bmatrix } ^ {\otimes 1 } = \begin{ bmatrix } 0 & 1 \\ \\ 1 & 0 \end{ bmatrix } , \qquad \begin{bmatrix} 0 & 1 \\ \\ 1 & 0 \end{ bmatrix } ^ {\otimes 2 } = \begin{ bmatrix } 0 &0&0&1 \\ \\ 0 &0&1&0 0 &1&0 \\ \\&0 \\\\ 1 &0&0&0 \end{bmatrix} .
\end{align}
