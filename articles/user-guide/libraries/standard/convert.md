---
title: Conversions de type dans les Q# bibliothèques standard
description: Découvrez les fonctions de conversion de type communes et définies par l’utilisateur dans les Q# bibliothèques standard.
author: cgranade
uid: microsoft.quantum.libraries.convert
ms.author: chgranad
ms.topic: conceptual
no-loc:
- Q#
- $$v
ms.openlocfilehash: 67f47339363a52097f342c8ae4e43a8a93d606a8
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98858022"
---
# <a name="type-conversions"></a>Conversions de type #

Q# est un langage **fortement typé** .
En particulier, Q# ne convertit pas implicitement les types distincts. Par exemple, `1 + 2.0` n’est pas une Q# expression valide.
Au lieu de cela, Q# fournit une variété de fonctions de conversion de type pour construire de nouvelles valeurs d’un type donné.

Par exemple, <xref:Microsoft.Quantum.Core.Length> a un type de sortie de `Int` , donc sa sortie doit d’abord être convertie en un pour qu' `Double` il puisse être utilisé comme une partie d’une expression à virgule flottante.
Cette opération peut être effectuée à l’aide de la <xref:Microsoft.Quantum.Convert.IntAsDouble> fonction :

```qsharp
open Microsoft.Quantum.Convert as Convert;

function HalfLength<'T>(arr : 'T[]) : Double {
    return Convert.IntAsDouble(Length(arr)) / 2.0;
}
```

L' <xref:Microsoft.Quantum.Convert> espace de noms fournit des fonctions de conversion de type communes pour travailler avec les types intégrés de base, tels que,,, `Int` `Double` `BigInt` `Result` et `Bool` :

```qsharp
let bool = Convert.ResultAsBool(One);        // true
let big = Convert.IntAsBigInt(271);          // 271L
let indices = Convert.RangeAsIntArray(0..4); // [0, 1, 2, 3, 4]
```

L' <xref:Microsoft.Quantum.Convert> espace de noms fournit également des conversions plus exotiques, telles que `FunctionAsOperation` , qui convertit les fonctions `'T -> 'U` en nouvelles opérations `'T => 'U` .

Enfin, la Q# bibliothèque standard fournit un certain nombre de types définis par l’utilisateur, tels que <xref:Microsoft.Quantum.Math.Complex> et <xref:Microsoft.Quantum.Arithmetic.LittleEndian> .
Avec ces types, la bibliothèque standard fournit des fonctions telles que <xref:Microsoft.Quantum.Arithmetic.BigEndianAsLittleEndian> :

```qsharp
open Microsoft.Quantum.Arithmetic as Arithmetic;

let register = Arithmetic.BigEndian(qubits);
IncrementByInteger(Arithmetic.BigEndianAsLittleEndian(register));
```
