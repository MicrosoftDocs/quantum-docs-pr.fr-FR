---
uid: Microsoft.Quantum.Diagnostics.EqualityWithinToleranceFact
title: EqualityWithinToleranceFact fonction)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: EqualityWithinToleranceFact
qsharp.summary: Represents the claim that a classical floating point value has the expected value up to a given absolute tolerance.
ms.openlocfilehash: 6ada2632974fddd6dd0fd8e4e6ab0866e4f29524
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96201714"
---
# <a name="equalitywithintolerancefact-function"></a><span data-ttu-id="4173e-102">EqualityWithinToleranceFact fonction)</span><span class="sxs-lookup"><span data-stu-id="4173e-102">EqualityWithinToleranceFact function</span></span>

<span data-ttu-id="4173e-103">Espace de noms : [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="4173e-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="4173e-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="4173e-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="4173e-105">Représente la revendication selon laquelle une valeur à virgule flottante classique a la valeur attendue jusqu’à une tolérance absolue donnée.</span><span class="sxs-lookup"><span data-stu-id="4173e-105">Represents the claim that a classical floating point value has the expected value up to a given absolute tolerance.</span></span>

```qsharp
function EqualityWithinToleranceFact (actual : Double, expected : Double, tolerance : Double) : Unit
```


## <a name="input"></a><span data-ttu-id="4173e-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="4173e-106">Input</span></span>

### <a name="actual--double"></a><span data-ttu-id="4173e-107">réel : [double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="4173e-107">actual : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="4173e-108">Nombre à vérifier.</span><span class="sxs-lookup"><span data-stu-id="4173e-108">The number to be checked.</span></span>


### <a name="expected--double"></a><span data-ttu-id="4173e-109">ATTENDU : [double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="4173e-109">expected : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="4173e-110">Valeur attendue.</span><span class="sxs-lookup"><span data-stu-id="4173e-110">The expected value.</span></span>


### <a name="tolerance--double"></a><span data-ttu-id="4173e-111">tolérance : [double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="4173e-111">tolerance : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="4173e-112">Tolérance absolue sur la différence entre réel et attendu.</span><span class="sxs-lookup"><span data-stu-id="4173e-112">Absolute tolerance on the difference between actual and expected.</span></span>



## <a name="output--unit"></a><span data-ttu-id="4173e-113">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="4173e-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

