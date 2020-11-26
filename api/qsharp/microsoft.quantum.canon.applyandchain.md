---
uid: Microsoft.Quantum.Canon.ApplyAndChain
title: Opération ApplyAndChain
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyAndChain
qsharp.summary: Computes a chain of AND gates
ms.openlocfilehash: c53bca6ecf964f4358b0a7ff1c61d4e8e195cd7d
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96219360"
---
# <a name="applyandchain-operation"></a>Opération ApplyAndChain

Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Calcule une chaîne de et des portes

```qsharp
operation ApplyAndChain (auxRegister : Qubit[], ctrlRegister : Qubit[], target : Qubit) : Unit is Adj
```


## <a name="description"></a>Description

Le qubits auxiliaire pour calculer des résultats temporaires doit être spécifié explicitement.
La longueur de ce registre est `Length(ctrlRegister) - 2` , s’il y a au moins deux contrôles ; sinon, la longueur est égale à 0.

## <a name="input"></a>Entrée

### <a name="auxregister--qubit"></a>auxRegister : [qubit](xref:microsoft.quantum.lang-ref.qubit)[]




### <a name="ctrlregister--qubit"></a>ctrlRegister : [qubit](xref:microsoft.quantum.lang-ref.qubit)[]




### <a name="target--qubit"></a>cible : [qubit](xref:microsoft.quantum.lang-ref.qubit)





## <a name="output--unit"></a>Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)

