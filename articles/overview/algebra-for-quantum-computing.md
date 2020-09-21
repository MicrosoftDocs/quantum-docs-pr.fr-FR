---
title: Algèbre linéaire pour l’informatique quantique
description: Découvrez les concepts fondamentaux de l’algèbre linéaire à connaître pour comprendre l’informatique quantique
author: bradben
ms.author: bradben
ms.date: 5/5/2020
ms.topic: overview
uid: microsoft.quantum.overview.algebra
no-loc:
- Q#
- $$v
ms.openlocfilehash: d7a8dff8d491a9ce6451148d2d27121f1c190ed0
ms.sourcegitcommit: 8256ff463eb9319f1933820a36c0838cf1e024e8
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/17/2020
ms.locfileid: "90759320"
---
# <a name="linear-algebra-for-quantum-computing"></a>Algèbre linéaire pour l’informatique quantique

L’algèbre linéaire est le langage de l’informatique quantique. Vous n’avez pas besoin de connaître les détails de son fonctionnement pour implémenter ou écrire des programmes quantiques, mais sachez qu’il est largement utilisé pour représenter les états des qubits et les opérations quantiques, et pour prédire le comportement d’un ordinateur quantique en réponse à une séquence d’instructions.

Tout comme avoir une certaine connaissance des [concepts fondamentaux de la physique quantique](xref:microsoft.quantum.overview.understanding) peut vous aider à comprendre l’informatique quantique, avoir quelques notions de base sur l’algèbre linéaire est utile pour mieux comprendre le fonctionnement des algorithmes quantiques. Vous devez au moins être familiarisé avec les **vecteurs** et la **multiplication des matrices**. Si vous souhaitez rafraîchir vos connaissances de ces concepts algébriques, consultez ces tutoriels qui expliquent les principes de base :

- [Tutoriel de notebook Jupyter sur l’algèbre linéaire](https://github.com/microsoft/QuantumKatas/tree/main/tutorials/LinearAlgebra)
- [Tutoriel de notebook Jupyter sur l’arithmétique complexe](https://github.com/microsoft/QuantumKatas/tree/main/tutorials/ComplexArithmetic)
- [Algèbre linéaire pour le calcul quantique](https://cds.cern.ch/record/1522001/files/978-1-4614-6336-8_BookBackMatter.pdf)
- [Principes de base de l’algèbre linéaire](https://www.math.ubc.ca/~carrell/NB.pdf)
- [Initiation au calcul quantique](https://www.codeproject.com/Articles/5155638/Quantum-Computation-Primer-Part-1#exploring-quantum-superposition)

## <a name="vectors-and-matrices-in-quantum-computing"></a>Vecteurs et matrices dans l’informatique quantique

Dans la rubrique [Comprendre l’informatique quantique](xref:microsoft.quantum.overview.understanding), vous avez appris qu’un qubit peut être dans un état 1, un état 0 ou une superposition ou les deux. En algèbre linéaire, l’état d’un qubit est décrit par un vecteur et est représenté par une **matrice** à une colonne $\begin{bmatrix} a \\\\  b \end{bmatrix}$. Il est également connu sous le nom de **vecteur d’état quantique** et doit remplir cette condition : $|a|^2 + |b|^2 = 1$.  

Les éléments de la matrice représentent la probabilité que le qubit soit réduit dans un sens ou l’autre, $|a|^2$ étant la probabilité de réduction à zéro, et $|b|^2$ étant la probabilité de réduction à un. Les matrices suivantes représentent toutes des vecteurs d’état quantique valides :

$$\begin{bmatrix} 1 \\\\  0 \end{bmatrix}, \begin{bmatrix} 0 \\\\  1 \end{bmatrix}, \begin{bmatrix} \frac{1}{\sqrt{2}} \\\\  \frac{1}{\sqrt{2}} \end{bmatrix}, \begin{bmatrix} \frac{1}{\sqrt{2}} \\\\  \frac{-1}{\sqrt{2}} \end{bmatrix}\text{ et }\begin{bmatrix} \frac{1}{\sqrt{2}} \\\\  \frac{i}{\sqrt{2}} \end{bmatrix}.$$

Dans la rubrique [Ordinateurs quantiques et simulateurs quantiques](xref:microsoft.quantum.overview.simulators), vous avez appris que les opérations quantiques sont utilisées pour changer l’état d’un qubit.  Les opérations quantiques peuvent également être représentées par une matrice. Quand une opération quantique est appliquée à un qubit, les deux matrices qui les représentent sont multipliées, et le résultat donné en réponse représente le nouvel état du qubit après l’opération.  

Voici deux opérations quantiques courantes représentées par la multiplication des matrices.


L’[opération `X`](xref:microsoft.quantum.intrinsic.x) est représentée par la matrice de Pauli $X$,

$$X = \begin{bmatrix} 0 & 1 \\\\ 1 & 0 \end{bmatrix},$$
    
et est utilisée pour inverser l’état d’un qubit de 0 à 1 (ou vice versa), par exemple

$$\begin{bmatrix}0 &1\\\\ 1 &0\end{bmatrix}\begin{bmatrix} 1 \\\\  0 \end{bmatrix} = \begin{bmatrix} 0 \\\\  1 \end{bmatrix}.$$

L’[opération « H »](xref:microsoft.quantum.intrinsic.h) est représentée par la transformation d’Hadamard $H$,

$$H = \dfrac{1}{\sqrt{2}}\begin{bmatrix}1 &1\\\\ 1 &-1\end{bmatrix},$$

 et met un qubit dans un état de superposition où il a une probabilité égale d’être réduit dans un sens ou l’autre, comme illustré ici

$$\frac{1}{\sqrt{2}}\begin{bmatrix}1 &1\\\\ 1 &-1\end{bmatrix}\begin{bmatrix} 1 \\\\  0 \end{bmatrix}=\frac{1}{\sqrt{2}}\begin{bmatrix} 1 \\\\  1 \end{bmatrix}=\left(\frac{1}{\sqrt{2}}\right)^2=\frac{1}{2}.$$

Une matrice qui représente une opération quantique a une exigence : elle doit être une matrice **unitaire**. Une matrice est unitaire si l’**inverse** de la matrice est égal à la matrice **transposée conjuguée**.

## <a name="representing-two-qubit-states"></a>Représentation des états de deux qubits

Dans les exemples ci-dessus, l’état d’un qubit était représenté par une matrice à une colonne $\begin{bmatrix} a \\\\  b \end{bmatrix}$, et l’application d’une opération au qubit était représentée par la multiplication des deux matrices. Toutefois, comme les ordinateurs quantiques utilisent plusieurs qubits, comment pouvez-vous représenter l’état combiné de deux qubits ? 

N’oubliez pas que chaque qubit est un espace vectoriel, et qu’il n’est donc pas possible d’effectuer une simple multiplication. À la place, vous utilisez un **produit tensoriel**. Il s’agit d’une opération associée qui crée un autre espace vectoriel à partir de plusieurs espaces vectoriels individuels et qui est représentée par le symbole $\otimes$. Par exemple, le produit tensoriel des deux états de qubits $\begin{bmatrix} a \\\\  b \end{bmatrix}$ et $\begin{bmatrix} c \\\\  d \end{bmatrix}$ se calcule ainsi :

$$ \begin{bmatrix} a \\\\  b \end{bmatrix} \otimes \begin{bmatrix} c \\\\  d \end{bmatrix} =\begin{bmatrix} a \begin{bmatrix} c \\\\  d \end{bmatrix} \\\\ b \begin{bmatrix}c \\\\  d \end{bmatrix} \end{bmatrix} = \begin{bmatrix} ac \\\\  ad \\\\  bc \\\\  bd \end{bmatrix}. $$

Le résultat est une matrice à quatre dimensions, où chaque élément représente une probabilité. Par exemple, $ac$ représente la probabilité que les deux qubits soient réduits à 0 et 0, $ad$ est la probabilité qu’ils soient réduits à 0 et 1, et ainsi de suite. 

De la même façon que l’état d’un seul qubit $\begin{bmatrix} a \\\\  b \end{bmatrix}$ doit satisfaire à l’exigence $|a|^2 + |b|^2 = 1$ afin de représenter un état quantique, l’état de deux qubits $\begin{bmatrix} ac \\\\  ad \\\\  bc \\\\  bd \end{bmatrix}$ doit satisfaire à l’exigence $|ac|^2 + |ad|^2 + |bc|^2+ |bd|^2 = 1$.

## <a name="summary"></a>Résumé

L’algèbre linéaire est le langage standard utilisé pour les représentations dans l’informatique quantique et la physique quantique. Les [bibliothèques](xref:microsoft.quantum.libraries) fournies avec le kit de développement Microsoft Quantum vous aideront à exécuter des algorithmes quantiques complexes sans avoir à vous plonger dans les dessous mathématiques. Connaître les concepts fondamentaux reste cependant utile pour démarrer plus rapidement et continuer sur des bases solides.

## <a name="next-steps"></a>Étapes suivantes

[Installer le QDK](xref:microsoft.quantum.install)
