---
uid: Microsoft.Quantum.Canon.ApplyMultiControlledCA
title: Opération ApplyMultiControlledCA
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyMultiControlledCA
qsharp.summary: Applies a multiply controlled version of a singly controlled operation. The modifier `CA` indicates that the single-qubit operation is controllable and adjointable.
ms.openlocfilehash: 5662efe0dc6f665206b8773596bf885ce631413c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92705195"
---
# <a name="applymulticontrolledca-operation"></a>Opération ApplyMultiControlledCA

Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Packages [](https://nuget.org/packages/)


Applique une version contrôlée par multiplication d’une opération contrôlée de façon unique.
Le modificateur `CA` indique que l’opération de qubit simple est contrôlable et adjointable.

```qsharp
operation ApplyMultiControlledCA (singlyControlledOp : (Qubit[] => Unit is Adj), ccnot : Microsoft.Quantum.Canon.CCNOTop, controls : Qubit[], targets : Qubit[]) : Unit
```


## <a name="input"></a>Entrée

### <a name="singlycontrolledop--qubit--unit-adj"></a>singlyControlledOp : [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => ajustement d' [unité](xref:microsoft.quantum.lang-ref.unit)

Opération contrôlée sur un qubit unique.
Le premier qubit de l’argument de l’opération est supposé être un contrôle et le reste est supposé être qubits cible.
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

- [*Michael A. Nielsen, Isaac L. Chuang* , calcul quantique et informations Quantum](http://doi.org/10.1017/CBO9780511976667)

## <a name="see-also"></a>Voir aussi

- [Microsoft. Quantum. Canon. ApplyMultiControlledC](xref:Microsoft.Quantum.Canon.ApplyMultiControlledC)