---
title: Circuits de quantum
description: Découvrez comment représenter visuellement des opérations quantiques simples et complexes avec des diagrammes de circuit quantique.
author: QuantumWriter
uid: microsoft.quantum.concepts.circuits
ms.author: nawiebe@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: 8ba4648f1837065d15957a01ab4ca8dd2d490a42
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/28/2020
ms.locfileid: "77905146"
---
# <a name="quantum-circuits"></a>Circuits quantiques
Prenons un moment pour la transformation unitaire $ \text{CNOTIN} _{01}(H\otimes 1) $.
Cette séquence de porte-clés revêt une importance fondamentale pour l’informatique quantique, car elle crée un État à deux qubit enchevêtré au maximum :

$ $ \mathrm{CNOT}_{01}(H\otimes 1) \ket{00} = \frac{1}{\sqrt{2}} \left (\ket{00} + \ket{11} \right), $ $

Les opérations ayant cette complexité ou une complexité accrue sont omniprésentes dans les algorithmes Quantum et la correction des erreurs Quantum. il doit donc s’avérer très utile de disposer d’une méthode simple pour la visualisation appelée *diagramme de circuit quantique*.
Le schéma de circuit pour la préparation de cet État Quantum enchevêtré de façon optimisée est le suivant :

<!--- ![](.\media\1.svg) --->
<!-- Can't find a way to easily center this... probably an extension needed:  -->
diagramme de circuit ![pour un État à deux qubit enchevêtré au maximum](~/media/Concepts1.png)

## <a name="quantum-circuit-diagram-conventions"></a>Conventions du diagramme de circuit quantique
Ce langage visuel pour les opérations de Quantum peut être plus facilement compréhensible que l’écriture de sa matrice équivalente une fois que vous comprenez les conventions d’expression d’un circuit quantique.
Nous allons passer en revue les conventions ci-dessous.

Dans un schéma de circuit, chaque ligne pleine représente un qubit ou plus généralement un registre qubit.
Par Convention, la ligne supérieure est qubit Register $0 $ et le reste sont étiquetés de manière séquentielle. Le circuit d’exemple ci-dessus est représenté comme agissant sur deux qubits (ou deux registres équivalents composés d’un qubit).
Les portes agissant sur un ou plusieurs registres qubit sont dénotées sous forme de zone.
Par exemple, le symbole

<!--- ![](.\media\2.svg) --->
<!-- Can't find a way to easily center this... probably an extension needed:  -->
![symbole pour une opération Hadarmard agissant sur un registre à qubit unique](~/media/concepts_2.png)

est une opération [hadarmard](xref:microsoft.quantum.intrinsic.h) agissant sur un registre à qubit unique.

Les portes de Quantum sont triées dans l’ordre chronologique avec la porte la plus à gauche à mesure que la porte est appliquée en premier au qubits.
En d’autres termes, si vous constatez que les câbles sont dépendants de l’État Quantum, les fils importent l’État Quantum par le biais de chacune des portes du diagramme, de gauche à droite.
Autrement dit, 

<!--- ![](.\media\3.svg) --->
<!-- Can't find a way to easily center this... probably an extension needed:  -->
![diagramme des portes de Quantum appliquées de gauche à droite](~/media/concepts_3.png)

est la matrice d’unités $CBA $.
La multiplication de matrice obéit à la Convention opposée : la matrice la plus à droite est appliquée en premier. Toutefois, dans les diagrammes de circuit Quantum, la porte la plus à gauche est appliquée en premier.
Cette différence peut parfois entraîner une confusion. il est donc important de noter cette différence importante entre la notation algébrique linéaire et les diagrammes de circuit quantique.

## <a name="inputs-and-outputs-of-quantum-circuits"></a>Entrées et sorties de circuits quantiques
Tous les exemples précédents donnés ont eu exactement le même nombre de fils (qubits) d’entrée à une porte quantique que le nombre de fils de la porte quantique.
Il peut sembler raisonnable que les circuits quantiques aient plus ou moins de sorties que d’entrées en général.
Toutefois, ce n’est pas possible car toutes les opérations de Quantum, les mesures Save, sont des unités et, par conséquent, réversibles.
S’ils n’ont pas le même nombre de sorties que les entrées, elles ne sont pas réversibles et, par conséquent, ne sont pas d’une contradiction.
Pour cette raison, toute zone dessinée dans un diagramme de circuit doit avoir exactement le même nombre de câbles qui l’entrent comme étant en cours de sortie.

Les diagrammes de circuit à plusieurs qubit suivent des conventions similaires pour les qubit.
En guise d’exemple de clarification, nous pouvons définir une opération unitaire à deux qubit $B $ pour être $ (H S\otimes X) $ et exprimer le circuit de façon équivalente

<!--- ![](.\media\4.svg) --->
<!-- Can't find a way to easily center this... probably an extension needed:  -->
diagramme de circuit ![d’une opération unitaire à deux qubit](~/media/concepts_4.png)

Nous pouvons également afficher $B $ comme ayant une action sur un seul registre à deux qubit au lieu de registres 2 1-qubit en fonction du contexte dans lequel le circuit est utilisé. La propriété la plus utile de tels diagrammes de circuits abstraits est peut-être qu’ils permettent de décrire des algorithmes Quantum compliqués à un niveau élevé sans avoir à les compiler en portes fondamentales.
Cela signifie que vous pouvez obtenir une intuition sur le workflow pour un grand algorithme Quantum sans avoir besoin de comprendre tous les détails sur le fonctionnement de chacune des sous-routines de l’algorithme.

## <a name="controlled-gates"></a>Portes contrôlées
L’autre construction intégrée aux diagrammes Quantum à plusieurs qubit est le contrôle.
L’action d’une porte à contrôle quantique, dénotée $ \Lambda (G) $, où une valeur de qubit unique contrôle l’application de $G $, peut être comprise en examinant l’exemple suivant d’une entrée d’état de produit $ \Lambda (G) (\alpha \ket{0} + \beta \ket{1}) \ket{\Psi} = \alpha \ket{0} \ket{\Psi} + \beta \ket{1} G\ket {\ psi}
Autrement dit, la porte contrôlée applique $G $ au registre contenant $ \Psi $ si et seulement si le contrôle qubit prend la valeur $1 $.
En général, nous décrivons ces opérations contrôlées dans des diagrammes de circuit comme

<!--- ![](.\media\5.svg) --->
<!-- Can't find a way to easily center this... probably an extension needed:  -->
diagramme de circuit ![d’une porte contrôlée de façon unique](~/media/concepts_5.png)

Ici, le cercle noir désigne le bit Quantum sur lequel la porte est contrôlée et un câble vertical dénote l’unité qui est appliquée lorsque le contrôle qubit prend la valeur $1 $.
Dans les cas spéciaux où $G = X $ et $G = Z $ nous introduisons la notation suivante pour décrire la version contrôlée des portes (Notez que la porte contrôlée-X est la [$CNOT $ Gate](xref:microsoft.quantum.intrinsic.cnot)) :

<!--- ![](.\media\6.svg) --->
<!-- Can't find a way to easily center this... probably an extension needed:  -->
diagramme de circuit ![pour les cas spéciaux de portes contrôlées](~/media/concepts_6.png)

Q # fournit des méthodes pour générer automatiquement la version contrôlée d’une opération, ce qui évite au programmeur d’avoir à coder manuellement ces opérations. Un exemple est illustré ci-dessous :

```qsharp
operation PrepareSuperposition(qubit : Qubit) : Unit
is Ctl { // Auto-generate the controlled specialization of the operation
    H(qubit);
}
```

## <a name="measurement-operator"></a>Opérateur de mesure
L’opération restante à visualiser dans les diagrammes de circuit est la mesure.
La mesure prend un registre qubit, le mesure et renvoie le résultat sous forme d’informations classiques.
Une opération de mesure est indiquée par un symbole de compteur et prend toujours comme entrée un registre qubit (indiqué par une ligne pleine) et renvoie des informations classiques (dénotées par une ligne double).
Plus précisément, un sous-circuit similaire à ce qui suit :

<!--- ![](.\media\7.svg) ---->
<!-- Can't find a way to easily center this... probably an extension needed:  -->
![symbole représentant une opération de mesure](~/media/concepts_7.png)

Q # implémente un [opérateur de mesure](xref:microsoft.quantum.intrinsic.measure) à cet effet.
Pour plus d’informations, consultez la [section sur les mesures](xref:microsoft.quantum.libraries.standard.prelude#measurements) .

De même, le sous-circuit

<!--- ![](.\media\8.svg) --->
<!-- Can't find a way to easily center this... probably an extension needed:  -->
diagramme de circuit ![représentant une opération contrôlée](~/media/concepts_8.png)

donne une porte contrôlée de façon classique, où $G $ est appliqué sur le bit de contrôle classique qui est la valeur $1 $.

## <a name="teleportation-circuit-diagram"></a>Diagramme de circuit de téléportisation
La [téléportage quantique](xref:microsoft.quantum.techniques.puttingittogether) est peut-être le meilleur algorithme Quantum pour illustrer ces composants.
La téléportage quantique est une méthode permettant de déplacer des données au sein d’un ordinateur quantique (ou même entre des ordinateurs quantiques distants dans un réseau quantique) à l’aide d’un enchevêtrement et d’une mesure.
Il est intéressant de pouvoir déplacer un État Quantum, disons la valeur d’un qubit donné, d’un qubit à un autre, sans même connaître la valeur de qubit !
Cela est nécessaire pour que le protocole fonctionne conformément aux lois de la mécanique des quantums.
Le circuit de téléportage Quantum est indiqué ci-dessous ; Nous fournissons également une version annotée du circuit pour illustrer comment lire le circuit Quantum.

<!--- ![](.\media\tp2.svg){ width=50% } --->
circuit ![Quantum teleportage](~/media/concepts_tp2.png)
