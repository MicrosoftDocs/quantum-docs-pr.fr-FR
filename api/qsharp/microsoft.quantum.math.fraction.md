---
uid: Microsoft.Quantum.Math.Fraction
title: Type de fraction défini par l’utilisateur
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: Fraction
qsharp.summary: Represents a rational number of the form `p/q`. Integer `p` is the first element of the tuple and `q` is the second element of the tuple.
ms.openlocfilehash: 350d470c374fc8e0a3f4c4a9a68ad8566ab88727
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92708504"
---
# <a name="fraction-user-defined-type"></a>Type de fraction défini par l’utilisateur

Espace de noms : [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)

Packages [](https://nuget.org/packages/)


Représente un nombre rationnel du formulaire `p/q` . Integer `p` est le premier élément du tuple et `q` est le deuxième élément du tuple.

```qsharp

newtype Fraction = (Numerator : Int, Denominator : Int);
```



## <a name="named-items"></a>Éléments nommés

### <a name="numerator--int"></a>Numérateur : [int](xref:microsoft.quantum.lang-ref.int)

Numérateur de la fraction.
### <a name="denominator--int"></a>Dénominateur : [entier](xref:microsoft.quantum.lang-ref.int)

Dénominateur de la fraction/