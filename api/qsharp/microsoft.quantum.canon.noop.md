---
uid: Microsoft.Quantum.Canon.NoOp
title: Opération NoOp
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: NoOp
qsharp.summary: Performs the identity operation (no-op) on an argument.
ms.openlocfilehash: 987e39577c3b736418234431ed7a915ae461f763
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92703948"
---
# <a name="noop-operation"></a>Opération NoOp

Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Packages [](https://nuget.org/packages/)


Exécute l’opération d’identité (no-op) sur un argument.

```qsharp
operation NoOp<'T> (input : 'T) : Unit
```


## <a name="description"></a>Description

Cette opération accepte une valeur de n’importe quel type et ne fait rien d’autre.
Cela peut être utile lorsqu’une entrée d’un type d’opération est attendue, mais qu’aucune action ne doit être effectuée.
Par exemple, si un syndrome de correction d’erreur particulier indique qu’aucune erreur ne s’est produite, `NoOp<Qubit[]>` il peut s’agir de la bonne procédure de récupération.
De même, si une opération attend une procédure de préparation d’État comme entrée, `NoOp<Qubit[]>` peut être utilisé pour préparer l’État $ \ket{0 \cdots 0} $.

## <a name="input"></a>Entrée

### <a name="input--t"></a>entrée : 't

Valeur à ignorer.



## <a name="output--unit"></a>Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Paramètres de type

### <a name="t"></a>Peut



## <a name="remarks"></a>Notes

Dans presque tous les cas, le paramètre de type `NoOp` doit être spécifié explicitement. Par exemple, `NoOp<Qubit>` est identique à <xref:microsoft.quantum.intrinsic.i> .

## <a name="see-also"></a>Voir aussi

- [Microsoft. Quantum. Intrinsic. I](xref:Microsoft.Quantum.Intrinsic.I)