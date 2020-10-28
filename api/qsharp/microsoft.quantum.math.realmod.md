---
uid: Microsoft.Quantum.Math.RealMod
title: RealMod fonction)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: RealMod
qsharp.summary: Computes the modulus between two real numbers.
ms.openlocfilehash: 6ec799885bd2f0d35314ed727356499efbe9fcf8
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92706798"
---
# <a name="realmod-function"></a><span data-ttu-id="44033-102">RealMod fonction)</span><span class="sxs-lookup"><span data-stu-id="44033-102">RealMod function</span></span>

<span data-ttu-id="44033-103">Espace de noms : [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="44033-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="44033-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="44033-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="44033-105">Calcule le modulo entre deux nombres réels.</span><span class="sxs-lookup"><span data-stu-id="44033-105">Computes the modulus between two real numbers.</span></span>

```qsharp
function RealMod (value : Double, modulo : Double, minValue : Double) : Double
```


## <a name="input"></a><span data-ttu-id="44033-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="44033-106">Input</span></span>

### <a name="value--double"></a><span data-ttu-id="44033-107">valeur : [double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="44033-107">value : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="44033-108">Nombre réel $x $ pour prendre le modulo de.</span><span class="sxs-lookup"><span data-stu-id="44033-108">A real number $x$ to take the modulus of.</span></span>


### <a name="modulo--double"></a><span data-ttu-id="44033-109">modulo : [double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="44033-109">modulo : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="44033-110">Nombre réel pour prendre le modulo de $x $ par rapport à.</span><span class="sxs-lookup"><span data-stu-id="44033-110">A real number to take the modulus of $x$ with respect to.</span></span>


### <a name="minvalue--double"></a><span data-ttu-id="44033-111">minValue : [double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="44033-111">minValue : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="44033-112">Valeur la plus petite à retourner par cette fonction.</span><span class="sxs-lookup"><span data-stu-id="44033-112">The smallest value to be returned by this function.</span></span>



## <a name="output--double"></a><span data-ttu-id="44033-113">Sortie : [double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="44033-113">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>



## <a name="remarks"></a><span data-ttu-id="44033-114">Notes</span><span class="sxs-lookup"><span data-stu-id="44033-114">Remarks</span></span>

<span data-ttu-id="44033-115">Cette fonction calcule le modulo réel en encapsulant la ligne réelle sur le cercle d’unité, puis en recherchant l’angle sur le cercle d’unité correspondant à l’entrée.</span><span class="sxs-lookup"><span data-stu-id="44033-115">This function computes the real modulus by wrapping the real line about the unit circle, then finding the angle on the unit circle corresponding to the input.</span></span>
<span data-ttu-id="44033-116">L' `minValue` entrée spécifie ensuite où couper le cercle d’unité.</span><span class="sxs-lookup"><span data-stu-id="44033-116">The `minValue` input then effectively specifies where to cut the unit circle.</span></span>