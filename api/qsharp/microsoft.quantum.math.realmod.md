---
uid: Microsoft.Quantum.Math.RealMod
title: RealMod fonction)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: RealMod
qsharp.summary: Computes the modulus between two real numbers.
ms.openlocfilehash: 20916d8462288395384aa875bfae4f042ba6b6ad
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96228251"
---
# <a name="realmod-function"></a>RealMod fonction)

Espace de noms : [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)

Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


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