---
uid: Microsoft.Quantum.Simulation.IntToPauli
title: IntToPauli fonction)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: IntToPauli
qsharp.summary: Converts a integer to a single-qubit Pauli operator.
ms.openlocfilehash: 18edb600f7b5b33c7ad98e78e32903c570082225
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96229203"
---
# <a name="inttopauli-function"></a>IntToPauli fonction)

Espace de noms : [Microsoft. Quantum. simulation](xref:Microsoft.Quantum.Simulation)

Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Convertit un entier en opérateur Pauli qubit unique.

```qsharp
function IntToPauli (idx : Int) : Pauli
```


## <a name="input"></a>Entrée

### <a name="idx--int"></a>idx : [int](xref:microsoft.quantum.lang-ref.int)

Entier dans la plage `0..3` à convertir en opérateurs Pauli.



## <a name="output--pauli"></a>Sortie : [Pauli](xref:microsoft.quantum.lang-ref.pauli)

`Pauli`Opérateur donné par `[PauliI, PauliX, PauliY, PauliZ][idx]` .