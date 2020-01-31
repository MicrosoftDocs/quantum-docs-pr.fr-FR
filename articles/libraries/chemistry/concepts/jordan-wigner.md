---
title: Jordanie-représentation Wigner | Microsoft Docs
description: Documents conceptuels de la représentation Jordanie-Wigner
author: nathanwiebe2
ms.author: nawiebe@microsoft.com
ms.date: 10/09/2017
ms.topic: article-type-from-white-list
uid: microsoft.quantum.chemistry.concepts.jordanwigner
ms.openlocfilehash: 5d9038e440a2022547395e889e149a531a7ef818
ms.sourcegitcommit: f8d6d32d16c3e758046337fb4b16a8c42fb04c39
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/29/2020
ms.locfileid: "76820536"
---
# <a name="jordan-wigner-representation"></a>Jordanie-représentation Wigner

Tandis que les deuxième Hamiltonians quantifiés sont facilement représentées en termes de $a ^ \dagger $ (création) et $a $ (annihilation), ces opérations ne sont pas des opérations fondamentales sur les ordinateurs quantiques.
Par conséquent, si nous souhaitons qu’il les implémente sur un ordinateur quantique, nous devons mapper les opérateurs aux matrices unitaires qui peuvent être implémentées sur un ordinateur quantique.
La représentation Jordanie – Wigner fournit une telle carte.
Toutefois, d’autres, telles que la représentation Bravyi – kitaev, existent également et présentent leurs propres avantages et inconvénients.
Le principal avantage de la représentation Jordanie-Wigner est sa simplicité.

La représentation Jordanie-Wigner est simple à dériver.
Rappelez-vous qu’un État $ \ket{0}_j $ signifie que spin orbital $j $ est vide et $ \ket{1}_j $ signifie qu’il est occupé.
Cela signifie que qubits peut naturellement stocker l’occupation d’un spin orbital donné.
Nous avons ensuite cette $a ^ \ dagger_j \ket{0}_j = \ket{1}_j $ et $a ^ \ dagger_j \ket{1}_J = $0.
Il est facile de vérifier que \begin{align} a ^ \ dagger_j & = \begin{bmatrix}0 & 0 \\\ 1 & 0 \end{bmatrix} = \frac{X_j-iY_j}{2}, \nonumber\\\\ a_j & = \begin{bmatrix}0 & 1 \\\ 0 & 0 \end{bmatrix} = \frac{X_j + iY_j}{2}, \end{align} où $X _J $ et $Y $ sont les opérateurs Pauli-_j $ et-$X $ agissant sur qubit $Y $.

>[!NOTE]
> Dans Q #, $ \ket{0}$ State représente le + 1 eigenstate de l’opérateur $Z $. Dans certaines zones de physique $ \ket{0}$ représente l’état de la terre faible-énergie et donc la-1 eigenstate de l’opérateur $Z $. Par conséquent, certaines formules peuvent différer de la documentation populaire.

Dans la bibliothèque chimie, nous utilisons $ \ket{0}$ pour représenter un spin-orbital inoccupé.
Cela montre que pour un seul spin orbital, il est facile de représenter des opérateurs de création et de annihilation en termes de matrices unitaires que les ordinateurs quantiques comprennent.
Notez que si $X $ et $Y $ sont des $a unitaires ^ \dagger $ et $a $ ne le sont pas.
Nous verrons plus tard que cela ne pose pas de problème pour la simulation.

L’un des problèmes restants, c’est que même si la construction ci-dessus fonctionne pour un seul spin orbital, elle échoue pour les systèmes avec deux orbites ou plus.
Étant donné que fermions est antisymmetic, nous savons que $a ^ \ dagger_j un ^ \ dagger_k =-a ^ \ dagger_k a ^ \ dagger_j $ pour tout $j $ et $k $.
Toutefois, $ $ \left (\frac{X_j-iY_j}{2}\right) \left (\frac{X_k-iY_k}{2}\right) = \left (\frac{X_k-iY_k}{2}\right) \left (\frac{X_j-iY_j}{2}\right).
$ $ En d’autres termes, les deux opérateurs de création ne sont pas anti-muets si nécessaire.
Cela peut être résolu de manière simple, si ce n’est pas élégant.
Le correctif est de noter que les opérateurs Pauli sont naturellement anti-muet.
En particulier, $XZ =-ZX $ et $YZ =-ZY $.
Par conséquent, par interspersing $Z $ Operators dans la construction de l’opérateur, nous pouvons émuler l’anti-mutation correcte.
La construction complète est la suivante : 

\begin{align} a ^ \ dagger_1 & = \left (\frac{X-iY}{2}\right) \otimes 1 \otimes 1 \otimes 1 \otimes \cdots \otimes 1,\\\\ un ^ \ dagger_2 & = Z\otimes\left (\frac{X-iY}{2}\right) \otimes 1 \ otimes 1 \otimes \cdots \otimes 1,\\\\ a ^ \ dagger_3 & = Z\otimes Z\otimes \left (\frac{X-iY}{2}\right) \otimes 1 \otimes \cdots \otimes 1,\\\\ & \vdots\\\\ a ^ \ dagger_N & = Z\otimes Z\otimes Z\otimes Z \otimes \cdots \otimes Z \ otimes \left (\frac{X-iY}{2}\right). \label{EQ : JW} \end{align}

Il est également pratique d’exprimer les opérateurs numériques, $n _j $, en termes d’opérateurs Pauli.
Heureusement, les chaînes de $Z $ Operators (appelées chaînes Jordanie-Wigner) annulent à l’issue de cette substitution.
Après avoir effectué cette sortie (et rappelant que $X _jY_j = iZ_j $), nous avons \begin{Equation} n_j = a ^ \ dagger_j a_j = \frac{(1-Z_j)}{2}.
\end{equation}


## <a name="constructing-hamiltonians-in-jordan-wigner-representation"></a>Construction de Hamiltonians dans la représentation Jordanie-Wigner

Une fois que nous avons appelé la représentation Jordanie-Wigner qui traduit le Hamilton en une somme d’opérateurs Pauli est simple.
Il suffit de remplacer chacun des opérateurs $a ^ \dagger $ et $a $ dans le Fermionic Hamilton par les chaînes des opérateurs Pauli ci-dessus.
Lorsqu’une de ces substitutions est effectuée, il n’y a que cinq classes de termes au sein de la partie Hamilton.
Ces cinq classes correspondent aux différentes façons dont nous pouvons choisir les $p, q $ et $p, q, r, s $ dans le corps et les deux termes dans le même corps.
Ces cinq classes, pour le cas où $p > q > r > s $ et des orbites à valeur réelle, sont

\begin{align} h_ {pp} a_p ^ \dagger a_p & = \ sum_p \frac{h_ {pp}}{2}(1-Z_p)\\\\ {PQ} (h_ ^ \dagger a_p + a ^ \ a_q dagger_q) a_p = \frac{& {PQ}} h_ \left (\{2}{j = q + 1} ^ {p-1} Z_j \right) \left (X_pX_q + Y_pY_q \right)\\\\ h_ {pqqp} n_p n_q & = \frac{h_ {pqqp}}{4}\left (1-Z_p-Z_q + Z_pZ_q \right)\\\\ H_ {pqqr} & = \frac{h_ {pqqr}}{2}\left (\ prod_ {j = r + 1} ^ {p-1} Z_j \right) \left (X_pX_r + Y_pY_r \right) \left (\frac{1-Z_q}{2}\right)\\\\ H_ {PQRS} & = \frac{h_ {PQRS}}{8}\ prod_ {j = s + 1} ^ {r-1} Z_j \ prod_ {k = q + 1} ^ {p-1} Z_k \big (XXXX-XXYY + XYXY\nonumber\\\\ & \qquad\qquad\qquad\qquad\qquad + YXXY + YXYX-YYXX\nonumber\\\\ & \qquad\qquad\qquad\qquad\qquad + XYYX + YYYY\Big) \end{align}

Bien que la génération de tels Hamiltonians uniquement nécessite l’application de ces règles de remplacement, cela serait irréalisable pour les molécules de grande taille qui peuvent se composer de millions de termes de la Hamilton.
En guise d’alternative, nous pouvons construire automatiquement le `JordanWignerEncoding` en fonction d’une représentation `FermionHamiltonian`e du lieu de la même-Hamilton.

```csharp
    // We load the namespace containing fermion and Pauli objects. 
    using Microsoft.Quantum.Chemistry.Fermion;
    using Microsoft.Quantum.Chemistry.Pauli;
    
    // We create an example `FermionHamiltonian` instance.
    var fermionHamiltonian = new FermionHamiltonian();

    // We convert this Fermion Hamiltonian to a Jordan-Wigner representation.
    var jordanWignerEncoding = fermionHamiltonian.ToPauliHamiltonian(QubitEncoding.JordanWigner);
```

Une fois les Hamiltonians construits sous cette forme, nous pouvons utiliser un hôte d’algorithmes de simulation quantique pour compiler la dynamique générée par $e ^ {-iHt} $ dans une séquence de portes élémentaires (dans une certaine tolérance d’erreur définissable par l’utilisateur).
Nous aborderons les deux méthodes les plus populaires pour les formules de simulation quantique, qubitization et Trotter – Suzuki, dans la documentation algorithmique. Nous fournissons des implémentations pour les deux méthodes dans la bibliothèque de simulations de la Hamilton.
