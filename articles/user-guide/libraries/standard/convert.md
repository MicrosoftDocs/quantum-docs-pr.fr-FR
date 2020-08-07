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
# <a name="type-conversions"></a><span data-ttu-id="f4523-103">Conversions de type</span><span class="sxs-lookup"><span data-stu-id="f4523-103">Type Conversions</span></span> #

<span data-ttu-id="f4523-104">Q#est un langage **fortement typé** .</span><span class="sxs-lookup"><span data-stu-id="f4523-104">Q# is a **strongly-typed** language.</span></span>
<span data-ttu-id="f4523-105">En particulier, Q# ne convertit pas implicitement les types distincts.</span><span class="sxs-lookup"><span data-stu-id="f4523-105">In particular, Q# does not implicitly cast between distinct types.</span></span> <span data-ttu-id="f4523-106">Par exemple, `1 + 2.0` n’est pas une Q# expression valide.</span><span class="sxs-lookup"><span data-stu-id="f4523-106">For instance, `1 + 2.0` is not a valid Q# expression.</span></span>
<span data-ttu-id="f4523-107">Au lieu de cela, Q# fournit une variété de fonctions de conversion de type pour construire de nouvelles valeurs d’un type donné.</span><span class="sxs-lookup"><span data-stu-id="f4523-107">Rather, Q# provides a variety of type conversion functions for constructing new values of a given type.</span></span>

<span data-ttu-id="f4523-108">Par exemple, <xref:microsoft.quantum.core.length> a un type de sortie de `Int` , donc sa sortie doit d’abord être convertie en un pour qu' `Double` il puisse être utilisé comme une partie d’une expression à virgule flottante.</span><span class="sxs-lookup"><span data-stu-id="f4523-108">For example, <xref:microsoft.quantum.core.length> has an output type of `Int`, so its output must first be converted to a `Double` before it can be used as a part of a floating-point expression.</span></span>
<span data-ttu-id="f4523-109">Cette opération peut être effectuée à l’aide de la <xref:microsoft.quantum.convert.intasdouble> fonction :</span><span class="sxs-lookup"><span data-stu-id="f4523-109">This can be done using the <xref:microsoft.quantum.convert.intasdouble> function:</span></span>

```qsharp
open Microsoft.Quantum.Convert as Convert;

function HalfLength<'T>(arr : 'T[]) : Double {
    return Convert.IntAsDouble(Length(arr)) / 2.0;
}
```

<span data-ttu-id="f4523-110">L' <xref:microsoft.quantum.convert> espace de noms fournit des fonctions de conversion de type communes pour travailler avec les types intégrés de base, tels que,,, `Int` `Double` `BigInt` `Result` et `Bool` :</span><span class="sxs-lookup"><span data-stu-id="f4523-110">The <xref:microsoft.quantum.convert> namespace provides common type conversion functions for working with the basic built-in types, such as `Int`, `Double`, `BigInt`, `Result`, and `Bool`:</span></span>

```qsharp
let bool = Convert.ResultAsBool(One);        // true
let big = Convert.IntAsBigInt(271);          // 271L
let indices = Convert.RangeAsIntArray(0..4); // [0, 1, 2, 3, 4]
```

<span data-ttu-id="f4523-111">L' <xref:microsoft.quantum.convert> espace de noms fournit également des conversions plus exotiques, telles que `FunctionAsOperation` , qui convertit les fonctions `'T -> 'U` en nouvelles opérations `'T => 'U` .</span><span class="sxs-lookup"><span data-stu-id="f4523-111">The <xref:microsoft.quantum.convert> namespace also provides some more exotic conversions, such as `FunctionAsOperation`, which converts functions `'T -> 'U` into new operations `'T => 'U`.</span></span>

<span data-ttu-id="f4523-112">Enfin, la Q# bibliothèque standard fournit un certain nombre de types définis par l’utilisateur, tels que <xref:microsoft.quantum.math.complex> et <xref:microsoft.quantum.arithmetic.littleendian> .</span><span class="sxs-lookup"><span data-stu-id="f4523-112">Finally, the Q# standard library provides a number of user-defined types such as <xref:microsoft.quantum.math.complex> and <xref:microsoft.quantum.arithmetic.littleendian>.</span></span>
<span data-ttu-id="f4523-113">Avec ces types, la bibliothèque standard fournit des fonctions telles que <xref:microsoft.quantum.arithmetic.bigendianaslittleendian> :</span><span class="sxs-lookup"><span data-stu-id="f4523-113">Along with these types, the standard library provides functions such as <xref:microsoft.quantum.arithmetic.bigendianaslittleendian>:</span></span>

```Q#
open Microsoft.Quantum.Arithmetic as Arithmetic;

let register = Arithmetic.BigEndian(qubits);
IncrementByInteger(Arithmetic.BigEndianAsLittleEndian(register));
```
