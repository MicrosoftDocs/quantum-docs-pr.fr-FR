---
uid: Microsoft.Quantum.Math.BigFraction
title: Type défini par l’utilisateur BigFraction
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: BigFraction
qsharp.summary: Represents a rational number of the form `p/q`. Integer `p` is the first element of the tuple and `q` is the second element of the tuple.
ms.openlocfilehash: a8daa54947097b95040a2dfa7a4d1b90bfaff856
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92708312"
---
# <a name="bigfraction-user-defined-type"></a>Type défini par l’utilisateur BigFraction

Espace de noms : [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)

Packages [](https://nuget.org/packages/)


Représente un nombre rationnel du formulaire `p/q` . Integer `p` est le premier élément du tuple et `q` est le deuxième élément du tuple.

```qsharp

newtype BigFraction = (Numerator : BigInt, Denominator : BigInt);
```



## <a name="named-items"></a>Éléments nommés

### <a name="numerator--bigint"></a>Numérateur : [bigint](xref:microsoft.quantum.lang-ref.bigint)

Numérateur de la fraction.
### <a name="denominator--bigint"></a>Dénominateur : [bigint](xref:microsoft.quantum.lang-ref.bigint)

Dénominateur de la fraction/