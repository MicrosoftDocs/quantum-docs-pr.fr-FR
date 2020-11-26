---
uid: Microsoft.Quantum.Canon.ControlledOnInt
title: ControlledOnInt fonction)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ControlledOnInt
qsharp.summary: Returns a unitary operator that applies an oracle on the target register if the control register state corresponds to a specified positive integer.
ms.openlocfilehash: 3cc5c00d9c7295106901149e06571ef1963d1323
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96207256"
---
# <a name="controlledonint-function"></a>ControlledOnInt fonction)

Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Retourne un opérateur unitaire qui applique Oracle sur le registre cible si l’état du registre de contrôle correspond à un entier positif spécifié.

```qsharp
function ControlledOnInt<'T> (numberState : Int, oracle : ('T => Unit is Adj + Ctl)) : ((Qubit[], 'T) => Unit is Adj + Ctl)
```


## <a name="input"></a>Entrée

### <a name="numberstate--int"></a>numberState : [entier](xref:microsoft.quantum.lang-ref.int)

Entier positif.


### <a name="oracle--t--unit--is-adj--ctl"></a>Oracle : 't => [unité](xref:microsoft.quantum.lang-ref.unit)  est Adj + CTL

Opérateur unitaire.



## <a name="output--qubitt--unit--is-adj--ctl"></a>Sortie : ([qubit](xref:microsoft.quantum.lang-ref.qubit)[], t) => [unité](xref:microsoft.quantum.lang-ref.unit)  est Adj + CTL

Opérateur unitaire qui s’applique au `oracle` Registre cible si l’état du registre de contrôle correspond à l’état du nombre `numberState` .

## <a name="type-parameters"></a>Paramètres de type

### <a name="t"></a>Peut



## <a name="remarks"></a>Notes

La valeur de `numberState` est interprétée à l’aide d’un encodage Little endian.