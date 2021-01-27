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
# <a name="type-conversions"></a><span data-ttu-id="8e8eb-103">Conversions de type</span><span class="sxs-lookup"><span data-stu-id="8e8eb-103">Type Conversions</span></span> #

<span data-ttu-id="8e8eb-104">Q# est un langage **fortement typé** .</span><span class="sxs-lookup"><span data-stu-id="8e8eb-104">Q# is a **strongly-typed** language.</span></span>
<span data-ttu-id="8e8eb-105">En particulier, Q# ne convertit pas implicitement les types distincts.</span><span class="sxs-lookup"><span data-stu-id="8e8eb-105">In particular, Q# does not implicitly cast between distinct types.</span></span> <span data-ttu-id="8e8eb-106">Par exemple, `1 + 2.0` n’est pas une Q# expression valide.</span><span class="sxs-lookup"><span data-stu-id="8e8eb-106">For instance, `1 + 2.0` is not a valid Q# expression.</span></span>
<span data-ttu-id="8e8eb-107">Au lieu de cela, Q# fournit une variété de fonctions de conversion de type pour construire de nouvelles valeurs d’un type donné.</span><span class="sxs-lookup"><span data-stu-id="8e8eb-107">Rather, Q# provides a variety of type conversion functions for constructing new values of a given type.</span></span>

<span data-ttu-id="8e8eb-108">Par exemple, <xref:Microsoft.Quantum.Core.Length> a un type de sortie de `Int` , donc sa sortie doit d’abord être convertie en un pour qu' `Double` il puisse être utilisé comme une partie d’une expression à virgule flottante.</span><span class="sxs-lookup"><span data-stu-id="8e8eb-108">For example, <xref:Microsoft.Quantum.Core.Length> has an output type of `Int`, so its output must first be converted to a `Double` before it can be used as a part of a floating-point expression.</span></span>
<span data-ttu-id="8e8eb-109">Cette opération peut être effectuée à l’aide de la <xref:Microsoft.Quantum.Convert.IntAsDouble> fonction :</span><span class="sxs-lookup"><span data-stu-id="8e8eb-109">This can be done using the <xref:Microsoft.Quantum.Convert.IntAsDouble> function:</span></span>

```qsharp
open Microsoft.Quantum.Convert as Convert;

function HalfLength<'T>(arr : 'T[]) : Double {
    return Convert.IntAsDouble(Length(arr)) / 2.0;
}
```

<span data-ttu-id="8e8eb-110">L' <xref:Microsoft.Quantum.Convert> espace de noms fournit des fonctions de conversion de type communes pour travailler avec les types intégrés de base, tels que,,, `Int` `Double` `BigInt` `Result` et `Bool` :</span><span class="sxs-lookup"><span data-stu-id="8e8eb-110">The <xref:Microsoft.Quantum.Convert> namespace provides common type conversion functions for working with the basic built-in types, such as `Int`, `Double`, `BigInt`, `Result`, and `Bool`:</span></span>

```qsharp
let bool = Convert.ResultAsBool(One);        // true
let big = Convert.IntAsBigInt(271);          // 271L
let indices = Convert.RangeAsIntArray(0..4); // [0, 1, 2, 3, 4]
```

<span data-ttu-id="8e8eb-111">L' <xref:Microsoft.Quantum.Convert> espace de noms fournit également des conversions plus exotiques, telles que `FunctionAsOperation` , qui convertit les fonctions `'T -> 'U` en nouvelles opérations `'T => 'U` .</span><span class="sxs-lookup"><span data-stu-id="8e8eb-111">The <xref:Microsoft.Quantum.Convert> namespace also provides some more exotic conversions, such as `FunctionAsOperation`, which converts functions `'T -> 'U` into new operations `'T => 'U`.</span></span>

<span data-ttu-id="8e8eb-112">Enfin, la Q# bibliothèque standard fournit un certain nombre de types définis par l’utilisateur, tels que <xref:Microsoft.Quantum.Math.Complex> et <xref:Microsoft.Quantum.Arithmetic.LittleEndian> .</span><span class="sxs-lookup"><span data-stu-id="8e8eb-112">Finally, the Q# standard library provides a number of user-defined types such as <xref:Microsoft.Quantum.Math.Complex> and <xref:Microsoft.Quantum.Arithmetic.LittleEndian>.</span></span>
<span data-ttu-id="8e8eb-113">Avec ces types, la bibliothèque standard fournit des fonctions telles que <xref:Microsoft.Quantum.Arithmetic.BigEndianAsLittleEndian> :</span><span class="sxs-lookup"><span data-stu-id="8e8eb-113">Along with these types, the standard library provides functions such as <xref:Microsoft.Quantum.Arithmetic.BigEndianAsLittleEndian>:</span></span>

```qsharp
open Microsoft.Quantum.Arithmetic as Arithmetic;

let register = Arithmetic.BigEndian(qubits);
IncrementByInteger(Arithmetic.BigEndianAsLittleEndian(register));
```
