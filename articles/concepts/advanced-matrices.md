---
title: Concepts avancés de la matrice | Microsoft Docs
description: Concepts avancés de la matrice
author: QuantumWriter
uid: microsoft.quantum.concepts.matrix-advanced
ms.author: nawiebe@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: f87b3bcd19d2f98fea2a9724a280781a78c4cbb9
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/26/2019
ms.locfileid: "73183758"
---
# <a name="advanced-matrix-concepts"></a>Concepts avancés de la matrice #

Nous étendons maintenant notre manipulation de matrices à [*valeurs propres, vecteurs propres*](https://en.wikipedia.org/wiki/Eigenvalues_and_eigenvectors) et [*exponentiels*](https://en.wikipedia.org/wiki/Matrix_exponential) , qui constituent un ensemble fondamental d’outils dont nous avons besoin pour décrire et implémenter des algorithmes Quantum.

## <a name="eigenvalues-and-eigenvectors"></a>Valeurs propres et vecteurs propres ##

Laissez $M $ être une matrice carrée et $v $ est un vecteur qui n’est pas le vecteur de zéros tous (c’est-à-dire le vecteur avec toutes les entrées égales à $0 $).

Nous disons $v $ est un [*extraction*](https://en.wikipedia.org/wiki/Eigenvalues_and_eigenvectors) de $M $ if $mV = CV $ pour un nombre $c $. Nous disons $c $ est le [*eigenvalue*](https://en.wikipedia.org/wiki/Eigenvalues_and_eigenvectors) correspondant au extraction $v $. En général, une matrice $M $ peut transformer un vecteur en un autre vecteur, mais un extraction est spécial, car il reste inchangé, sauf s’il est multiplié par un nombre. Notez que si $v $ est un extraction avec eigenvalue $c $, $av $ est également un extraction (pour toute valeur différente de zéro $a $) avec le même eigenvalue.

Par exemple, pour la matrice d’identité, chaque vecteur $v $ est un extraction avec eigenvalue $1 $.

En guise d’autre exemple, considérez une [*matrice diagonale*](https://en.wikipedia.org/wiki/Diagonal_matrix) $D $ qui n’a que des entrées autres que zéro sur la diagonale :

$ $ \begin{bmatrix} d_1 & 0 & 0 \\\\ 0 & d_2 & 0 \\\\ 0 & 0 & D_3 \end{bmatrix}.
$$

Les vecteurs

$ $ \begin{bmatrix}1 \\\\ 0 \\\\ 0 \end{bmatrix}, \begin{bmatrix}0 \\\\ 1 \\\\ 0 \ end {bmatrix} et \begin{bmatrix}0 \\\\ 0 \\\\ 1 \ fin {bmatrix} $ $

vecteurs propres de cette matrice avec valeurs propres $d _ 1, $d _2 $ et $d _3 $, respectivement. Si $d _ 1 $, $d _2 $ et $d _3 $ sont des nombres distincts, ces vecteurs (et leurs multiples) sont les seuls vecteurs propres de la matrice $D $. En général, pour une matrice diagonale, il est facile de lire les valeurs propres et les vecteurs propres. Les valeurs propres sont tous des nombres apparaissant sur la diagonale, et leurs vecteurs propres respectifs sont les vecteurs d’unité avec une entrée égale à $1 $ et les entrées restantes égales à $0 $.

Notez dans l’exemple ci-dessus que le vecteurs propres de $D $ forment une base pour les vecteurs $3 $ dimensionnels. Une base est un ensemble de vecteurs, de sorte que tout vecteur peut être écrit comme une combinaison linéaire de ces vecteurs. Plus explicitement, $v _ 1 $, $v _2 $ et $v _3 $ forment une base si un vecteur $v $ peut être écrit comme $v = A_1 V_1 + a_2 V_2 + A_3 V_3 $ pour certains nombres $a _ 1 _ 1, $a _2 $ et $a _3 $.

Rappelez-vous qu’une matrice Hermitian (également appelée autojoint) est une matrice carrée complexe égale à son propre conjugué complexe, tandis qu’une matrice d’unités est une matrice carrée complexe dont l’inverse est égal à son conjugué complexe.
Pour les matrices Hermitian et Unity, qui sont essentiellement les seules matrices rencontrées dans Quantum Computing, il existe un résultat général appelé le [*spectral*](https://en.wikipedia.org/wiki/Spectral_theorem), qui déclare les éléments suivants : pour n’importe quelle matrice Hermitian ou unitaire $M $, il existe un unité de $U $ telle que $M = U ^ \dagger D U $ pour une matrice diagonale $D $. En outre, les entrées diagonales de $D $ seront le valeurs propres de $M $.

Nous savons déjà comment calculer le valeurs propres et le vecteurs propres d’une matrice diagonale $D $. À l’aide de cette aide, nous savons que si $v $ est un extraction de $D $ avec eigenvalue $c $, par exemple $Dv = CV $, $U ^ \dagger v $ sera un extraction de $M $ avec eigenvalue $c $. Cela est dû au fait que

$ $M (U ^ \dagger v) = U ^ \dagger D U (U ^ \dagger v) = U ^ \dagger D (U U ^ \dagger) v = U ^ \dagger D v = c U ^ \dagger v. $ $

## <a name="matrix-exponentials"></a>Exponentiels de la matrice
Une [*matrice exponentielle*](https://en.wikipedia.org/wiki/Matrix_exponential) peut également être définie en analogie exacte avec la fonction exponentielle.  La matrice exponentielle d’une matrice $A $ peut être exprimée sous la forme

$ $ e ^ A = \boldone + A + \frac{A ^ 2} {2 !} + \frac{A ^ 3} {3 !} + \cdots $ $

Cela est important, car l’évolution du temps de Quantum mécanique est décrite par une matrice d’unités au format $e ^ {iB} $ pour la matrice Hermitian $B $.  C’est la raison pour laquelle l’exécution de la matrice exponentielles est une partie fondamentale de l’informatique Quantum et, comme Q #, elle offre des routines intrinsèques pour décrire ces opérations.
Il existe de nombreuses façons de calculer un exponentiel de matrice sur un ordinateur classique, et en général, une approximation approximative d’un tel exponentiel est chargée avec les risques.  Consultez [*Cleve mole et Charles Van Loan. « Dix-neuf façons douteuse de calculer l’exponentiel d’une matrice. » SIAM révision 20,4 (1978) : 801-836*](https://doi.org/10.1137/S00361445024180) pour plus d’informations sur les défis impliqués.

Le moyen le plus simple de comprendre comment calculer l’exponentiel d’une matrice consiste à utiliser les valeurs propres et les vecteurs propres de cette matrice.  Plus précisément, le point de vue spectral évoqué ci-dessus indique que pour chaque Hermitian ou matrice d’unités $A $ il existe une matrice d’unités $U $ et une matrice diagonale $D $ telle que $A = U ^ \dagger D.  En raison des propriétés de unitarity, nous avons $A ^ 2 = U ^ \dagger D ^ 2 U $ et de la même façon pour toute alimentation $p $ $A ^ p = U ^ \dagger D ^ p U $.  Si nous le remplaçons par la définition d’opérateur de l’opérateur exponentiel, nous obtenons :

$ $ e ^ A = U ^ \dagger \left (\boldone + D + \frac{D ^ 2} {2 !} + \cdots \right) U = U ^ \dagger \begin{bmatrix}\exp (d_{11}) & 0 & \cdots & 0\\\\ 0 & \exp (d_{22}) & \cdots & 0\\\\ \vdots & \vdots & \ddots & \vdots\\\\ 0 & 0 & \cdots & \exp (d_ {NN}) \end{bmatrix} U. $ $

En d’autres termes, si vous transformez en eigenbasis de la matrice $A $, le calcul de la valeur exponentielle de la matrice est équivalent au calcul de la valeur exponentielle ordinaire du valeurs propres de la matrice.  Dans la mesure où de nombreuses opérations dans quantum computing impliquent l’exécution de la matrice exponentielles, cette astuce de transformation en eigenbasis d’une matrice pour simplifier l’exécution de l’opérateur exponentiel s’affiche fréquemment et constitue la base de nombreux algorithmes Quantum tels que Trotter – méthodes de simulation de quantum de style Suzuki présentées plus loin dans ce guide.

Une autre propriété utile est si $B $ est à la fois unitéal et Hermitian, c’est-à-dire $B = B ^{-1}= B ^ \dagger $, puis $B ^ 2 = \boldone $. En appliquant cette règle à l’expansion ci-dessus de la matrice exponentielle et en regroupant les termes $ \boldone $ et $B $, vous pouvez constater que pour n’importe quelle valeur réelle $x l’identité

$ $e ^ {iBx} = \boldone \cos (x) + iB\sin (x) $ $


comprend. Cette astuce est particulièrement utile, car elle permet de tenir compte des actions exponentielles de la matrice, même si la dimension de $B $ est exponentiellement grande, pour le cas particulier lorsque $B $ est à la fois unitaire et Hermitian.
