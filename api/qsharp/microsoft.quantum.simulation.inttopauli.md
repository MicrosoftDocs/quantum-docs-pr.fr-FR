---
uid: Microsoft.Quantum.Simulation.IntToPauli
title: IntToPauli fonction)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: IntToPauli
qsharp.summary: Converts a integer to a single-qubit Pauli operator.
ms.openlocfilehash: f0f1186f14a0dc30bb34bd29f148cdc830fd1337
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92709014"
---
# <a name="inttopauli-function"></a>IntToPauli fonction)

Espace de noms : [Microsoft. Quantum. simulation](xref:Microsoft.Quantum.Simulation)

Packages [](https://nuget.org/packages/)


Convertit un entier en opérateur Pauli qubit unique.

```qsharp
function IntToPauli (idx : Int) : Pauli
```


## <a name="input"></a>Entrée

### <a name="idx--int"></a>idx : [int](xref:microsoft.quantum.lang-ref.int)

Entier dans la plage `0..3` à convertir en opérateurs Pauli.



## <a name="output--pauli"></a>Sortie : [Pauli](xref:microsoft.quantum.lang-ref.pauli)

`Pauli`Opérateur donné par `[PauliI, PauliX, PauliY, PauliZ][idx]` .