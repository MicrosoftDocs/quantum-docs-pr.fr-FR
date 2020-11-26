---
uid: Microsoft.Quantum.Random.DrawRandomDouble
title: Opération DrawRandomDouble
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: DrawRandomDouble
qsharp.summary: Draws a random real number in a given inclusive interval.
ms.openlocfilehash: d62416f4a222716edb9393fe4f43731d0e8aa9d3
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96192942"
---
# <a name="drawrandomdouble-operation"></a><span data-ttu-id="24836-102">Opération DrawRandomDouble</span><span class="sxs-lookup"><span data-stu-id="24836-102">DrawRandomDouble operation</span></span>

<span data-ttu-id="24836-103">Espace de noms : [Microsoft. Quantum. Random](xref:Microsoft.Quantum.Random)</span><span class="sxs-lookup"><span data-stu-id="24836-103">Namespace: [Microsoft.Quantum.Random](xref:Microsoft.Quantum.Random)</span></span>

<span data-ttu-id="24836-104">Package : [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="24836-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="24836-105">Dessine un nombre réel aléatoire dans un intervalle inclusif donné.</span><span class="sxs-lookup"><span data-stu-id="24836-105">Draws a random real number in a given inclusive interval.</span></span>

```qsharp
operation DrawRandomDouble (min : Double, max : Double) : Double
```


## <a name="input"></a><span data-ttu-id="24836-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="24836-106">Input</span></span>

### <a name="min--double"></a><span data-ttu-id="24836-107">min : [double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="24836-107">min : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="24836-108">Plus petit nombre réel à dessiner.</span><span class="sxs-lookup"><span data-stu-id="24836-108">The smallest real number to be drawn.</span></span>


### <a name="max--double"></a><span data-ttu-id="24836-109">Max : [double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="24836-109">max : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="24836-110">Nombre réel le plus grand à dessiner.</span><span class="sxs-lookup"><span data-stu-id="24836-110">The largest real number to be drawn.</span></span>



## <a name="output--double"></a><span data-ttu-id="24836-111">Sortie : [double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="24836-111">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="24836-112">Nombre réel aléatoire dans l’intervalle inclusif de `min` à `max` avec une probabilité uniforme.</span><span class="sxs-lookup"><span data-stu-id="24836-112">A random real number in the inclusive interval from `min` to `max` with uniform probability.</span></span>

## <a name="remarks"></a><span data-ttu-id="24836-113">Notes</span><span class="sxs-lookup"><span data-stu-id="24836-113">Remarks</span></span>

<span data-ttu-id="24836-114">Échoue si `max <= min` .</span><span class="sxs-lookup"><span data-stu-id="24836-114">Fails if `max <= min`.</span></span>

## <a name="see-also"></a><span data-ttu-id="24836-115">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="24836-115">See Also</span></span>

- [<span data-ttu-id="24836-116">Microsoft. Quantum. ContinuousUniformDistribution</span><span class="sxs-lookup"><span data-stu-id="24836-116">Microsoft.Quantum.ContinuousUniformDistribution</span></span>](xref:Microsoft.Quantum.ContinuousUniformDistribution)