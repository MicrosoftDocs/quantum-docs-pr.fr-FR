---
uid: Microsoft.Quantum.Canon.ConjugatedByCA
title: ConjugatedByCA fonction)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ConjugatedByCA
qsharp.summary: Given outer and inner operations, returns a new operation that conjugates the inner operation by the outer operation.
ms.openlocfilehash: 54301f991d3bda14e2d2a0a6837ee89d299f2e04
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840825"
---
# <a name="conjugatedbyca-function"></a>ConjugatedByCA fonction)

Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


En fonction des opérations externes et internes, retourne une nouvelle opération qui conjugue l’opération interne par l’opération externe.

```qsharp
function ConjugatedByCA<'T> (outerOperation : ('T => Unit is Adj), innerOperation : ('T => Unit is Adj + Ctl)) : ('T => Unit is Adj + Ctl)
```


## <a name="input"></a>Entrée

### <a name="outeroperation--t--unit--is-adj"></a>outerOperation : t => [unité](xref:microsoft.quantum.lang-ref.unit)  est adj

L’opération $U $ qui doit être utilisée pour conjuguer $V $. Notez que l’opération externe $U $ doit être adjointable, mais qu’elle n’a pas besoin d’être contrôlable.


### <a name="inneroperation--t--unit--is-adj--ctl"></a>innerOperation : t => [unité](xref:microsoft.quantum.lang-ref.unit)  est Adj + CTL

L’opération $V être conjuguée.



## <a name="output--t--unit--is-adj--ctl"></a>Sortie : 't => [unité](xref:microsoft.quantum.lang-ref.unit)  est Adj + CTL

Nouvelle opération dont l’action est représentée par le $U unitaire ^ {\dagger} V U $.

## <a name="type-parameters"></a>Paramètres de type

### <a name="t"></a>Peut

Type de la cible sur laquelle les opérations internes et externes agissent.

## <a name="remarks"></a>Notes

L’opération externe est toujours supposée être adjointable, mais elle n’a pas besoin d’être contrôlable pour que l’opération combinée soit contrôlable.

## <a name="see-also"></a>Voir aussi

- [Microsoft. Quantum. Canon. ConjugatedByA](xref:Microsoft.Quantum.Canon.ConjugatedByA)
- [Microsoft. Quantum. Canon. ConjugatedByC](xref:Microsoft.Quantum.Canon.ConjugatedByC)
- [Microsoft. Quantum. Canon. ConjugatedByCA](xref:Microsoft.Quantum.Canon.ConjugatedByCA)
- [Microsoft. Quantum. Canon. ApplyWith](xref:Microsoft.Quantum.Canon.ApplyWith)