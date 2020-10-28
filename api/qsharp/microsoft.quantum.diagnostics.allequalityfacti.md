---
uid: Microsoft.Quantum.Diagnostics.AllEqualityFactI
title: AllEqualityFactI fonction)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AllEqualityFactI
qsharp.summary: Asserts that two arrays of integer values are equal.
ms.openlocfilehash: 9ccd212010ae557de5ca4ab2a38d4724c5c29aa8
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92702796"
---
# <a name="allequalityfacti-function"></a><span data-ttu-id="ee923-102">AllEqualityFactI fonction)</span><span class="sxs-lookup"><span data-stu-id="ee923-102">AllEqualityFactI function</span></span>

<span data-ttu-id="ee923-103">Espace de noms : [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="ee923-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="ee923-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="ee923-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="ee923-105">Déclare que deux tableaux de valeurs entières sont égaux.</span><span class="sxs-lookup"><span data-stu-id="ee923-105">Asserts that two arrays of integer values are equal.</span></span>

```qsharp
function AllEqualityFactI (actual : Int[], expected : Int[], message : String) : Unit
```


## <a name="input"></a><span data-ttu-id="ee923-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="ee923-106">Input</span></span>

### <a name="actual--int"></a><span data-ttu-id="ee923-107">réel : [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="ee923-107">actual : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="ee923-108">Tableau produit par un cas de test présentant un intérêt.</span><span class="sxs-lookup"><span data-stu-id="ee923-108">The array that is produced by a test case of interest.</span></span>


### <a name="expected--int"></a><span data-ttu-id="ee923-109">ATTENDU : [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="ee923-109">expected : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="ee923-110">Tableau attendu à partir d’un cas de test présentant un intérêt.</span><span class="sxs-lookup"><span data-stu-id="ee923-110">The array that is expected from a test case of interest.</span></span>


### <a name="message--string"></a><span data-ttu-id="ee923-111">message : [chaîne](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="ee923-111">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="ee923-112">Message à imprimer si les tableaux ne sont pas égaux.</span><span class="sxs-lookup"><span data-stu-id="ee923-112">A message to be printed if the arrays are not equal.</span></span>



## <a name="output--unit"></a><span data-ttu-id="ee923-113">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="ee923-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

