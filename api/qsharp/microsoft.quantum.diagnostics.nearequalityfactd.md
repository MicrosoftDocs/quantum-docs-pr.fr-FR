---
uid: Microsoft.Quantum.Diagnostics.NearEqualityFactD
title: NearEqualityFactD fonction)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: NearEqualityFactD
qsharp.summary: Asserts that a classical floating point value has the expected value up to a small tolerance of 1e-10.
ms.openlocfilehash: 5b55f515b27667071218a3f604ef703a6a15206d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92702616"
---
# <a name="nearequalityfactd-function"></a><span data-ttu-id="726eb-102">NearEqualityFactD fonction)</span><span class="sxs-lookup"><span data-stu-id="726eb-102">NearEqualityFactD function</span></span>

<span data-ttu-id="726eb-103">Espace de noms : [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="726eb-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="726eb-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="726eb-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="726eb-105">Déclare qu’une valeur à virgule flottante classique a la valeur attendue jusqu’à une petite tolérance de 1e-10.</span><span class="sxs-lookup"><span data-stu-id="726eb-105">Asserts that a classical floating point value has the expected value up to a small tolerance of 1e-10.</span></span>

```qsharp
function NearEqualityFactD (actual : Double, expected : Double) : Unit
```


## <a name="input"></a><span data-ttu-id="726eb-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="726eb-106">Input</span></span>

### <a name="actual--double"></a><span data-ttu-id="726eb-107">réel : [double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="726eb-107">actual : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="726eb-108">Nombre à vérifier.</span><span class="sxs-lookup"><span data-stu-id="726eb-108">The number to be checked.</span></span>


### <a name="expected--double"></a><span data-ttu-id="726eb-109">ATTENDU : [double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="726eb-109">expected : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="726eb-110">Valeur attendue.</span><span class="sxs-lookup"><span data-stu-id="726eb-110">The expected value.</span></span>



## <a name="output--unit"></a><span data-ttu-id="726eb-111">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="726eb-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="726eb-112">Notes</span><span class="sxs-lookup"><span data-stu-id="726eb-112">Remarks</span></span>

<span data-ttu-id="726eb-113">Cela équivaut à une <xref:microsoft.quantum.diagnostics.equalitywithintolerancefact> tolérance codée en dur de $10 ^ {-10} $.</span><span class="sxs-lookup"><span data-stu-id="726eb-113">This is equivalent to <xref:microsoft.quantum.diagnostics.equalitywithintolerancefact> with hardcoded tolerance of $10^{-10}$.</span></span>