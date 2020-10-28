---
uid: Microsoft.Quantum.Math.ExpModI
title: ExpModI fonction)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ExpModI
qsharp.summary: Returns an integer raised to a given power, with respect to a given modulus.
ms.openlocfilehash: e31273702a9850d0162f160ca412ff6d50f38b28
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92708378"
---
# <a name="expmodi-function"></a>ExpModI fonction)

Espace de noms : [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)

Packages [](https://nuget.org/packages/)


Retourne un entier élevé à une puissance donnée, par rapport à un modulo donné.

```qsharp
function ExpModI (expBase : Int, power : Int, modulus : Int) : Int
```


## <a name="description"></a>Description

Nous allons dénoter expBase par $x $, Power by $p $ et Modulo par $N $.
La fonction retourne $x ^ p \operatorname{mod} N $.

Nous supposons que $N $, $x $ sont positifs et que l’alimentation n’est pas négative.

## <a name="input"></a>Entrée

### <a name="expbase--int"></a>expBase : [entier](xref:microsoft.quantum.lang-ref.int)




### <a name="power--int"></a>puissance : [int](xref:microsoft.quantum.lang-ref.int)




### <a name="modulus--int"></a>modulo : [entier](xref:microsoft.quantum.lang-ref.int)





## <a name="output--int"></a>Sortie : [int](xref:microsoft.quantum.lang-ref.int)



## <a name="remarks"></a>Notes

Prend le temps proportionnel au nombre de bits dans `power` , et non à `power` lui-même.