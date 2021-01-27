---
uid: Microsoft.Quantum.Random.DrawRandomDouble
title: Opération DrawRandomDouble
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: DrawRandomDouble
qsharp.summary: Draws a random real number in a given inclusive interval.
ms.openlocfilehash: 792e9c714b761b48618aec2091e167a359c2b522
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98847620"
---
# <a name="drawrandomdouble-operation"></a><span data-ttu-id="1cd8f-102">Opération DrawRandomDouble</span><span class="sxs-lookup"><span data-stu-id="1cd8f-102">DrawRandomDouble operation</span></span>

<span data-ttu-id="1cd8f-103">Espace de noms : [Microsoft. Quantum. Random](xref:Microsoft.Quantum.Random)</span><span class="sxs-lookup"><span data-stu-id="1cd8f-103">Namespace: [Microsoft.Quantum.Random](xref:Microsoft.Quantum.Random)</span></span>

<span data-ttu-id="1cd8f-104">Package : [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="1cd8f-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="1cd8f-105">Dessine un nombre réel aléatoire dans un intervalle inclusif donné.</span><span class="sxs-lookup"><span data-stu-id="1cd8f-105">Draws a random real number in a given inclusive interval.</span></span>

```qsharp
operation DrawRandomDouble (min : Double, max : Double) : Double
```


## <a name="input"></a><span data-ttu-id="1cd8f-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="1cd8f-106">Input</span></span>

### <a name="min--double"></a><span data-ttu-id="1cd8f-107">min : [double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="1cd8f-107">min : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="1cd8f-108">Plus petit nombre réel à dessiner.</span><span class="sxs-lookup"><span data-stu-id="1cd8f-108">The smallest real number to be drawn.</span></span>


### <a name="max--double"></a><span data-ttu-id="1cd8f-109">Max : [double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="1cd8f-109">max : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="1cd8f-110">Nombre réel le plus grand à dessiner.</span><span class="sxs-lookup"><span data-stu-id="1cd8f-110">The largest real number to be drawn.</span></span>



## <a name="output--double"></a><span data-ttu-id="1cd8f-111">Sortie : [double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="1cd8f-111">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="1cd8f-112">Nombre réel aléatoire dans l’intervalle inclusif de `min` à `max` avec une probabilité uniforme.</span><span class="sxs-lookup"><span data-stu-id="1cd8f-112">A random real number in the inclusive interval from `min` to `max` with uniform probability.</span></span>

## <a name="example"></a><span data-ttu-id="1cd8f-113">Exemple</span><span class="sxs-lookup"><span data-stu-id="1cd8f-113">Example</span></span>

<span data-ttu-id="1cd8f-114">L’extrait de code Q # suivant dessine aléatoirement un angle entre $0 $ et $2 \pi $ :</span><span class="sxs-lookup"><span data-stu-id="1cd8f-114">The following Q# snippet randomly draws an angle between $0$ and $2 \pi$:</span></span>

```qsharp
let angle = DrawRandomDouble(0.0, 2.0 * PI());
```

## <a name="remarks"></a><span data-ttu-id="1cd8f-115">Notes</span><span class="sxs-lookup"><span data-stu-id="1cd8f-115">Remarks</span></span>

<span data-ttu-id="1cd8f-116">Échoue si `max <= min` .</span><span class="sxs-lookup"><span data-stu-id="1cd8f-116">Fails if `max <= min`.</span></span>

## <a name="see-also"></a><span data-ttu-id="1cd8f-117">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="1cd8f-117">See Also</span></span>

- [<span data-ttu-id="1cd8f-118">Microsoft. Quantum. ContinuousUniformDistribution</span><span class="sxs-lookup"><span data-stu-id="1cd8f-118">Microsoft.Quantum.ContinuousUniformDistribution</span></span>](xref:Microsoft.Quantum.ContinuousUniformDistribution)