---
title: Vecteurs et matrices | Microsoft Docs
description: Vecteurs et matrices
author: QuantumWriter
uid: microsoft.quantum.concepts.vectors
ms.author: nawiebe@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: 58c96f9cda22b712e1a408e5566e0a8ee987bd6e
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/26/2019
ms.locfileid: "73183741"
---
# <a name="vectors-and-matrices"></a>Vecteurs et matrices

Une certaine connaissance des vecteurs et des matrices est essentielle pour comprendre l’informatique quantique. Nous fournissons une brève présentation ci-dessous et les lecteurs intéressés sont recommandés pour lire une référence standard sur l’algèbre linéaire telle que *Strang, G. (1993). Présentation de l’algèbre linéaire (vol. 3). Wellesley, MA : Wellesley-Cambridge Press* ou une référence en ligne telle que [algébrique linéaire](http://joshua.smcvt.edu/linearalgebra/).

Un vecteur de colonne (ou simplement [*Vector*](https://en.wikipedia.org/wiki/Vector_(mathematics_and_physics))) $v $ de dimension (ou taille) $n $ est une collection de $n nombre complexe $ (V_1, V_2, \ldots, V_n) $ organisé en tant que colonne :

$ $v = \begin{bmatrix} V_1\\\\ V_2\\\\ \vdots\\\\ V_n \end{bmatrix} $ $

La norme d’un vecteur $v $ est définie sous la forme $ \sqrt{\sum\_i | v\_i | ^ 2} $. Un vecteur est considéré comme une norme d’unité (ou il est également appelé vecteur d' [*unité*](https://en.wikipedia.org/wiki/Unit_vector)) si sa norme est $1 $. Le [*voisin d’un vecteur*](https://en.wikipedia.org/wiki/Adjoint_matrix) $v $ est indiqué $v ^ \dagger $ et est défini comme étant le vecteur de ligne suivant où $\*$ désigne le conjugué complexe,

$ $ \begin{bmatrix}V_1 \\\\ \vdots \\\\ V_n \end{bmatrix} ^ \dagger = \begin{bmatrix}V_1 ^ * & \cdots & V_n ^ * \end{bmatrix} $ $

La méthode la plus courante pour multiplier deux vecteurs ensemble est le [*produit interne*](https://en.wikipedia.org/wiki/Inner_product_space), également connu sous le nom de produit scalaire.  Le produit interne donne la projection d’un vecteur sur un autre et est très utile pour décrire comment exprimer un vecteur comme somme d’autres vecteurs plus simples.  Le produit interne entre $u $ et $v $, indiqué $ \left\langle u, v\right\rangle $ est défini comme

$ $ \langle u, v\rangle = u ^ \dagger v = u\_1 ^ {\*} V_1 + \cdots + u\_n ^ {\*} v\_n.
$$

Cette notation autorise également l’écriture de la norme d’un vecteur $v $ en tant que $ \sqrt{\langle v, v\rangle} $.

Nous pouvons multiplier un vecteur par un nombre $c $ pour former un nouveau vecteur dont les entrées sont multipliées par $c $. Nous pouvons également ajouter deux vecteurs $u $ et $v $ pour former un nouveau vecteur dont les entrées sont la somme des entrées de $u $ et $v $. Ces opérations sont décrites ci-dessous :

$ $ \mathrm{If} ~ u = \begin{bmatrix} u_1\\\\ u_2\\\\ \vdots\\\\ u_n \end{bmatrix} ~ \mathrm{and} ~ v = \begin{bmatrix} V_1\\\\ V_2\\\\ \vdots @no__ t_10_ \\ V_n \end{bmatrix}, ~ \mathrm{Then} ~ au + BV = \begin{bmatrix} AU_1 + bv_1\\\\ au_2 + bv_2\\\\ \vdots\\\\ au_n + bv_n \end{bmatrix}.
$$

Une [*matrice*](https://en.wikipedia.org/wiki/Matrix_(mathematics)) de taille $m \times n $ est une collection de $mn des nombres complexes organisés en $m $ rows et $n $ Columns, comme indiqué ci-dessous :

$ $M = \begin{bmatrix} _ m{11} ~ ~ m{12} ~ ~ \cdots ~ ~ m {1N}\\\\ m{21} ~ ~ m{22} ~ ~ \cdots ~ ~ m {2n}\\\\ \ddots\\\\ m {M1} ~ ~ m {m2} ~ ~ \cdots ~ ~ m {mn}\\@no__ t_11_ \end{bmatrix}. $ $

Notez qu’un vecteur de dimension $n $ est simplement une matrice de taille $n \times $1. Comme pour les vecteurs, nous pouvons multiplier une matrice par un nombre $c $ pour obtenir une nouvelle matrice où chaque entrée est multipliée par $c $, et nous pouvons ajouter deux matrices de même taille pour produire une nouvelle matrice dont les entrées sont la somme des entrées respectives des deux matrices. 

## <a name="matrix-multiplication-and-tensor-products"></a>Produits de multiplication de matrice et tenseur

Nous pouvons également multiplier deux matrices $M $ de dimension $m \times n $ et $N $ de dimension $n \times p $ pour obtenir une nouvelle matrice $P $ de dimension $m \times p $ comme suit :

\begin{align} & \begin{bmatrix} m{11} ~ ~ m{12} ~ ~ \cdots ~ ~ m {1N}\\\\ m{21} ~ ~ m{22} ~ ~ \cdots ~ ~ m {2n}\\\\ \ddots\\\\ m {M1} ~ ~ m {m2} ~ ~ \cdots ~ ~ m {mn} \end{bmatrix} \ BEGIN {bmatrix} n_{11} ~ ~ n_{12} ~ ~ \cdots ~ ~ n_ {1P}\\\\ n_{21} ~ ~ n_{22} ~ ~ \cdots ~ ~ n_ {2p}\\\\ \ddots\\\\ n_ {N1} ~ ~ n_ {N2} ~ ~ \cdots ~ ~ n_ {NP} \end{bmatrix} = \begin{bmatrix} P_{11} ~ ~ P_{12} ~ ~ \cdots ~ ~ P_ {1P}\\\\ P_{21} ~ ~ P_{22} ~ ~ \cdots ~ ~ P_ {2p}\\\\ \ddots\\\\ P_ {M1} ~ ~ P_ {m2} ~ ~ \cdots ~ ~ P_ {MP} \end{bmatrix} \end{align}

où les entrées de $P $ sont $P _ {ik} = \sum_j _ m {ij} n_ {JK} $. Par exemple, l’entrée $P _{11}$ est le produit interne de la première ligne de $M $ avec la première colonne de $N $. Notez que dans la mesure où un vecteur est simplement un cas particulier d’une matrice, cette définition s’étend à la multiplication de vecteurs de matrice. 

Toutes les matrices que nous considérons sont des matrices carrées, où le nombre de lignes et de colonnes est égal, ou vecteurs, qui correspond uniquement à $1 $ colonne. Une matrice carrée spéciale est la [*matrice d’identité*](https://en.wikipedia.org/wiki/Identity_matrix), dénotée $ \boldone $, dont tous les éléments diagonales sont égaux à $1 $ et les éléments restants égaux à $0 $ :

$ $ \boldone = \begin{bmatrix} 1 ~ ~ 0 ~ ~ \cdots ~ ~ 0\\\\ 0 ~ ~ 1 ~ ~ \cdots ~ ~ 0\\\\ ~ ~ \ddots\\\\ 0 ~ ~ 0 ~ ~ \cdots ~ ~ 1 \end{bmatrix}. $ $

Pour une matrice carrée $A $, nous disons une matrice $B $ est son [*inverse*](https://en.wikipedia.org/wiki/Invertible_matrix) si $AB = BA = \boldone $. L’inverse d’une matrice n’a pas besoin d’exister, mais lorsqu’elle existe, elle est unique et nous la dénotarons $A ^{-1}$. 

Pour n’importe quelle matrice $M $, la permutation de voisins ou de conjugués de $M $ est une matrice $N $ telle que $N _ {IJ} = m {ji} ^\*$. Le voisin de $M $ est généralement indiqué $M ^ \dagger $. Nous disons qu’une matrice $U $ est [*unitaire*](https://en.wikipedia.org/wiki/Unitary_matrix) si $uu ^ \Dagger = u ^ \dagger U = \boldone $ ou équivalent, $U ^{-1} = u ^ \dagger $.  La propriété la plus importante des matrices unitaires est peut-être qu’elle conserve la norme d’un vecteur.  Cela se produit car 

$ $ \langle v, v \rangle = v ^ \dagger v = v ^ \dagger U ^{-1} U v = v ^ \dagger U ^ \dagger U v = \langle U v, U v\rangle. $ $  

Une matrice $M $ est dite [*Hermitian*](https://en.wikipedia.org/wiki/Hermitian_matrix) si $M = M ^ \dagger $.

Enfin, le [*produit tenseur*](https://en.wikipedia.org/wiki/Tensor_product) (ou produit Kronecker) de deux matrices $M $ de Size $m \times n $ et $N $ de taille $p \times q $ est une matrice plus grande $P = M\otimes n $ de taille $MP \times NQ $ et est obtenue à partir de $M $ et de $N $ comme suit :

\begin{align} M \otimes N & = \begin{bmatrix} m{11} ~ ~ \cdots ~ ~ m {1N} \\\\ \ddots\\\\ m {M1} ~ ~ \cdots ~ ~ m {mn} \end{bmatrix} \otimes \begin{bmatrix} n_{11} ~ ~ \cdots ~ ~ n_ {1t}\\\\ \ddots @no__ t_8_ \\ n_ {P1} ~ ~ \cdots ~ ~ n_ {PQ} \end{bmatrix}\\\\ & = \begin{bmatrix} m{11} \begin{bmatrix} n_{11} ~ ~ \cdots ~ ~ n_ {1t}\\\\ \ddots\\\\ n_ {P1} ~ ~ \cdots ~ ~ n_ {PQ} \end{bmatrix} ~ ~ \cdots ~ ~ m {1N} \begin{bmatrix} n_{11} ~ ~ \cdots ~ ~ n_ {1t}\\\\ \ddots\\\\ n_ {P1} ~ ~ \cdots ~ ~ n_ {PQ} \end{bmatrix}\\\\ \ddots\\\\ m {M1} \begin{bmatrix} n_{11} ~ ~ \ cdots ~ ~ n_ {1t}\\\\ \ddots\\\\ n_ {P1} ~ ~ \cdots ~ ~ n_ {PQ} \end{bmatrix} ~ ~ \cdots ~ ~ m {mn} \begin{bmatrix} n_{11} ~ ~ \cdots ~ ~ n_ {1t}\\\\ \ddots\\\\ n_ {P1} ~ ~ \cdots ~ ~ n_ {PQ} \end {bmatrix} \end{bmatrix}.
\end{align}

Cette solution est mieux illustrée par des exemples :

$ $ \begin{bmatrix} a \\\\ b \end{bmatrix} \otimes \begin{bmatrix} c \\\\ d \\\\ e \end{bmatrix} = \begin{bmatrix} a \begin{bmatrix} c \\\\ d \\\\ e \end{bmatrix} @no__ t_10_ \\[1.5 em] b \begin{bmatrix} c \\\\ d \\\\ e\end {bmatrix} \end{bmatrix} = \begin{bmatrix} a \\c \\ a d \\\\ a e \\\\ b c \\\\ b d \\\\ be\end {bmatrix} $ $

et la

$ $ \begin{bmatrix} a \ b \\\\ c \ d \end{bmatrix} \otimes \begin{bmatrix} e \ f\\\\g \ h \end{bmatrix} = \begin{bmatrix} a\begin {bmatrix} e \ f\\\\ g \ h \end{bmatrix} b\begin {bmatrix} e \ f\\@no__ t_7_ g \ h \end{bmatrix} \\\\[1em] c\begin {bmatrix} e \ f\\\\ g \ h \end{bmatrix} d\begin {bmatrix} e \ f\\\\ g \ h \end{bmatrix} \end{bmatrix} = \begin{bmatrix} AE \ AF \ est \ BF \\@no__ t_15_ AG \ Ah \ BG \ BH \\\\ ce \ CF \ de \ DF \\\\ CG \ ch \ DG \ DH \end{bmatrix}.
$$

Une dernière convention de notation utile entourant les produits tenseur est que, pour n’importe quel vecteur $v $ ou Matrix $M $, $v ^ {\otimes n} $ ou $M ^ {\otimes n} $ est la main à la main pour un produit tenseur répété $n $ Fold.  Exemple :

\begin{align} & \begin{bmatrix} 1 \\\\ 0 \end{bmatrix} ^ {\otimes 1} = \begin{bmatrix} 1 \\\\ 0 \end{bmatrix}, \qquad\begin{bmatrix} 1 \\\\ 0 \end{bmatrix} ^ {\otimes 2} = \begin{bmatrix} 1 \\\\ 0 \\\\0 \\\\0 \end{bmatrix}, \qquad\begin{bmatrix} 1 \\\\-1 \end{bmatrix} ^ {\otimes 2} = \begin{bmatrix} 1 \\\\-1 \\\\-1 \\\\1 \end{bmatrix}, \\\\ & \begin{bmatrix} 0 & 1 \\\\ 1 & 0 \end{bmatrix} ^ {\otimes 1} = \begin{bmatrix} 0 & 1 \\\\ 1 & 0 \end{bmatrix}, \qquad\begin{bmatrix} 0 & 1 \\@no__ t_27_ 1 & 0 \end{bmatrix} ^ {\otimes 2} = \begin{bmatrix} 0 & 0 & 0 & 1 \\\\ 0 & 0 & 1 & 0 \\\\ 0 & 1 & 0 & 0\\\\ 1 & 0 & 0 & 0 \ end {bmatrix}.
\end{align}
