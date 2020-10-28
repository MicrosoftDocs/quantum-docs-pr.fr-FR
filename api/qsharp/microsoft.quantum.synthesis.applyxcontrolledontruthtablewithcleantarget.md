---
uid: Microsoft.Quantum.Synthesis.ApplyXControlledOnTruthTableWithCleanTarget
title: Opération ApplyXControlledOnTruthTableWithCleanTarget
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: ApplyXControlledOnTruthTableWithCleanTarget
qsharp.summary: Applies the @"microsoft.quantum.intrinsic.x" operation on `target`, if the Boolean function `func` evaluates to true for the classical assignment in `controlRegister`.
ms.openlocfilehash: b43a5351985339bcf7c1f2bbe03ae6dc6dfdd165
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92709179"
---
# <a name="applyxcontrolledontruthtablewithcleantarget-operation"></a>Opération ApplyXControlledOnTruthTableWithCleanTarget

Espace de noms : [Microsoft. Quantum. Synthesis](xref:Microsoft.Quantum.Synthesis)

Packages [](https://nuget.org/packages/)


Applique l' @"microsoft.quantum.intrinsic.x" opération sur `target` , si la fonction booléenne `func` prend la valeur true pour l’assignation classique dans `controlRegister` .

```qsharp
operation ApplyXControlledOnTruthTableWithCleanTarget (func : BigInt, controlRegister : Qubit[], target : Qubit) : Unit
```


## <a name="description"></a>Description

Cette opération implémente un cas particulier de @"microsoft.quantum.synthesis.applyxcontrolledontruthtable" , dans lequel le qubit cible est connu comme étant dans l’état $ {0} \ket $.

L’implémentation utilise des @"microsoft.quantum.intrinsic.cnot" portes et @"microsoft.quantum.intrinsic.r1" .  L’implémentation de l’opération joint est optimisée et utilise le décalcul basé sur les mesures.

## <a name="input"></a>Entrée

### <a name="func--bigint"></a>Func : [bigint](xref:microsoft.quantum.lang-ref.bigint)

Table de vérité booléenne représentée comme grand entier


### <a name="controlregister--qubit"></a>controlRegister : [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Registre de contrôle qubits


### <a name="target--qubit"></a>cible : [qubit](xref:microsoft.quantum.lang-ref.qubit)

Qubit cible (doit être dans l’État $ \ket {0} $)



## <a name="output--unit"></a>Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)



## <a name="see-also"></a>Voir aussi

- [Microsoft. Quantum. Synthesis. ApplyXControlledOnTruthTable](xref:Microsoft.Quantum.Synthesis.ApplyXControlledOnTruthTable)