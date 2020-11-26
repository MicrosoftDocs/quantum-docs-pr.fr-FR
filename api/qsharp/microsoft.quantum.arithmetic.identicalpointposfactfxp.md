---
uid: Microsoft.Quantum.Arithmetic.IdenticalPointPosFactFxP
title: IdenticalPointPosFactFxP fonction)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: IdenticalPointPosFactFxP
qsharp.summary: Assert that all fixed-point numbers in the provided array have identical point positions when counting from the least- significant bit. I.e., number of bits minus point position must be constant for all fixed-point numbers in the array.
ms.openlocfilehash: 907e270e1c3710fb346044ad7757171c6d5f568d
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96223049"
---
# <a name="identicalpointposfactfxp-function"></a><span data-ttu-id="cb4fa-102">IdenticalPointPosFactFxP fonction)</span><span class="sxs-lookup"><span data-stu-id="cb4fa-102">IdenticalPointPosFactFxP function</span></span>

<span data-ttu-id="cb4fa-103">Espace de noms : [Microsoft. Quantum. Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="cb4fa-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="cb4fa-104">Package : [Microsoft. Quantum. Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span><span class="sxs-lookup"><span data-stu-id="cb4fa-104">Package: [Microsoft.Quantum.Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span></span>


<span data-ttu-id="cb4fa-105">Déclarez que tous les nombres à virgule fixe dans le tableau fourni ont des positions de point identiques lors du comptage à partir du bit de poids faible.</span><span class="sxs-lookup"><span data-stu-id="cb4fa-105">Assert that all fixed-point numbers in the provided array have identical point positions when counting from the least- significant bit.</span></span> <span data-ttu-id="cb4fa-106">Par exemple, le nombre de bits moins la position du point doit être constant pour tous les nombres à virgule fixe dans le tableau.</span><span class="sxs-lookup"><span data-stu-id="cb4fa-106">I.e., number of bits minus point position must be constant for all fixed-point numbers in the array.</span></span>

```qsharp
function IdenticalPointPosFactFxP (fixedPoints : Microsoft.Quantum.Arithmetic.FixedPoint[]) : Unit
```


## <a name="input"></a><span data-ttu-id="cb4fa-107">Entrée</span><span class="sxs-lookup"><span data-stu-id="cb4fa-107">Input</span></span>

### <a name="fixedpoints--fixedpoint"></a><span data-ttu-id="cb4fa-108">fixedPoints : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)[]</span><span class="sxs-lookup"><span data-stu-id="cb4fa-108">fixedPoints : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)[]</span></span>

<span data-ttu-id="cb4fa-109">Tableau de nombres à virgule fixe Quantum dont la compatibilité est vérifiée (à l’aide d’assertions).</span><span class="sxs-lookup"><span data-stu-id="cb4fa-109">Array of quantum fixed-point numbers that will be checked for compatibility (using assertions).</span></span>



## <a name="output--unit"></a><span data-ttu-id="cb4fa-110">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="cb4fa-110">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

