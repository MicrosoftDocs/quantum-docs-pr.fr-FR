---
uid: Microsoft.Quantum.Canon.ApplyControlledOnBitString
title: Opération ApplyControlledOnBitString
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyControlledOnBitString
qsharp.summary: Applies a unitary operation on the target register, controlled on a a state specified by a given bit mask.
ms.openlocfilehash: 6947d2dbdec4cfbb592143024a7c8ccd53a32029
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96219071"
---
# <a name="applycontrolledonbitstring-operation"></a>Opération ApplyControlledOnBitString

Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Applique une opération unitaire sur le registre cible, contrôlée sur un état spécifié par un masque de bits donné.

```qsharp
operation ApplyControlledOnBitString<'T> (bits : Bool[], oracle : ('T => Unit is Adj + Ctl), controlRegister : Qubit[], targetRegister : 'T) : Unit is Adj + Ctl
```


## <a name="input"></a>Entrée

### <a name="bits--bool"></a>bits : [bool](xref:microsoft.quantum.lang-ref.bool)[]

Chaîne de bits pour contrôler l’opération unitaire donnée.


### <a name="oracle--t--unit--is-adj--ctl"></a>Oracle : 't => [unité](xref:microsoft.quantum.lang-ref.unit)  est Adj + CTL

Opération unitaire à appliquer sur le registre cible.


### <a name="controlregister--qubit"></a>controlRegister : [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Registre quantique qui contrôle l’application de `oracle` .


### <a name="targetregister--t"></a>targetRegister : 't

Registre cible à passer `oracle` en tant qu’entrée.



## <a name="output--unit"></a>Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Paramètres de type

### <a name="t"></a>Peut



## <a name="remarks"></a>Notes

Le modèle donné par `bits` peut être plus petit que `controlRegister` , auquel cas des qubits de contrôle supplémentaires sont ignorés (c’est-à-dire qu’ils ne sont ni contrôlés sur $ \ket {0} $, ni sur $ \ket {1} $).
Si `bits` est plus long que `controlRegister` , une erreur est générée.

Par exemple, `bits = [0,1,0,0,1]` signifie que `oracle` est appliqué si et seulement si `controlRegister` est dans l’État $ \ket {0} \ket {1} \ket {0} \ket {0} \ket {1} $.