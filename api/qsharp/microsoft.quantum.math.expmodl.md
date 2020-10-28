---
uid: Microsoft.Quantum.Math.ExpModL
title: ExpModL fonction)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ExpModL
qsharp.summary: Returns an integer raised to a given power, with respect to a given modulus.
ms.openlocfilehash: 73d434bd364847b4e5e06d1a9f460424e0c50850
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92708534"
---
# <a name="expmodl-function"></a>ExpModL fonction)

Espace de noms : [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)

Packages [](https://nuget.org/packages/)


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