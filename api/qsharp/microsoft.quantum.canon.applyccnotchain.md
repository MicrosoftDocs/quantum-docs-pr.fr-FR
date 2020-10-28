---
uid: Microsoft.Quantum.Canon.ApplyCCNOTChain
title: Opération ApplyCCNOTChain
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyCCNOTChain
qsharp.summary: Implements a cascade of CCNOT gates controlled on corresponding bits of two qubit registers, acting on the next qubit of one of the registers. Starting from the qubits at position 0 in both registers as controls, CCNOT is applied to the qubit at position 1 of the target register, then controlled by the qubits at position 1 acting on the qubit at position 2 in the target register, etc., ending with an action on the target qubit in position `Length(nQubits)-1`.
ms.openlocfilehash: e4f38e9bb54839076b817f6e61e96ca6a550576b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92705454"
---
# <a name="applyccnotchain-operation"></a>Opération ApplyCCNOTChain

Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Packages [](https://nuget.org/packages/)


Implémente une cascade de portes CCNOT contrôlées sur les bits correspondants de deux registres qubit, agissant sur la qubit suivante de l’un des registres.
À partir de qubits à la position 0 dans les deux registres en tant que contrôles, CCNOT est appliqué au qubit à la position 1 du Registre cible, puis contrôlé par le qubits à la position 1 agissant sur le qubit à la position 2 dans le registre cible, etc., se terminant par une action sur le qubit cible à la position 2 `Length(nQubits)-1` .

```qsharp
operation ApplyCCNOTChain (register : Qubit[], targets : Qubit[]) : Unit
```


## <a name="input"></a>Entrée

### <a name="register--qubit"></a>Register : [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Registre qubit, utilisé uniquement pour les contrôles.


### <a name="targets--qubit"></a>cibles : [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Registre qubit, utilisé pour les contrôles et comme cible.



## <a name="output--unit"></a>Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Notes

Le registre qubit cible doit avoir un qubit de plus que l’autre.