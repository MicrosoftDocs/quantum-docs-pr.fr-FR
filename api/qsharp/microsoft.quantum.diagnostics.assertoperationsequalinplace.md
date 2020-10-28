---
uid: Microsoft.Quantum.Diagnostics.AssertOperationsEqualInPlace
title: Opération AssertOperationsEqualInPlace
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AssertOperationsEqualInPlace
qsharp.summary: >-
  Given two operations, asserts that they act identically for all input states.

  This assertion is implemented by checking the action of the operations on all states of the form $V_0 \otimes ... \otimes V_{n-1}$, where $V_k$ is one of the states $\ket{0}$, $\ket{1}$, $\ket{+}$ and $\ket{i}$ (+1 eigenstate of Pauli Y operator).

  This assertion uses $n$ qubits and requires multiple calls of the operations being compared.
ms.openlocfilehash: 407a139da816281346eb06849f81e91b83202653
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92702754"
---
# <a name="assertoperationsequalinplace-operation"></a>Opération AssertOperationsEqualInPlace

Espace de noms : [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)

Packages [](https://nuget.org/packages/)


À partir de deux opérations, déclare qu’elles agissent de la même manière pour tous les États d’entrée.

Cette assertion est implémentée en vérifiant l’action des opérations sur tous les États de la forme $V _0 \otimes... \otimes V_ {n-1} $, où $V _k $ est l’un des États $ \ket {0} $, $ \ket {1} $, $ \ket{+} $ et $ \ket{i} $ (+ 1 eigenstate de l’opérateur Y Pauli).

Cette assertion utilise $n $ qubits et nécessite plusieurs appels des opérations comparées.

```qsharp
operation AssertOperationsEqualInPlace (nQubits : Int, givenU : (Qubit[] => Unit), expectedU : (Qubit[] => Unit is Adj)) : Unit
```


## <a name="input"></a>Entrée

### <a name="nqubits--int"></a>nQubits : [entier](xref:microsoft.quantum.lang-ref.int)

Nombre de qubits $n $ que les opérations `givenU` et `expectedU` utilisent.


### <a name="givenu--qubit--unit"></a>donné : [qubit](xref:microsoft.quantum.lang-ref.qubit)[] = [unité](xref:microsoft.quantum.lang-ref.unit)> 

Opération sur $n $ qubits à vérifier.


### <a name="expectedu--qubit--unit-adj"></a>expected : [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => ajustement d' [unité](xref:microsoft.quantum.lang-ref.unit)

Opération de référence sur $n $ qubits `givenU` à comparer.



## <a name="output--unit"></a>Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)



## <a name="references"></a>Références

La base des États $ \ket {0} $, $ \ket {1} $, $ \ket{+} $ et $ \ket{i} $ est la base de Chuang-Nielsen, décrite dans [ *i. L. Chuang, M. A. Nielsen*](https://arxiv.org/abs/quant-ph/9610001).

## <a name="see-also"></a>Voir aussi

- [Microsoft. Quantum. Diagnostics. AssertOperationsEqualReferenced](xref:Microsoft.Quantum.Diagnostics.AssertOperationsEqualReferenced)