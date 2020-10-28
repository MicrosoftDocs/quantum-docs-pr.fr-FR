---
uid: Microsoft.Quantum.Canon.ApplyToEachC
title: Opération ApplyToEachC
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToEachC
qsharp.summary: Applies a single-qubit operation to each element in a register. The modifier `C` indicates that the single-qubit operation is controllable.
ms.openlocfilehash: dfa18b6eb7a2c42fa2982994a2fc92170b52599c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92704966"
---
# <a name="applytoeachc-operation"></a>Opération ApplyToEachC

Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Packages [](https://nuget.org/packages/)


Applique une opération à qubit unique à chaque élément d’un registre.
Le modificateur `C` indique que l’opération de qubit simple est contrôlable.

```qsharp
operation ApplyToEachC<'T> (singleElementOperation : ('T => Unit is Ctl), register : 'T[]) : Unit
```


## <a name="input"></a>Entrée

### <a name="singleelementoperation--t--unit-ctl"></a>singleElementOperation : t => CTL de l' [unité](xref:microsoft.quantum.lang-ref.unit)

Opération à appliquer à chaque qubit.


### <a name="register--t"></a>inscrire : 't []

Tableau de qubits sur lequel appliquer l’opération donnée.



## <a name="output--unit"></a>Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Paramètres de type

### <a name="t"></a>Peut

Cible sur laquelle l’opération agit.

## <a name="see-also"></a>Voir aussi

- [Microsoft. Quantum. Canon. ApplyToEach](xref:Microsoft.Quantum.Canon.ApplyToEach)