---
uid: Microsoft.Quantum.Diagnostics.AssertOperationsEqualInPlaceCompBasis
title: Opération AssertOperationsEqualInPlaceCompBasis
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AssertOperationsEqualInPlaceCompBasis
qsharp.summary: Checks if the operation `givenU` is equal to the operation `expectedU` on the given input size  by checking the action of the operations only on the vectors from the computational basis. This is a necessary, but not sufficient, condition for the equality of two unitaries.
ms.openlocfilehash: 3275680f86ca2a178c7f044b97d226fe41c3186c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92702751"
---
# <a name="assertoperationsequalinplacecompbasis-operation"></a>Opération AssertOperationsEqualInPlaceCompBasis

Espace de noms : [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)

Packages [](https://nuget.org/packages/)


Vérifie si l’opération `givenU` est égale à l’opération `expectedU` sur la taille d’entrée donnée en vérifiant l’action des opérations uniquement sur les vecteurs à partir de la base de calcul.
Il s’agit d’une condition nécessaire, mais pas suffisante, pour l’égalité de deux unités.

```qsharp
operation AssertOperationsEqualInPlaceCompBasis (nQubits : Int, givenU : (Qubit[] => Unit), expectedU : (Qubit[] => Unit is Adj)) : Unit
```


## <a name="input"></a>Entrée

### <a name="nqubits--int"></a>nQubits : [entier](xref:microsoft.quantum.lang-ref.int)

Nombre de qubits $n $ que les opérations `givenU` et `expectedU` utilisent.


### <a name="givenu--qubit--unit"></a>donné : [qubit](xref:microsoft.quantum.lang-ref.qubit)[] = [unité](xref:microsoft.quantum.lang-ref.unit)> 

Opération sur $n $ qubits à vérifier.


### <a name="expectedu--qubit--unit-adj"></a>expected : [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => ajustement d' [unité](xref:microsoft.quantum.lang-ref.unit)

Opération de référence sur $n $ qubits `givenU` à comparer.



## <a name="output--unit"></a>Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)

