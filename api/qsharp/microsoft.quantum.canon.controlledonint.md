---
uid: Microsoft.Quantum.Canon.ControlledOnInt
title: ControlledOnInt fonction)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ControlledOnInt
qsharp.summary: Returns a unitary operator that applies an oracle on the target register if the control register state corresponds to a specified positive integer.
ms.openlocfilehash: 4c48f3257f91fc50040d02cae7c2f7bdf87ea7c5
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92704310"
---
# <a name="controlledonint-function"></a>ControlledOnInt fonction)

Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Packages [](https://nuget.org/packages/)


Retourne un opérateur unitaire qui applique Oracle sur le registre cible si l’état du registre de contrôle correspond à un entier positif spécifié.

```qsharp
function ControlledOnInt<'T> (numberState : Int, oracle : ('T => Unit is Adj + Ctl)) : ((Qubit[], 'T) => Unit is Adj + Ctl)
```


## <a name="input"></a>Entrée

### <a name="numberstate--int"></a>numberState : [entier](xref:microsoft.quantum.lang-ref.int)

Entier positif.


### <a name="oracle--t--unit-adj--ctl"></a>Oracle : 't = [> Adj](xref:microsoft.quantum.lang-ref.unit) + CTL

Opérateur unitaire.



## <a name="output--qubitt--unit-adj--ctl"></a>Sortie : ([qubit](xref:microsoft.quantum.lang-ref.qubit)[], t) [=> ajuster](xref:microsoft.quantum.lang-ref.unit) + CTL

Opérateur unitaire qui s’applique au `oracle` Registre cible si l’état du registre de contrôle correspond à l’état du nombre `numberState` .

## <a name="type-parameters"></a>Paramètres de type

### <a name="t"></a>Peut



## <a name="remarks"></a>Notes

La valeur de `numberState` est interprétée à l’aide d’un encodage Little endian.