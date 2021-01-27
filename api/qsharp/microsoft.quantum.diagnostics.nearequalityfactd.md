---
uid: Microsoft.Quantum.Diagnostics.NearEqualityFactD
title: NearEqualityFactD fonction)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: NearEqualityFactD
qsharp.summary: Asserts that a classical floating point value has the expected value up to a small tolerance of 1e-10.
ms.openlocfilehash: d632a7a12c9ebbebfbc7939f2b8a24de8ae1ba2a
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98827909"
---
# <a name="nearequalityfactd-function"></a><span data-ttu-id="57253-102">NearEqualityFactD fonction)</span><span class="sxs-lookup"><span data-stu-id="57253-102">NearEqualityFactD function</span></span>

<span data-ttu-id="57253-103">Espace de noms : [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="57253-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="57253-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="57253-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="57253-105">Déclare qu’une valeur à virgule flottante classique a la valeur attendue jusqu’à une petite tolérance de 1e-10.</span><span class="sxs-lookup"><span data-stu-id="57253-105">Asserts that a classical floating point value has the expected value up to a small tolerance of 1e-10.</span></span>

```qsharp
function NearEqualityFactD (actual : Double, expected : Double) : Unit
```


## <a name="input"></a><span data-ttu-id="57253-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="57253-106">Input</span></span>

### <a name="actual--double"></a><span data-ttu-id="57253-107">réel : [double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="57253-107">actual : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="57253-108">Nombre à vérifier.</span><span class="sxs-lookup"><span data-stu-id="57253-108">The number to be checked.</span></span>


### <a name="expected--double"></a><span data-ttu-id="57253-109">ATTENDU : [double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="57253-109">expected : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="57253-110">Valeur attendue.</span><span class="sxs-lookup"><span data-stu-id="57253-110">The expected value.</span></span>



## <a name="output--unit"></a><span data-ttu-id="57253-111">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="57253-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="57253-112">Notes</span><span class="sxs-lookup"><span data-stu-id="57253-112">Remarks</span></span>

<span data-ttu-id="57253-113">Cela équivaut à une <xref:microsoft.quantum.diagnostics.equalitywithintolerancefact> tolérance codée en dur de $10 ^ {-10} $.</span><span class="sxs-lookup"><span data-stu-id="57253-113">This is equivalent to <xref:microsoft.quantum.diagnostics.equalitywithintolerancefact> with hardcoded tolerance of $10^{-10}$.</span></span>