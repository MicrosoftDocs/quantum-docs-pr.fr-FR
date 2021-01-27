---
uid: Microsoft.Quantum.Canon.ApplyLowDepthAnd
title: Opération ApplyLowDepthAnd
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyLowDepthAnd
qsharp.summary: Inverts a given target qubit if and only if both control qubits are in the 1 state, with T-depth 1, using measurement to perform the adjoint operation.
ms.openlocfilehash: 7fa9d9bf2f1905bf1b59e783d7bceb8cb2e09fa4
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841702"
---
# <a name="applylowdepthand-operation"></a>Opération ApplyLowDepthAnd

Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Inverse un qubit cible donné si et seulement si les deux contrôles qubits sont dans l’État 1, avec T-depth 1, à l’aide de mesures pour effectuer l’opération joint.

```qsharp
operation ApplyLowDepthAnd (control1 : Qubit, control2 : Qubit, target : Qubit) : Unit is Adj + Ctl
```


## <a name="description"></a>Description

Inverse `target` si et seulement si les deux contrôles ont la valeur 1, mais suppose que `target` est dans l’État 0.  L’opération a T-Count 4, T-depth 1 et requiert un qubit d’assistance et peut donc être préférable à une opération CCNOT, si `target` est connu pour être 0.  Le voisin de cette opération est basé sur les mesures et ne nécessite pas de grille T, ni de qubit d’assistance.

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
- Peter selingo : « circuits quantiques de T-depth 1 », phys. Rev. A 87, 042302, 2013 [arXiv : 1210.0974](https://arxiv.org/abs/1210.0974) doi : 10.1103/PhysRevA. 87.042302