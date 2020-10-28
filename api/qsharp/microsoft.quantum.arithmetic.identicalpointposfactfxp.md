---
uid: Microsoft.Quantum.Arithmetic.IdenticalPointPosFactFxP
title: IdenticalPointPosFactFxP fonction)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: IdenticalPointPosFactFxP
qsharp.summary: Assert that all fixed-point numbers in the provided array have identical point positions when counting from the least- significant bit. I.e., number of bits minus point position must be constant for all fixed-point numbers in the array.
ms.openlocfilehash: 0b285ce980ca1abbc3eb20838389a6f49835e742
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92707275"
---
# <a name="identicalpointposfactfxp-function"></a><span data-ttu-id="1e5c8-102">IdenticalPointPosFactFxP fonction)</span><span class="sxs-lookup"><span data-stu-id="1e5c8-102">IdenticalPointPosFactFxP function</span></span>

<span data-ttu-id="1e5c8-103">Espace de noms : [Microsoft. Quantum. Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="1e5c8-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="1e5c8-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="1e5c8-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="1e5c8-105">Déclarez que tous les nombres à virgule fixe dans le tableau fourni ont des positions de point identiques lors du comptage à partir du bit de poids faible.</span><span class="sxs-lookup"><span data-stu-id="1e5c8-105">Assert that all fixed-point numbers in the provided array have identical point positions when counting from the least- significant bit.</span></span> <span data-ttu-id="1e5c8-106">Par exemple, le nombre de bits moins la position du point doit être constant pour tous les nombres à virgule fixe dans le tableau.</span><span class="sxs-lookup"><span data-stu-id="1e5c8-106">I.e., number of bits minus point position must be constant for all fixed-point numbers in the array.</span></span>

```qsharp
function IdenticalPointPosFactFxP (fixedPoints : Microsoft.Quantum.Arithmetic.FixedPoint[]) : Unit
```


## <a name="input"></a><span data-ttu-id="1e5c8-107">Entrée</span><span class="sxs-lookup"><span data-stu-id="1e5c8-107">Input</span></span>

### <a name="fixedpoints--fixedpoint"></a><span data-ttu-id="1e5c8-108">fixedPoints : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)[]</span><span class="sxs-lookup"><span data-stu-id="1e5c8-108">fixedPoints : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)[]</span></span>

<span data-ttu-id="1e5c8-109">Tableau de nombres à virgule fixe Quantum dont la compatibilité est vérifiée (à l’aide d’assertions).</span><span class="sxs-lookup"><span data-stu-id="1e5c8-109">Array of quantum fixed-point numbers that will be checked for compatibility (using assertions).</span></span>



## <a name="output--unit"></a><span data-ttu-id="1e5c8-110">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="1e5c8-110">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

