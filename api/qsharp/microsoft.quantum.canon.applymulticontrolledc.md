---
uid: Microsoft.Quantum.Canon.ApplyMultiControlledC
title: Opération ApplyMultiControlledC
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyMultiControlledC
qsharp.summary: Applies a multiply controlled version of a singly controlled operation. The modifier `C` indicates that the single-qubit operation is controllable.
ms.openlocfilehash: 2d5703eed3a3b6e611ae7c993febf018fcb148b3
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96218408"
---
# <a name="applymulticontrolledc-operation"></a>Opération ApplyMultiControlledC

Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Applique une version contrôlée par multiplication d’une opération contrôlée de façon unique.
Le modificateur `C` indique que l’opération de qubit simple est contrôlable.

```qsharp
operation ApplyMultiControlledC (singlyControlledOp : (Qubit[] => Unit), ccnot : Microsoft.Quantum.Canon.CCNOTop, controls : Qubit[], targets : Qubit[]) : Unit is Ctl
```


## <a name="input"></a>Entrée

### <a name="singlycontrolledop--qubit--unit"></a>singlyControlledOp : [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [unité](xref:microsoft.quantum.lang-ref.unit) 

Opération contrôlée sur un qubit unique.
Le premier qubit de l’argument de l’opération est supposé être un contrôle et les autres sont supposés être des qubits cibles.
`ApplyMultiControlled` appelle toujours `singlyControlledOp` avec un argument de longueur au moins égal à 1.


### <a name="ccnot--ccnotop"></a>ccnot : [CCNOTop](xref:Microsoft.Quantum.Canon.CCNOTop)

Porte contrôlée par contrôle-non à utiliser pour la construction.


### <a name="controls--qubit"></a>contrôles : [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Qubits `singlyControlledOp` à contrôler sur.
La longueur de `controls` doit être au moins égale à 1.


### <a name="targets--qubit"></a>cibles : [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Qubits cible sur lequel `singlyControlledOp` agit.



## <a name="output--unit"></a>Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Notes

Cette opération utilise uniquement Clean Ancilla qubits.

Pour l’explication et le schéma du circuit, voir la figure 4,10, section 4,3 dans Nielsen & Chuang

## <a name="references"></a>Références

- [*Michael A. Nielsen, Isaac L. Chuang*, calcul quantique et informations Quantum](http://doi.org/10.1017/CBO9780511976667)

## <a name="see-also"></a>Voir aussi

- [Microsoft. Quantum. Canon. ApplyMultiControlledCA](xref:Microsoft.Quantum.Canon.ApplyMultiControlledCA)