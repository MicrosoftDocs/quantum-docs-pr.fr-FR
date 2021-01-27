---
uid: Microsoft.Quantum.Arithmetic.AssertProbInt
title: Opération AssertProbInt
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: AssertProbInt
qsharp.summary: Asserts that the probability of a specific state of a quantum register has the expected value.
ms.openlocfilehash: 85ff04bbad9dc2ed0f803db65508fdfbb0d22c56
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843401"
---
# <a name="assertprobint-operation"></a>Opération AssertProbInt

Espace de noms : [Microsoft. Quantum. Arithmetic](xref:Microsoft.Quantum.Arithmetic)

Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


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



## <a name="example"></a>Exemple

Supposons que le `qubits` Registre encode un État Quantum 3-qubit $ \ket{\Psi} = \ sqrt {1/8} \ Ket {0} + \ sqrt {7/8} \ Ket {6} $ dans un format avec primauté des octets de poids faible (Little-endian).
Cela signifie que le nombre indique $ \ket {0} \equiv\ket {0} \ket {0} \ket {0} $ et $ \ket \equiv\ket \ket {6} {0} {1} {1} $. Les affirmations suivantes ont ensuite été effectuées :

```qsharp
AssertProbInt(0, 0.125, qubits, 10e-10);
AssertProbInt(6, 0.875, qubits, 10e-10);
```