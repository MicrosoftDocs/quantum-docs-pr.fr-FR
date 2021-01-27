---
uid: Microsoft.Quantum.Canon.ApplyAnd
title: Opération ApplyAnd
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyAnd
qsharp.summary: Inverts a given target qubit if and only if both control qubits are in the 1 state, using measurement to perform the adjoint operation.
ms.openlocfilehash: 39ffb9c598b6345c0d63c0c0d9705d84e101cc47
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845190"
---
# <a name="applyand-operation"></a>Opération ApplyAnd

Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Inverse un qubit cible donné si et seulement si les deux contrôles qubits sont dans l’État 1, à l’aide de mesures pour exécuter l’opération joint.

```qsharp
operation ApplyAnd (control1 : Qubit, control2 : Qubit, target : Qubit) : Unit is Adj + Ctl
```


## <a name="description"></a>Description

Inverse `target` si et seulement si les deux contrôles ont la valeur 1, mais suppose que `target` est dans l’État 0.  L’opération a T-Count 4, T-Depth 2 et ne nécessite aucune qubit d’assistance et peut donc être préférable à une opération CCNOT, si `target` est connu pour être 0.  Le voisin de cette opération est basé sur des mesures et ne nécessite pas de grille T.

L’application contrôlée de cette opération ne nécessite pas de qubit d’assistance, de `2^c` `Rz` portails et n’est pas optimisée pour plus de précision, où `c` est le nombre de qubits de contrôle globaux, y compris les deux contrôles de l' `ApplyAnd` opération.  L’application contrôlée par l’application voisine requiert des `2^c - 1` `Rz` portes (avec un angle deux fois la taille de l’opération non voisine), aucune qubit d’assistance et n’est pas optimisée pour plus de profondeur.

## <a name="input"></a>Entrée

### <a name="control1--qubit"></a>Control1 : [qubit](xref:microsoft.quantum.lang-ref.qubit)

Premier contrôle qubit


### <a name="control2--qubit"></a>Control2 : [qubit](xref:microsoft.quantum.lang-ref.qubit)

Deuxième qubit de contrôle


### <a name="target--qubit"></a>cible : [qubit](xref:microsoft.quantum.lang-ref.qubit)

Qubit auxiliaire cible ; doit être dans l’État 0



## <a name="output--unit"></a>Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)



## <a name="references"></a>Références

- Cody Jones : « nouvelles constructions pour la porte Toffoli à tolérance de pannes », phys. Rev. A 87, 022328, 2013 [arXiv : 1212.5069](https://arxiv.org/abs/1212.5069) doi : 10.1103/PhysRevA. 87.022328
- Craig Gidney : « diviser le coût de l’ajout quantique », Quantum 2, page 74, 2018 [arXiv : 1709.06648](https://arxiv.org/abs/1709.06648) doi : 10.1103/PhysRevA. 85.044302
- Mathias Soeken : « circuits Oracle Quantum et modèle d’arborescence de Noël », [article de blog du 19 décembre 2019](https://msoeken.github.io/blog_qac.html) (Remarque : explique la construction à plusieurs contrôleurs)