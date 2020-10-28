---
uid: Microsoft.Quantum.Canon.ApplyToEach
title: Opération ApplyToEach
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToEach
qsharp.summary: Applies a single-qubit operation to each element in a register.
ms.openlocfilehash: e1625829e2e9efd9d39fe0692f01c1cbbffc651c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92704982"
---
# <a name="applytoeach-operation"></a>Opération ApplyToEach

Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Packages [](https://nuget.org/packages/)


Applique une opération à qubit unique à chaque élément d’un registre.

```qsharp
operation ApplyToEach<'T> (singleElementOperation : ('T => Unit), register : 'T[]) : Unit
```


## <a name="input"></a>Entrée

### <a name="singleelementoperation--t--unit"></a>singleElementOperation : 't => [unité](xref:microsoft.quantum.lang-ref.unit) 

Opération à appliquer à chaque qubit.


### <a name="register--t"></a>inscrire : 't []

Tableau de qubits sur lequel appliquer l’opération donnée.



## <a name="output--unit"></a>Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Paramètres de type

### <a name="t"></a>Peut

Cible sur laquelle l’opération agit.

## <a name="see-also"></a>Voir aussi

- [Microsoft. Quantum. Canon. ApplyToEachC](xref:Microsoft.Quantum.Canon.ApplyToEachC)
- [Microsoft. Quantum. Canon. ApplyToEachA](xref:Microsoft.Quantum.Canon.ApplyToEachA)
- [Microsoft. Quantum. Canon. ApplyToEachCA](xref:Microsoft.Quantum.Canon.ApplyToEachCA)