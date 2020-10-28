---
title: 'Conversions de type dans les :::no-loc(Q#)::: bibliothèques standard'
description: 'Découvrez les fonctions de conversion de type communes et définies par l’utilisateur dans les :::no-loc(Q#)::: bibliothèques standard.'
author: cgranade
uid: microsoft.quantum.libraries.convert
ms.author: chgranad
ms.topic: article
no-loc:
- ':::no-loc(Q#):::'
- ':::no-loc($$v):::'
ms.openlocfilehash: 9ec3a2ecd2aa59a10a7033e7b3067eb147ce4035
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92691107"
---
# <a name="type-conversions"></a><span data-ttu-id="cb999-103">Conversions de type</span><span class="sxs-lookup"><span data-stu-id="cb999-103">Type Conversions</span></span> #

<span data-ttu-id="cb999-104">:::no-loc(Q#)::: est un langage **fortement typé** .</span><span class="sxs-lookup"><span data-stu-id="cb999-104">:::no-loc(Q#)::: is a **strongly-typed** language.</span></span>
<span data-ttu-id="cb999-105">En particulier, :::no-loc(Q#)::: ne convertit pas implicitement les types distincts.</span><span class="sxs-lookup"><span data-stu-id="cb999-105">In particular, :::no-loc(Q#)::: does not implicitly cast between distinct types.</span></span> <span data-ttu-id="cb999-106">Par exemple, `1 + 2.0` n’est pas une :::no-loc(Q#)::: expression valide.</span><span class="sxs-lookup"><span data-stu-id="cb999-106">For instance, `1 + 2.0` is not a valid :::no-loc(Q#)::: expression.</span></span>
<span data-ttu-id="cb999-107">Au lieu de cela, :::no-loc(Q#)::: fournit une variété de fonctions de conversion de type pour construire de nouvelles valeurs d’un type donné.</span><span class="sxs-lookup"><span data-stu-id="cb999-107">Rather, :::no-loc(Q#)::: provides a variety of type conversion functions for constructing new values of a given type.</span></span>

<span data-ttu-id="cb999-108">Par exemple, <xref:Microsoft.Quantum.Core.Length> a un type de sortie de `Int` , donc sa sortie doit d’abord être convertie en un pour qu' `Double` il puisse être utilisé comme une partie d’une expression à virgule flottante.</span><span class="sxs-lookup"><span data-stu-id="cb999-108">For example, <xref:Microsoft.Quantum.Core.Length> has an output type of `Int`, so its output must first be converted to a `Double` before it can be used as a part of a floating-point expression.</span></span>
<span data-ttu-id="cb999-109">Cette opération peut être effectuée à l’aide de la <xref:Microsoft.Quantum.Convert.IntAsDouble> fonction :</span><span class="sxs-lookup"><span data-stu-id="cb999-109">This can be done using the <xref:Microsoft.Quantum.Convert.IntAsDouble> function:</span></span>

```qsharp
open Microsoft.Quantum.Convert as Convert;

function HalfLength<'T>(arr : 'T[]) : Double {
    return Convert.IntAsDouble(Length(arr)) / 2.0;
}
```

<span data-ttu-id="cb999-110">L' <xref:Microsoft.Quantum.Convert> espace de noms fournit des fonctions de conversion de type communes pour travailler avec les types intégrés de base, tels que,,, `Int` `Double` `BigInt` `Result` et `Bool` :</span><span class="sxs-lookup"><span data-stu-id="cb999-110">The <xref:Microsoft.Quantum.Convert> namespace provides common type conversion functions for working with the basic built-in types, such as `Int`, `Double`, `BigInt`, `Result`, and `Bool`:</span></span>

```qsharp
let bool = Convert.ResultAsBool(One);        // true
let big = Convert.IntAsBigInt(271);          // 271L
let indices = Convert.RangeAsIntArray(0..4); // [0, 1, 2, 3, 4]
```

<span data-ttu-id="cb999-111">L' <xref:Microsoft.Quantum.Convert> espace de noms fournit également des conversions plus exotiques, telles que `FunctionAsOperation` , qui convertit les fonctions `'T -> 'U` en nouvelles opérations `'T => 'U` .</span><span class="sxs-lookup"><span data-stu-id="cb999-111">The <xref:Microsoft.Quantum.Convert> namespace also provides some more exotic conversions, such as `FunctionAsOperation`, which converts functions `'T -> 'U` into new operations `'T => 'U`.</span></span>

<span data-ttu-id="cb999-112">Enfin, la :::no-loc(Q#)::: bibliothèque standard fournit un certain nombre de types définis par l’utilisateur, tels que <xref:Microsoft.Quantum.Math.Complex> et <xref:Microsoft.Quantum.Arithmetic.LittleEndian> .</span><span class="sxs-lookup"><span data-stu-id="cb999-112">Finally, the :::no-loc(Q#)::: standard library provides a number of user-defined types such as <xref:Microsoft.Quantum.Math.Complex> and <xref:Microsoft.Quantum.Arithmetic.LittleEndian>.</span></span>
<span data-ttu-id="cb999-113">Avec ces types, la bibliothèque standard fournit des fonctions telles que <xref:Microsoft.Quantum.Arithmetic.BigEndianAsLittleEndian> :</span><span class="sxs-lookup"><span data-stu-id="cb999-113">Along with these types, the standard library provides functions such as <xref:Microsoft.Quantum.Arithmetic.BigEndianAsLittleEndian>:</span></span>

```:::no-loc(Q#):::
open Microsoft.Quantum.Arithmetic as Arithmetic;

let register = Arithmetic.BigEndian(qubits);
IncrementByInteger(Arithmetic.BigEndianAsLittleEndian(register));
```
