---
uid: Microsoft.Quantum.Math.ExpModL
title: ExpModL fonction)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ExpModL
qsharp.summary: Returns an integer raised to a given power, with respect to a given modulus.
ms.openlocfilehash: 07da113caeb9f6f3f3f3f92f13478f33021bfa14
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96210743"
---
# <a name="expmodl-function"></a>ExpModL fonction)

Espace de noms : [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)

Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Retourne un entier élevé à une puissance donnée, par rapport à un modulo donné.

```qsharp
function ExpModL (expBase : BigInt, power : BigInt, modulus : BigInt) : BigInt
```


## <a name="description"></a>Description

Nous allons dénoter expBase par $x $, Power by $p $ et Modulo par $N $.
La fonction retourne $x ^ p \operatorname{mod} N $.

Nous supposons que $N $, $x $ sont positifs et que l’alimentation n’est pas négative.

## <a name="input"></a>Entrée

### <a name="expbase--bigint"></a>expBase : [bigint](xref:microsoft.quantum.lang-ref.bigint)




### <a name="power--bigint"></a>puissance : [bigint](xref:microsoft.quantum.lang-ref.bigint)




### <a name="modulus--bigint"></a>modulo : [bigint](xref:microsoft.quantum.lang-ref.bigint)





## <a name="output--bigint"></a>Sortie : [bigint](xref:microsoft.quantum.lang-ref.bigint)



## <a name="remarks"></a>Notes

Prend le temps proportionnel au nombre de bits dans `power` , et non à `power` lui-même.