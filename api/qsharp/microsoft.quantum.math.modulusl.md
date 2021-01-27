---
uid: Microsoft.Quantum.Math.ModulusL
title: Fonction modulo
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ModulusL
qsharp.summary: Computes the canonical residue of `value` modulo `modulus`.
ms.openlocfilehash: 6be2edb052cf55f8e8465c76b5dcadeb61ff11ea
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842741"
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

Cette fonction se comporte différemment de la façon dont l’opérateur `%` se comporte en C# et Q # comme dans le résultat est toujours un entier non négatif compris entre 0 et `modulus - 1` , même si la valeur est négative.