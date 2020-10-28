---
uid: Microsoft.Quantum.Canon.AndLadder
title: Opération AndLadder
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: AndLadder
qsharp.summary: Performs a controlled "AND ladder" on a register of target qubits.
ms.openlocfilehash: 05a0e8110539742501883fea75ac368d9946164d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92705518"
---
# <a name="andladder-operation"></a>Opération AndLadder

Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Packages [](https://nuget.org/packages/)


Effectue une « échelle » contrôlée sur un registre de qubits cibles.

```qsharp
operation AndLadder (ccnot : Microsoft.Quantum.Canon.CCNOTop, controls : Qubit[], targets : Qubit[]) : Unit
```


## <a name="description"></a>Description

Cette opération applique une transformation décrite par le mappage suivant de la base de calcul, $ $ \begin{align} \ket{x \_ 1, \dots, x \_ n} \ket{y \_ 1, \dots, y \_ {n-1}} \mapsto \ket{x \_ 1, \dots, x \_ n} \ket{y \_ 1 \oplus (x \_ 1 \land x \_ 2), \dots, y \_ {n-1} \oplus (x \_ 1 \land x \_ 2 \land \cdots \land x \_ {n-1}}, \end{align} $ $ WHERE $ \ket{x \_ 1, \dots, x \_ n} $ fait référence aux États de base de calcul de `controls` , et où $ \ket{y \_ 1, \dots, y \_ {n-1}} $ fait référence aux États de base de calcul de `targets` .

## <a name="input"></a>Entrée

### <a name="ccnot--ccnotop"></a>ccnot : [CCNOTop](xref:Microsoft.Quantum.Canon.CCNOTop)

Porte CCNOT à utiliser pour la construction.


### <a name="controls--qubit"></a>contrôles : [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Un registre de qubits à utiliser comme contrôles pour l’échelle et.
Cette opération laisse les États de base de calcul `controls` invariants.
La longueur de `controls` doit être au moins égale à 2, et doit être égale à un plus la longueur de `targets` .


### <a name="targets--qubit"></a>cibles : [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

La longueur de `targets` doit être au moins égale à 1 et égale à la longueur de `controls` moins un.



## <a name="output--unit"></a>Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Notes

- Utilisé dans le cadre de <xref:microsoft.quantum.canon.applymulticontrolledc> et de <xref:microsoft.quantum.canon.applymulticontrolledca> .
- Pour le diagramme explication et circuit, voir la figure 4,10, section 4,3 dans Nielsen & Chuang.

## <a name="references"></a>Références

- [*Michael A. Nielsen, Isaac L. Chuang* , calcul quantique et informations Quantum](http://doi.org/10.1017/CBO9780511976667)