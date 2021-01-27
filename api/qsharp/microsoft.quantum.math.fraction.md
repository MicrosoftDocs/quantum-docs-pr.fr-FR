---
uid: Microsoft.Quantum.Math.Fraction
title: Type de fraction défini par l’utilisateur
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: Fraction
qsharp.summary: Represents a rational number of the form `p/q`. Integer `p` is the first element of the tuple and `q` is the second element of the tuple.
ms.openlocfilehash: a56d28e34938729a8e4ffda5f870e0b6a25be017
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98857515"
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