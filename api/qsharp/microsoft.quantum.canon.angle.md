---
uid: Microsoft.Quantum.Canon.Angle
title: Fonction angle
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Angle
qsharp.summary: Returns 1, if `index` has an odd number of 1s and -1, if `index` has an even number of 1s.
ms.openlocfilehash: da3ecdaf1b2c88180bd2a660fac0b6e87b2cafa1
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92705523"
---
# <a name="angle-function"></a><span data-ttu-id="c3561-102">Fonction angle</span><span class="sxs-lookup"><span data-stu-id="c3561-102">Angle function</span></span>

<span data-ttu-id="c3561-103">Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="c3561-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="c3561-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="c3561-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="c3561-105">Retourne 1, si `index` a un nombre impair de 1s et-1, si `index` a un nombre pair de 1s.</span><span class="sxs-lookup"><span data-stu-id="c3561-105">Returns 1, if `index` has an odd number of 1s and -1, if `index` has an even number of 1s.</span></span>

```qsharp
function Angle (index : Int) : Int
```


## <a name="description"></a><span data-ttu-id="c3561-106">Description</span><span class="sxs-lookup"><span data-stu-id="c3561-106">Description</span></span>

<span data-ttu-id="c3561-107">La valeur correspond au signe du coefficient du spectre Rademacher-Walsh de la variable n et de la fonction pour une affectation donnée qui détermine l’angle de la rotation.</span><span class="sxs-lookup"><span data-stu-id="c3561-107">Value corresponds to the sign of the coefficient of the Rademacher-Walsh spectrum of the n-variable AND function for a given assignment that decides the angle of the rotation.</span></span>

## <a name="input"></a><span data-ttu-id="c3561-108">Entrée</span><span class="sxs-lookup"><span data-stu-id="c3561-108">Input</span></span>

### <a name="index--int"></a><span data-ttu-id="c3561-109">index : [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="c3561-109">index : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="c3561-110">Assignation d’entrée en tant qu’entier (de 0 à 2 ^ n-1)</span><span class="sxs-lookup"><span data-stu-id="c3561-110">Input assignment as integer (from 0 to 2^n - 1)</span></span>



## <a name="output--int"></a><span data-ttu-id="c3561-111">Sortie : [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="c3561-111">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

