---
uid: Microsoft.Quantum.Diagnostics.EqualityWithinToleranceFact
title: EqualityWithinToleranceFact fonction)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: EqualityWithinToleranceFact
qsharp.summary: Represents the claim that a classical floating point value has the expected value up to a given absolute tolerance.
ms.openlocfilehash: de15a32d5b38c5ab8c681d2c052669a48cf676cc
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92702658"
---
# <a name="equalitywithintolerancefact-function"></a><span data-ttu-id="78e60-102">EqualityWithinToleranceFact fonction)</span><span class="sxs-lookup"><span data-stu-id="78e60-102">EqualityWithinToleranceFact function</span></span>

<span data-ttu-id="78e60-103">Espace de noms : [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="78e60-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="78e60-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="78e60-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="78e60-105">Représente la revendication selon laquelle une valeur à virgule flottante classique a la valeur attendue jusqu’à une tolérance absolue donnée.</span><span class="sxs-lookup"><span data-stu-id="78e60-105">Represents the claim that a classical floating point value has the expected value up to a given absolute tolerance.</span></span>

```qsharp
function EqualityWithinToleranceFact (actual : Double, expected : Double, tolerance : Double) : Unit
```


## <a name="input"></a><span data-ttu-id="78e60-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="78e60-106">Input</span></span>

### <a name="actual--double"></a><span data-ttu-id="78e60-107">réel : [double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="78e60-107">actual : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="78e60-108">Nombre à vérifier.</span><span class="sxs-lookup"><span data-stu-id="78e60-108">The number to be checked.</span></span>


### <a name="expected--double"></a><span data-ttu-id="78e60-109">ATTENDU : [double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="78e60-109">expected : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="78e60-110">Valeur attendue.</span><span class="sxs-lookup"><span data-stu-id="78e60-110">The expected value.</span></span>


### <a name="tolerance--double"></a><span data-ttu-id="78e60-111">tolérance : [double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="78e60-111">tolerance : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="78e60-112">Tolérance absolue sur la différence entre réel et attendu.</span><span class="sxs-lookup"><span data-stu-id="78e60-112">Absolute tolerance on the difference between actual and expected.</span></span>



## <a name="output--unit"></a><span data-ttu-id="78e60-113">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="78e60-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>
