---
uid: Microsoft.Quantum.Math.RealMod
title: RealMod fonction)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: RealMod
qsharp.summary: Computes the modulus between two real numbers.
ms.openlocfilehash: 6ec799885bd2f0d35314ed727356499efbe9fcf8
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92706798"
---
# <a name="realmod-function"></a>RealMod fonction)

Espace de noms : [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)

Packages [](https://nuget.org/packages/)


Calcule le modulo entre deux nombres réels.

```qsharp
function RealMod (value : Double, modulo : Double, minValue : Double) : Double
```


## <a name="input"></a>Entrée

### <a name="value--double"></a>valeur : [double](xref:microsoft.quantum.lang-ref.double)

Nombre réel $x $ pour prendre le modulo de.


### <a name="modulo--double"></a>modulo : [double](xref:microsoft.quantum.lang-ref.double)

Nombre réel pour prendre le modulo de $x $ par rapport à.


### <a name="minvalue--double"></a>minValue : [double](xref:microsoft.quantum.lang-ref.double)

Valeur la plus petite à retourner par cette fonction.



## <a name="output--double"></a>Sortie : [double](xref:microsoft.quantum.lang-ref.double)



## <a name="remarks"></a>Notes

Cette fonction calcule le modulo réel en encapsulant la ligne réelle sur le cercle d’unité, puis en recherchant l’angle sur le cercle d’unité correspondant à l’entrée.
L' `minValue` entrée spécifie ensuite où couper le cercle d’unité.