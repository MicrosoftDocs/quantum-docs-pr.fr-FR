---
uid: Microsoft.Quantum.Math.ModulusI
title: Fonction modulo
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ModulusI
qsharp.summary: Computes the canonical residue of `value` modulo `modulus`.
ms.openlocfilehash: 6bbb3877b93e1fc6b38f85a716ba617311c7cfba
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96227775"
---
# <a name="modulusi-function"></a>Fonction modulo

Espace de noms : [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)

Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Calcule le résidu canonique du `value` modulo `modulus` .

```qsharp
function ModulusI (value : Int, modulus : Int) : Int
```


## <a name="input"></a>Entrée

### <a name="value--int"></a>valeur : [int](xref:microsoft.quantum.lang-ref.int)

Valeur de laquelle le résidu est calculé


### <a name="modulus--int"></a>modulo : [entier](xref:microsoft.quantum.lang-ref.int)

Le modulo par lequel les résidus sont précédés doit être positif



## <a name="output--int"></a>Sortie : [int](xref:microsoft.quantum.lang-ref.int)

Entier $r $ entre 0 et `modulus - 1` qui `value - r` est divisible par le modulo

## <a name="remarks"></a>Notes

Cette fonction se comporte différemment de la façon dont l’opérateur `%` se comporte en C# et Q # comme dans le résultat est toujours un entier positif compris entre 0 et `modulus - 1` , même si la valeur est négative.