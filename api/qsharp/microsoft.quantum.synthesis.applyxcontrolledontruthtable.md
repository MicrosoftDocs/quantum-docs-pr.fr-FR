---
uid: Microsoft.Quantum.Synthesis.ApplyXControlledOnTruthTable
title: Opération ApplyXControlledOnTruthTable
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: ApplyXControlledOnTruthTable
qsharp.summary: Applies the @"microsoft.quantum.intrinsic.x" operation on `target`, if the Boolean function `func` evaluates to true for the classical assignment in `controlRegister`.
ms.openlocfilehash: 73d63936f02a52dfbbad7b8575110177a9e4463d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92709185"
---
# <a name="applyxcontrolledontruthtable-operation"></a>Opération ApplyXControlledOnTruthTable

Espace de noms : [Microsoft. Quantum. Synthesis](xref:Microsoft.Quantum.Synthesis)

Packages [](https://nuget.org/packages/)


Applique l' @"microsoft.quantum.intrinsic.x" opération sur `target` , si la fonction booléenne `func` prend la valeur true pour l’assignation classique dans `controlRegister` .

```qsharp
operation ApplyXControlledOnTruthTable (func : BigInt, controlRegister : Qubit[], target : Qubit) : Unit
```


## <a name="description"></a>Description

L’opération implémente l’opération unitaire \begin{align} U\ket {x} \ Ket {y} = \ket{x}\ket{y \oplus f (x)} \end{align} où $x $ et $y $ représentent `controlRegister` et `target` , respectivement.

La fonction booléenne $f $ est représentée sous la forme d’un tableau de vérité dans le cadre d’un grand entier.
Par exemple, la fonction majoritaire sur trois entrées est représentée par le bitstring `11101000` , où le bit le plus significatif `1` correspond à l’assignation d’entrée `(1, 1, 1)` , et le bit le moins significatif `0` correspond à l’assignation d’entrée `(0, 0, 0)` .
Il peut être représenté par le grand entier `0xE8L` en notation hexadécimale ou comme en `232L` notation décimale.  Le `L` suffixe indique que la constante est de type `BigInt` .
Vous trouverez plus d’informations sur cette représentation dans les [tables de vérité Kata](https://github.com/microsoft/QuantumKatas/tree/main/TruthTables).

L’implémentation utilise des @"microsoft.quantum.intrinsic.cnot" portes et @"microsoft.quantum.intrinsic.r1" .

## <a name="input"></a>Entrée

### <a name="func--bigint"></a>Func : [bigint](xref:microsoft.quantum.lang-ref.bigint)

Table de vérité booléenne représentée comme grand entier


### <a name="controlregister--qubit"></a>controlRegister : [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Registre de contrôle qubits


### <a name="target--qubit"></a>cible : [qubit](xref:microsoft.quantum.lang-ref.qubit)

Qubit cible



## <a name="output--unit"></a>Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)



## <a name="references"></a>Références

- [*N. Schuch* , *J. Siewert* , PRL 91, no. 027902, 2003, arXiv : quant-pH/0303063](https://arxiv.org/abs/quant-ph/0303063)
- [*Mathias Soeken* , *Martin Roetteler* , arXiv : 2005.12310](https://arxiv.org/abs/2005.12310)

## <a name="see-also"></a>Voir aussi

- [Microsoft. Quantum. Synthesis. ApplyXControlledOnTruthTableWithCleanTarget](xref:Microsoft.Quantum.Synthesis.ApplyXControlledOnTruthTableWithCleanTarget)