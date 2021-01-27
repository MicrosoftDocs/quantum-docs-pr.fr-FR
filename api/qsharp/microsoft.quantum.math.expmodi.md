---
uid: Microsoft.Quantum.Math.ExpModI
title: ExpModI fonction)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ExpModI
qsharp.summary: Returns an integer raised to a given power, with respect to a given modulus.
ms.openlocfilehash: dd4fc7d98275f6a02e3b13163b92f0812c92a82f
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98857030"
---
# <a name="expmodi-function"></a>ExpModI fonction)

Espace de noms : [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)

Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


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