---
uid: Microsoft.Quantum.Math.ModulusL
title: Fonction modulo
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ModulusL
qsharp.summary: Computes the canonical residue of `value` modulo `modulus`.
ms.openlocfilehash: e7e692059051fde295634c37892ec54e2cf1b095
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92709122"
---
# <a name="modulusl-function"></a>Fonction modulo

Espace de noms : [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)

Packages [](https://nuget.org/packages/)


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