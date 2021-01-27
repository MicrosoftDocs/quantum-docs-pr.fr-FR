---
uid: Microsoft.Quantum.Random.DrawRandomInt
title: Opération DrawRandomInt
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: DrawRandomInt
qsharp.summary: Draws a random integer in a given inclusive range.
ms.openlocfilehash: ebed7f52b7c4a8c538ed9d718c486b5aa94a0327
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98851139"
---
# <a name="drawrandomint-operation"></a><span data-ttu-id="ecaa0-102">Opération DrawRandomInt</span><span class="sxs-lookup"><span data-stu-id="ecaa0-102">DrawRandomInt operation</span></span>

<span data-ttu-id="ecaa0-103">Espace de noms : [Microsoft. Quantum. Random](xref:Microsoft.Quantum.Random)</span><span class="sxs-lookup"><span data-stu-id="ecaa0-103">Namespace: [Microsoft.Quantum.Random](xref:Microsoft.Quantum.Random)</span></span>

<span data-ttu-id="ecaa0-104">Package : [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="ecaa0-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="ecaa0-105">Dessine un entier aléatoire dans une plage inclusive donnée.</span><span class="sxs-lookup"><span data-stu-id="ecaa0-105">Draws a random integer in a given inclusive range.</span></span>

```qsharp
operation DrawRandomInt (min : Int, max : Int) : Int
```


## <a name="input"></a><span data-ttu-id="ecaa0-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="ecaa0-106">Input</span></span>

### <a name="min--int"></a><span data-ttu-id="ecaa0-107">min : [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="ecaa0-107">min : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="ecaa0-108">Plus petit entier à dessiner.</span><span class="sxs-lookup"><span data-stu-id="ecaa0-108">The smallest integer to be drawn.</span></span>


### <a name="max--int"></a><span data-ttu-id="ecaa0-109">Max : [entier](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="ecaa0-109">max : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="ecaa0-110">Plus grand entier à dessiner.</span><span class="sxs-lookup"><span data-stu-id="ecaa0-110">The largest integer to be drawn.</span></span>



## <a name="output--int"></a><span data-ttu-id="ecaa0-111">Sortie : [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="ecaa0-111">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="ecaa0-112">Entier dans la plage inclusive comprise entre `min` et `max` avec une probabilité uniforme.</span><span class="sxs-lookup"><span data-stu-id="ecaa0-112">An integer in the inclusive range from `min` to `max` with uniform probability.</span></span>

## <a name="example"></a><span data-ttu-id="ecaa0-113">Exemple</span><span class="sxs-lookup"><span data-stu-id="ecaa0-113">Example</span></span>

<span data-ttu-id="ecaa0-114">L’extrait de code Q # suivant remplace de manière aléatoire un dé à six côtés :</span><span class="sxs-lookup"><span data-stu-id="ecaa0-114">The following Q# snippet randomly rolls a six-sided die:</span></span>

```qsharp
let roll = DrawRandomInt(1, 6);
```

## <a name="remarks"></a><span data-ttu-id="ecaa0-115">Notes</span><span class="sxs-lookup"><span data-stu-id="ecaa0-115">Remarks</span></span>

<span data-ttu-id="ecaa0-116">Échoue si `max <= min` .</span><span class="sxs-lookup"><span data-stu-id="ecaa0-116">Fails if `max <= min`.</span></span>

## <a name="see-also"></a><span data-ttu-id="ecaa0-117">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="ecaa0-117">See Also</span></span>

- [<span data-ttu-id="ecaa0-118">Microsoft. Quantum. DiscreteUniformDistribution</span><span class="sxs-lookup"><span data-stu-id="ecaa0-118">Microsoft.Quantum.DiscreteUniformDistribution</span></span>](xref:Microsoft.Quantum.DiscreteUniformDistribution)