---
uid: Microsoft.Quantum.Canon.NoOp
title: Opération NoOp
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: NoOp
qsharp.summary: Performs the identity operation (no-op) on an argument.
ms.openlocfilehash: 45f3c8c9d4bae8ac8f7f60c4e4f8ead5d92e7c00
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98852391"
---
# <a name="noop-operation"></a>Opération NoOp

Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Package : [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


Exécute l’opération d’identité (no-op) sur un argument.

```qsharp
operation NoOp<'T> (input : 'T) : Unit is Adj + Ctl
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