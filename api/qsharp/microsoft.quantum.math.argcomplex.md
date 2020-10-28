---
uid: Microsoft.Quantum.Math.ArgComplex
title: ArgComplex fonction)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ArgComplex
qsharp.summary: Returns the phase of a complex number of type `Complex`.
ms.openlocfilehash: 629aa32ad80e5aa3d6f5ff75ac65df9b1a96fc15
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92708336"
---
# <a name="argcomplex-function"></a><span data-ttu-id="cb83c-102">ArgComplex fonction)</span><span class="sxs-lookup"><span data-stu-id="cb83c-102">ArgComplex function</span></span>

<span data-ttu-id="cb83c-103">Espace de noms : [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="cb83c-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="cb83c-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="cb83c-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="cb83c-105">Retourne la phase d’un nombre complexe de type `Complex` .</span><span class="sxs-lookup"><span data-stu-id="cb83c-105">Returns the phase of a complex number of type `Complex`.</span></span>

```qsharp
function ArgComplex (input : Microsoft.Quantum.Math.Complex) : Double
```


## <a name="input"></a><span data-ttu-id="cb83c-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="cb83c-106">Input</span></span>

### <a name="input--complex"></a><span data-ttu-id="cb83c-107">entrée : [complexe](xref:Microsoft.Quantum.Math.Complex)</span><span class="sxs-lookup"><span data-stu-id="cb83c-107">input : [Complex](xref:Microsoft.Quantum.Math.Complex)</span></span>

<span data-ttu-id="cb83c-108">Nombre complexe $c = x + i y $.</span><span class="sxs-lookup"><span data-stu-id="cb83c-108">Complex number $c = x + i y$.</span></span>



## <a name="output--double"></a><span data-ttu-id="cb83c-109">Sortie : [double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="cb83c-109">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="cb83c-110">Phase $ \text{Arg} [c] = \text{ArcTan} (y, x) \Dans (-\pi, \pi] $.</span><span class="sxs-lookup"><span data-stu-id="cb83c-110">Phase $\text{Arg}[c] = \text{ArcTan}(y,x) \in (-\pi,\pi]$.</span></span>