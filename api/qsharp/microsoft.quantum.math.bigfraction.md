---
uid: Microsoft.Quantum.Math.BigFraction
title: Type défini par l’utilisateur BigFraction
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: BigFraction
qsharp.summary: Represents a rational number of the form `p/q`. Integer `p` is the first element of the tuple and `q` is the second element of the tuple.
ms.openlocfilehash: bfbf49e7a3d060417e506a1977c20adc08b81f0e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846900"
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