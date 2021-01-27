---
uid: Microsoft.Quantum.Diagnostics.AssertOperationsEqualReferenced
title: Opération AssertOperationsEqualReferenced
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AssertOperationsEqualReferenced
qsharp.summary: >-
  Given two operations, asserts that they act identically for all input states.

  This assertion is implemented by using the Choi–Jamiołkowski isomorphism to reduce the assertion to one of a qubit state assertion on two entangled registers. Thus, this operation needs only a single call to each operation being tested, but requires twice as many qubits to be allocated. This assertion can be used to ensure, for instance, that an optimized version of an operation acts identically to its naïve implementation, or that an operation which acts on a range of non-quantum inputs agrees with known cases.
ms.openlocfilehash: 045f00a720e9f4d2e6993c66ace44a81e192ff30
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853461"
---
# <a name="assertoperationsequalreferenced-operation"></a>Opération AssertOperationsEqualReferenced

Espace de noms : [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)

Package : [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


À partir de deux opérations, déclare qu’elles agissent de la même manière pour tous les États d’entrée.

Cette assertion est implémentée à l’aide de la isomorphism Choi – Jamiołkowski pour réduire l’assertion à l’une des affirmations d’état de qubit sur deux registres.
Par conséquent, cette opération n’a besoin que d’un seul appel à chaque opération en cours de test, mais nécessite deux fois plus de qubits à allouer.
Cette assertion peut être utilisée pour s’assurer, par exemple, qu’une version optimisée d’une opération agit de la même manière que son implémentation naïve, ou qu’une opération qui agit sur une plage d’entrées non quantiques accepte les cas connus.

```qsharp
operation AssertOperationsEqualReferenced (nQubits : Int, actual : (Qubit[] => Unit), expected : (Qubit[] => Unit is Adj)) : Unit
```


## <a name="input"></a>Entrée

### <a name="nqubits--int"></a>nQubits : [entier](xref:microsoft.quantum.lang-ref.int)

Nombre de qubits à transmettre à chaque opération.


### <a name="actual--qubit--unit"></a>réel : [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [unité](xref:microsoft.quantum.lang-ref.unit) 

Opération à tester.


### <a name="expected--qubit--unit--is-adj"></a>ATTENDU : [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [unité](xref:microsoft.quantum.lang-ref.unit)  est adj

Opération définissant le comportement attendu pour l’opération testée.



## <a name="output--unit"></a>Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Notes

Cette opération nécessite que l’opération modélisant le comportement attendu soit adjointable, afin que l’inverse puisse être effectué sur le registre cible seul.
Formellement, il est possible de spécifier une opération de transposer, qui assouplit cette exigence, mais l’opération de transposer n’est pas en général physiquement réalisable pour les opérations de Quantum arbitraires et n’est donc pas incluse ici comme une option.