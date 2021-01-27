---
uid: Microsoft.Quantum.Math.RealMod
title: RealMod fonction)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: RealMod
qsharp.summary: Computes the modulus between two real numbers.
ms.openlocfilehash: 56da313fabb20655ec358120b8d9b435e4971159
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848346"
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



## <a name="example"></a>Exemple

```qsharp
    // Returns 3 π / 2.
    let y = RealMod(5.5 * PI(), 2.0 * PI(), 0.0);
    // Returns -1.2, since +3.6 and -1.2 are 4.8 apart on the real line,
    // which is a multiple of 2.4.
    let z = RealMod(3.6, 2.4, -1.2);
```

## <a name="remarks"></a>Notes

Cette fonction calcule le modulo réel en encapsulant la ligne réelle sur le cercle d’unité, puis en recherchant l’angle sur le cercle d’unité correspondant à l’entrée.
L' `minValue` entrée spécifie ensuite où couper le cercle d’unité.