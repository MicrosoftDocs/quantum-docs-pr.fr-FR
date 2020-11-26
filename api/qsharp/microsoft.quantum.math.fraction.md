---
uid: Microsoft.Quantum.Math.Fraction
title: Type de fraction défini par l’utilisateur
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: Fraction
qsharp.summary: Represents a rational number of the form `p/q`. Integer `p` is the first element of the tuple and `q` is the second element of the tuple.
ms.openlocfilehash: 1838bb2b605b109742948ec0633b08ca01baea98
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96210673"
---
# <a name="fraction-user-defined-type"></a>Type de fraction défini par l’utilisateur

Espace de noms : [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)

Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Représente un nombre rationnel du formulaire `p/q` . Integer `p` est le premier élément du tuple et `q` est le deuxième élément du tuple.

```qsharp

newtype Fraction = (Numerator : Int, Denominator : Int);
```



## <a name="named-items"></a>Éléments nommés

### <a name="numerator--int"></a>Numérateur : [int](xref:microsoft.quantum.lang-ref.int)

Numérateur de la fraction.
### <a name="denominator--int"></a>Dénominateur : [entier](xref:microsoft.quantum.lang-ref.int)

Dénominateur de la fraction/