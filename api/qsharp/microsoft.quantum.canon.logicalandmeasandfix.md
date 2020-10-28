---
uid: Microsoft.Quantum.Canon.LogicalANDMeasAndFix
title: Opération LogicalANDMeasAndFix
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: LogicalANDMeasAndFix
qsharp.summary: Computes the logical AND of multiple qubits.
ms.openlocfilehash: 86e4b9a8c6ed5f4f56db0ceefc8051d34e911c4c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92704030"
---
# <a name="logicalandmeasandfix-operation"></a>Opération LogicalANDMeasAndFix

Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Packages [](https://nuget.org/packages/)


Calcule le AND logique de plusieurs qubits.

```qsharp
operation LogicalANDMeasAndFix (ctrlRegister : Qubit[], target : Qubit) : Unit
```


## <a name="input"></a>Entrée

### <a name="ctrlregister--qubit"></a>ctrlRegister : [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Entrée qubits dans l’entrée multiple et la porte.


### <a name="target--qubit"></a>cible : [qubit](xref:microsoft.quantum.lang-ref.qubit)

Qubit sur lequel est écrit la sortie de et. Cela est supposé démarrer toujours dans l’État $ \ket {0} $.



## <a name="output--unit"></a>Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Notes

Quand `ctrlRegister` a exactement $2 $ qubits, cela équivaut à l’opération mais à la phase `CCNOT` avec une phase $e ^ {i \ pi/2} $ sur $ \ket {001} $ et $-e ^ {i \ pi/2} $ sur $ \ket {101} $ et $ \ket {011} $.
Le Voisint est également une approche Measure-and-Fixup qui est l’inverse de l’opération d’origine uniquement dans des cas spéciaux (voir références), mais utilise moins de portes T.

## <a name="references"></a>Références

- [*Craig Gidney* , 1709,06648](https://arxiv.org/abs/1709.06648)