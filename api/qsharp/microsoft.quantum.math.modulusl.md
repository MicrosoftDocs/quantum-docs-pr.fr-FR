---
uid: Microsoft.Quantum.Math.ModulusL
title: Fonction modulo
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ModulusL
qsharp.summary: Computes the canonical residue of `value` modulo `modulus`.
ms.openlocfilehash: 5c9a8ceceac5d2cdac6b82f7f74a85e9443382a2
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96194931"
---
# <a name="modulusl-function"></a>Fonction modulo

Espace de noms : [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)

Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Calcule le résidu canonique du `value` modulo `modulus` .

```qsharp
function ModulusL (value : BigInt, modulus : BigInt) : BigInt
```


## <a name="input"></a>Entrée

### <a name="value--bigint"></a>valeur : [bigint](xref:microsoft.quantum.lang-ref.bigint)

Valeur de laquelle le résidu est calculé


### <a name="modulus--bigint"></a>modulo : [bigint](xref:microsoft.quantum.lang-ref.bigint)

Le modulo par lequel les résidus sont précédés doit être positif



## <a name="output--bigint"></a>Sortie : [bigint](xref:microsoft.quantum.lang-ref.bigint)

Entier $r $ entre 0 et `modulus - 1` qui `value - r` est divisible par le modulo

## <a name="remarks"></a>Notes

Cette fonction se comporte différemment de la façon dont l’opérateur `%` se comporte en C# et Q # comme dans le résultat est toujours un entier positif compris entre 0 et `modulus - 1` , même si la valeur est négative.