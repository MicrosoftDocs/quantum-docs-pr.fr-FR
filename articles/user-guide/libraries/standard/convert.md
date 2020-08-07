---
title: Conversions de type dans les Q# bibliothèques standard
description: Découvrez les fonctions de conversion de type communes et définies par l’utilisateur dans les Q# bibliothèques standard.
author: cgranade
uid: microsoft.quantum.libraries.convert
ms.author: chgranad@microsoft.com
ms.topic: article
no-loc:
- Q#
- $$v
ms.openlocfilehash: 2319bf453f5fbf6bd068859ea65562423d3ff4d0
ms.sourcegitcommit: 6bf99d93590d6aa80490e88f2fd74dbbee8e0371
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/06/2020
ms.locfileid: "87868509"
---
# <a name="type-conversions"></a>Conversions de type #

Q#est un langage **fortement typé** .
En particulier, Q# ne convertit pas implicitement les types distincts. Par exemple, `1 + 2.0` n’est pas une Q# expression valide.
Au lieu de cela, Q# fournit une variété de fonctions de conversion de type pour construire de nouvelles valeurs d’un type donné.

Par exemple, <xref:microsoft.quantum.core.length> a un type de sortie de `Int` , donc sa sortie doit d’abord être convertie en un pour qu' `Double` il puisse être utilisé comme une partie d’une expression à virgule flottante.
Cette opération peut être effectuée à l’aide de la <xref:microsoft.quantum.convert.intasdouble> fonction :

```qsharp
open Microsoft.Quantum.Convert as Convert;

function HalfLength<'T>(arr : 'T[]) : Double {
    return Convert.IntAsDouble(Length(arr)) / 2.0;
}
```

L' <xref:microsoft.quantum.convert> espace de noms fournit des fonctions de conversion de type communes pour travailler avec les types intégrés de base, tels que,,, `Int` `Double` `BigInt` `Result` et `Bool` :

```qsharp
let bool = Convert.ResultAsBool(One);        // true
let big = Convert.IntAsBigInt(271);          // 271L
let indices = Convert.RangeAsIntArray(0..4); // [0, 1, 2, 3, 4]
```

L' <xref:microsoft.quantum.convert> espace de noms fournit également des conversions plus exotiques, telles que `FunctionAsOperation` , qui convertit les fonctions `'T -> 'U` en nouvelles opérations `'T => 'U` .

Enfin, la Q# bibliothèque standard fournit un certain nombre de types définis par l’utilisateur, tels que <xref:microsoft.quantum.math.complex> et <xref:microsoft.quantum.arithmetic.littleendian> .
Avec ces types, la bibliothèque standard fournit des fonctions telles que <xref:microsoft.quantum.arithmetic.bigendianaslittleendian> :

```Q#
open Microsoft.Quantum.Arithmetic as Arithmetic;

let register = Arithmetic.BigEndian(qubits);
IncrementByInteger(Arithmetic.BigEndianAsLittleEndian(register));
```
