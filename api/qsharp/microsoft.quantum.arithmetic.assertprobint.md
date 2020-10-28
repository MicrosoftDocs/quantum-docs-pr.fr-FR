---
uid: Microsoft.Quantum.Arithmetic.AssertProbInt
title: Opération AssertProbInt
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: AssertProbInt
qsharp.summary: Asserts that the probability of a specific state of a quantum register has the expected value.
ms.openlocfilehash: a8e4217e18528adc0aa9923f1c0dcfb59e1d2488
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92707438"
---
# <a name="assertprobint-operation"></a>Opération AssertProbInt

Espace de noms : [Microsoft. Quantum. Arithmetic](xref:Microsoft.Quantum.Arithmetic)

Packages [](https://nuget.org/packages/)


Déclare que la probabilité d’un état spécifique d’un registre Quantum a la valeur attendue.

```qsharp
operation AssertProbInt (stateIndex : Int, expected : Double, qubits : Microsoft.Quantum.Arithmetic.LittleEndian, tolerance : Double) : Unit
```


## <a name="description"></a>Description

À partir d’un $n $-qubit Quantum State $ \ket{\Psi} = \sum ^ {2 ^ n-1} _ {j = 0} \ alpha_j \ket{j} $, déclare que la probabilité $ | \ alpha_j | ^ 2 $ de l’État $ \ket{j} $ indexée par $j $ a la valeur attendue.

## <a name="input"></a>Entrée

### <a name="stateindex--int"></a>stateIndex : [entier](xref:microsoft.quantum.lang-ref.int)

L’index $j $ de l’État $ \ket{j} $ représenté par un `LittleEndian` Registre.


### <a name="expected--double"></a>ATTENDU : [double](xref:microsoft.quantum.lang-ref.double)

La valeur attendue de $ | \ alpha_j | ^ 2 $.


### <a name="qubits--littleendian"></a>qubits : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

Le registre qubit qui stocke $ \ket{\Psi} $ dans un format avec primauté des octets de poids faible.


### <a name="tolerance--double"></a>tolérance : [double](xref:microsoft.quantum.lang-ref.double)

Tolérance absolue sur la différence entre réel et attendu.



## <a name="output--unit"></a>Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)

