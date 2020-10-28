---
uid: Microsoft.Quantum.Intrinsic.Reset
title: Opération de réinitialisation
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: Reset
qsharp.summary: Given a single qubit, measures it and ensures it is in the |0⟩ state such that it can be safely released.
ms.openlocfilehash: c89cbbce49e294e56abc11b3b0492d2ed8e980a8
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92707110"
---
# <a name="reset-operation"></a>Opération de réinitialisation

Espace de noms : [Microsoft. Quantum. Intrinsic](xref:Microsoft.Quantum.Intrinsic)

Packages [](https://nuget.org/packages/)


Étant donné un qubit unique, le mesure et s’assure qu’il est dans l’État | 0 ⟩, de sorte qu’il peut être libéré en toute sécurité.

```qsharp
operation Reset (target : Qubit) : Unit
```


## <a name="input"></a>Entrée

### <a name="target--qubit"></a>cible : [qubit](xref:microsoft.quantum.lang-ref.qubit)

Qubit dont l’État doit être réinitialisé à $ \ket {0} $.



## <a name="output--unit"></a>Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)

