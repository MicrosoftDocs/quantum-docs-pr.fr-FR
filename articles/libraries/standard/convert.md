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
# <a name="type-conversions"></a><span data-ttu-id="711f1-103">Conversions de type</span><span class="sxs-lookup"><span data-stu-id="711f1-103">Type Conversions</span></span> #

<span data-ttu-id="711f1-104">Q # est un langage **fortement typé** .</span><span class="sxs-lookup"><span data-stu-id="711f1-104">Q# is a **strongly-typed** language.</span></span>
<span data-ttu-id="711f1-105">En particulier, Q # ne convertit pas implicitement les types distincts.</span><span class="sxs-lookup"><span data-stu-id="711f1-105">In particular, Q# does not implicitly cast between distinct types.</span></span> <span data-ttu-id="711f1-106">Par exemple, `1 + 2.0` n’est pas une expression Q # valide.</span><span class="sxs-lookup"><span data-stu-id="711f1-106">For instance, `1 + 2.0` is not a valid Q# expression.</span></span>
<span data-ttu-id="711f1-107">Au lieu de cela, Q # fournit une variété de fonctions de conversion de type pour construire de nouvelles valeurs d’un type donné.</span><span class="sxs-lookup"><span data-stu-id="711f1-107">Rather, Q# provides a variety of type conversion functions for constructing new values of a given type.</span></span>

<span data-ttu-id="711f1-108">Par exemple, <xref:microsoft.quantum.core.length> a un type de sortie `Int`, sa sortie doit d’abord être convertie en `Double` avant de pouvoir être utilisée dans le cadre d’une expression à virgule flottante.</span><span class="sxs-lookup"><span data-stu-id="711f1-108">For example, <xref:microsoft.quantum.core.length> has an output type of `Int`, so its output must first be converted to a `Double` before it can be used as a part of a floating-point expression.</span></span>
<span data-ttu-id="711f1-109">Cette opération peut être effectuée à l’aide de la fonction <xref:microsoft.quantum.convert.intasdouble> :</span><span class="sxs-lookup"><span data-stu-id="711f1-109">This can be done using the <xref:microsoft.quantum.convert.intasdouble> function:</span></span>

```qsharp
open Microsoft.Quantum.Convert as Convert;

function HalfLength<'T>(arr : 'T[]) : Double {
    return Convert.IntAsDouble(Length(arr)) / 2.0;
}
```

<span data-ttu-id="711f1-110">L’espace de noms <xref:microsoft.quantum.convert> fournit des fonctions de conversion de type communes pour travailler avec les types intégrés de base, comme `Int`, `Double`, `BigInt`, `Result`et `Bool`:</span><span class="sxs-lookup"><span data-stu-id="711f1-110">The <xref:microsoft.quantum.convert> namespace provides common type conversion functions for working with the basic built-in types, such as `Int`, `Double`, `BigInt`, `Result`, and `Bool`:</span></span>

```qsharp
let bool = Convert.ResultAsBool(One);        // true
let big = Convert.IntAsBigInt(271);          // 271L
let indices = Convert.RangeAsIntArray(0..4); // [0, 1, 2, 3, 4]
```

<span data-ttu-id="711f1-111">L’espace de noms <xref:microsoft.quantum.convert> fournit également des conversions plus exotiques, telles que `FunctionAsOperation`, qui convertit les fonctions `'T -> 'U` en nouvelles opérations `'T => 'U`.</span><span class="sxs-lookup"><span data-stu-id="711f1-111">The <xref:microsoft.quantum.convert> namespace also provides some more exotic conversions, such as `FunctionAsOperation`, which converts functions `'T -> 'U` into new operations `'T => 'U`.</span></span>

<span data-ttu-id="711f1-112">Enfin, la bibliothèque standard Q # fournit un certain nombre de types définis par l’utilisateur, tels que <xref:microsoft.quantum.math.complex> et <xref:microsoft.quantum.arithmetic.littleendian>.</span><span class="sxs-lookup"><span data-stu-id="711f1-112">Finally, the Q# standard library provides a number of user-defined types such as <xref:microsoft.quantum.math.complex> and <xref:microsoft.quantum.arithmetic.littleendian>.</span></span>
<span data-ttu-id="711f1-113">Avec ces types, la bibliothèque standard fournit des fonctions telles que <xref:microsoft.quantum.arithmetic.bigendianaslittleendian>:</span><span class="sxs-lookup"><span data-stu-id="711f1-113">Along with these types, the standard library provides functions such as <xref:microsoft.quantum.arithmetic.bigendianaslittleendian>:</span></span>

```Q#
open Microsoft.Quantum.Arithmetic as Arithmetic;

let register = Arithmetic.BigEndian(qubits);
IncrementByInteger(Arithmetic.BigEndianAsLittleEndian(register));
```
