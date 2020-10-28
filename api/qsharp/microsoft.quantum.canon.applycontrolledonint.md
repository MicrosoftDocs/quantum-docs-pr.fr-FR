---
uid: Microsoft.Quantum.Canon.ApplyControlledOnInt
title: Opération ApplyControlledOnInt
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyControlledOnInt
qsharp.summary: Applies a unitary operation on the target register if the control register state corresponds to a specified positive integer.
ms.openlocfilehash: c8ea76946143967de4b6ac65986a1c4407ecb633
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92705430"
---
# <a name="applycontrolledonint-operation"></a>Opération ApplyControlledOnInt

Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Packages [](https://nuget.org/packages/)


Applique une opération unitaire sur le registre cible si l’état du registre de contrôle correspond à un entier positif spécifié.

```qsharp
operation ApplyControlledOnInt<'T> (numberState : Int, oracle : ('T => Unit is Adj + Ctl), controlRegister : Qubit[], targetRegister : 'T) : Unit
```


## <a name="input"></a>Entrée

### <a name="numberstate--int"></a>numberState : [entier](xref:microsoft.quantum.lang-ref.int)

Entier non négatif sur lequel l’opération `oracle` doit être contrôlée.


### <a name="oracle--t--unit-adj--ctl"></a>Oracle : 't = [> Adj](xref:microsoft.quantum.lang-ref.unit) + CTL

Opération unitaire à contrôler.


### <a name="controlregister--qubit"></a>controlRegister : [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Registre quantique qui contrôle l’application de `oracle` .


### <a name="targetregister--t"></a>targetRegister : 't

Registre sur lequel appliquer `oracle` .



## <a name="output--unit"></a>Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Paramètres de type

### <a name="t"></a>Peut



## <a name="remarks"></a>Notes

La valeur de `numberState` est interprétée à l’aide d’un encodage Little endian.

`numberState` doit être au maximum de $2 ^ \texttt{Length (controlRegister)}-$1.
Par exemple, `numberState = 537` signifie que `oracle` est appliqué si et seulement si `controlRegister` est dans l’État $ \ket {537} $.