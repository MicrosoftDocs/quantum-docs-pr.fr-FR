---
title: 'Q # bibliothèques standard-conversions de type | Microsoft Docs'
description: 'Q # bibliothèques standard-conversions de type'
author: cgranade
uid: microsoft.quantum.libraries.convert
ms.author: chgranad@microsoft.com
ms.topic: article
ms.openlocfilehash: 4716f0d9562229f08ef6f0f5f80961f793de4c5c
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2019
ms.locfileid: "73184472"
---
# <a name="type-conversions"></a>Conversions de type #

Q # est un langage **fortement typé** .
En particulier, Q # ne convertit pas implicitement les types distincts. Par exemple, `1 + 2.0` n’est pas une expression Q # valide.
Au lieu de cela, Q # fournit une variété de fonctions de conversion de type pour construire de nouvelles valeurs d’un type donné.

Par exemple, <xref:microsoft.quantum.core.length> a un type de sortie `Int`, sa sortie doit d’abord être convertie en `Double` avant de pouvoir être utilisée dans le cadre d’une expression à virgule flottante.
Cette opération peut être effectuée à l’aide de la fonction <xref:microsoft.quantum.convert.intasdouble> :

```qsharp
open Microsoft.Quantum.Convert as Convert;

function HalfLength<'T>(arr : 'T[]) : Double {
    return Convert.IntAsDouble(Length(arr)) / 2.0;
}
```

L’espace de noms <xref:microsoft.quantum.convert> fournit des fonctions de conversion de type communes pour travailler avec les types intégrés de base, comme `Int`, `Double`, `BigInt`, `Result`et `Bool`:

```qsharp
let bool = Convert.ResultAsBool(One);        // true
let big = Convert.IntAsBigInt(271);          // 271L
let indices = Convert.RangeAsIntArray(0..4); // [0, 1, 2, 3, 4]
```

L’espace de noms <xref:microsoft.quantum.convert> fournit également des conversions plus exotiques, telles que `FunctionAsOperation`, qui convertit les fonctions `'T -> 'U` en nouvelles opérations `'T => 'U`.

Enfin, la bibliothèque standard Q # fournit un certain nombre de types définis par l’utilisateur, tels que <xref:microsoft.quantum.math.complex> et <xref:microsoft.quantum.arithmetic.littleendian>.
Avec ces types, la bibliothèque standard fournit des fonctions telles que <xref:microsoft.quantum.arithmetic.bigendianaslittleendian>:

```Q#
open Microsoft.Quantum.Arithmetic as Arithmetic;

let register = Arithmetic.BigEndian(qubits);
IncrementByInteger(Arithmetic.BigEndianAsLittleEndian(register));
```
