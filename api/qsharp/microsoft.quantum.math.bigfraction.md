---
uid: Microsoft.Quantum.Math.BigFraction
title: Type défini par l’utilisateur BigFraction
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: BigFraction
qsharp.summary: Represents a rational number of the form `p/q`. Integer `p` is the first element of the tuple and `q` is the second element of the tuple.
ms.openlocfilehash: 1c9b9e350c4fa3664b2c66da05149005b1170ec3
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96211081"
---
# <a name="bigfraction-user-defined-type"></a>Type défini par l’utilisateur BigFraction

Espace de noms : [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)

Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Représente un nombre rationnel du formulaire `p/q` . Integer `p` est le premier élément du tuple et `q` est le deuxième élément du tuple.

```qsharp

newtype BigFraction = (Numerator : BigInt, Denominator : BigInt);
```



## <a name="named-items"></a>Éléments nommés

### <a name="numerator--bigint"></a>Numérateur : [bigint](xref:microsoft.quantum.lang-ref.bigint)

Numérateur de la fraction.
### <a name="denominator--bigint"></a>Dénominateur : [bigint](xref:microsoft.quantum.lang-ref.bigint)

Dénominateur de la fraction/