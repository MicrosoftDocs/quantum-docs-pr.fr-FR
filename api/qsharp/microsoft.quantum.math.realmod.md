---
uid: Microsoft.Quantum.Math.RealMod
title: RealMod fonction)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: RealMod
qsharp.summary: Computes the modulus between two real numbers.
ms.openlocfilehash: 56da313fabb20655ec358120b8d9b435e4971159
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848346"
---
# <a name="realmod-function"></a><span data-ttu-id="c068d-102">RealMod fonction)</span><span class="sxs-lookup"><span data-stu-id="c068d-102">RealMod function</span></span>

<span data-ttu-id="c068d-103">Espace de noms : [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="c068d-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="c068d-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="c068d-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="c068d-105">Calcule le modulo entre deux nombres réels.</span><span class="sxs-lookup"><span data-stu-id="c068d-105">Computes the modulus between two real numbers.</span></span>

```qsharp
function RealMod (value : Double, modulo : Double, minValue : Double) : Double
```


## <a name="input"></a><span data-ttu-id="c068d-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="c068d-106">Input</span></span>

### <a name="value--double"></a><span data-ttu-id="c068d-107">valeur : [double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="c068d-107">value : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="c068d-108">Nombre réel $x $ pour prendre le modulo de.</span><span class="sxs-lookup"><span data-stu-id="c068d-108">A real number $x$ to take the modulus of.</span></span>


### <a name="modulo--double"></a><span data-ttu-id="c068d-109">modulo : [double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="c068d-109">modulo : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="c068d-110">Nombre réel pour prendre le modulo de $x $ par rapport à.</span><span class="sxs-lookup"><span data-stu-id="c068d-110">A real number to take the modulus of $x$ with respect to.</span></span>


### <a name="minvalue--double"></a><span data-ttu-id="c068d-111">minValue : [double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="c068d-111">minValue : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="c068d-112">Valeur la plus petite à retourner par cette fonction.</span><span class="sxs-lookup"><span data-stu-id="c068d-112">The smallest value to be returned by this function.</span></span>



## <a name="output--double"></a><span data-ttu-id="c068d-113">Sortie : [double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="c068d-113">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>



## <a name="example"></a><span data-ttu-id="c068d-114">Exemple</span><span class="sxs-lookup"><span data-stu-id="c068d-114">Example</span></span>

```qsharp
    // Returns 3 π / 2.
    let y = RealMod(5.5 * PI(), 2.0 * PI(), 0.0);
    // Returns -1.2, since +3.6 and -1.2 are 4.8 apart on the real line,
    // which is a multiple of 2.4.
    let z = RealMod(3.6, 2.4, -1.2);
```

## <a name="remarks"></a><span data-ttu-id="c068d-115">Notes</span><span class="sxs-lookup"><span data-stu-id="c068d-115">Remarks</span></span>

<span data-ttu-id="c068d-116">Cette fonction calcule le modulo réel en encapsulant la ligne réelle sur le cercle d’unité, puis en recherchant l’angle sur le cercle d’unité correspondant à l’entrée.</span><span class="sxs-lookup"><span data-stu-id="c068d-116">This function computes the real modulus by wrapping the real line about the unit circle, then finding the angle on the unit circle corresponding to the input.</span></span>
<span data-ttu-id="c068d-117">L' `minValue` entrée spécifie ensuite où couper le cercle d’unité.</span><span class="sxs-lookup"><span data-stu-id="c068d-117">The `minValue` input then effectively specifies where to cut the unit circle.</span></span>