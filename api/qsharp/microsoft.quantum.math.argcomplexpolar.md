---
uid: Microsoft.Quantum.Math.ArgComplexPolar
title: ArgComplexPolar fonction)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ArgComplexPolar
qsharp.summary: Returns the phase of a complex number of type `ComplexPolar`.
ms.openlocfilehash: 5809b5463e6bf8ee73d095dfe4eafedfbb5e0702
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98852902"
---
# <a name="argcomplexpolar-function"></a><span data-ttu-id="a6ce0-102">ArgComplexPolar fonction)</span><span class="sxs-lookup"><span data-stu-id="a6ce0-102">ArgComplexPolar function</span></span>

<span data-ttu-id="a6ce0-103">Espace de noms : [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="a6ce0-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="a6ce0-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="a6ce0-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="a6ce0-105">Retourne la phase d’un nombre complexe de type `ComplexPolar` .</span><span class="sxs-lookup"><span data-stu-id="a6ce0-105">Returns the phase of a complex number of type `ComplexPolar`.</span></span>

```qsharp
function ArgComplexPolar (input : Microsoft.Quantum.Math.ComplexPolar) : Double
```


## <a name="input"></a><span data-ttu-id="a6ce0-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="a6ce0-106">Input</span></span>

### <a name="input--complexpolar"></a><span data-ttu-id="a6ce0-107">entrée : [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span><span class="sxs-lookup"><span data-stu-id="a6ce0-107">input : [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span></span>

<span data-ttu-id="a6ce0-108">Nombre complexe $c = r e ^ {i t} $.</span><span class="sxs-lookup"><span data-stu-id="a6ce0-108">Complex number $c = r e^{i t}$.</span></span>



## <a name="output--double"></a><span data-ttu-id="a6ce0-109">Sortie : [double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="a6ce0-109">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="a6ce0-110">Phase $ \text{Arg} [c] = t $.</span><span class="sxs-lookup"><span data-stu-id="a6ce0-110">Phase $\text{Arg}[c] = t$.</span></span>