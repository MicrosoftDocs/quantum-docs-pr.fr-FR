---
uid: Microsoft.Quantum.Diagnostics.AllEqualityFactB
title: AllEqualityFactB fonction)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AllEqualityFactB
qsharp.summary: Asserts that two arrays of boolean values are equal.
ms.openlocfilehash: 79dcf65956ba9436fb6fdd452f22f35d4852d6f8
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96213699"
---
# <a name="allequalityfactb-function"></a><span data-ttu-id="3ee22-102">AllEqualityFactB fonction)</span><span class="sxs-lookup"><span data-stu-id="3ee22-102">AllEqualityFactB function</span></span>

<span data-ttu-id="3ee22-103">Espace de noms : [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="3ee22-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="3ee22-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="3ee22-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="3ee22-105">Déclare que deux tableaux de valeurs booléennes sont égaux.</span><span class="sxs-lookup"><span data-stu-id="3ee22-105">Asserts that two arrays of boolean values are equal.</span></span>

```qsharp
function AllEqualityFactB (actual : Bool[], expected : Bool[], message : String) : Unit
```


## <a name="input"></a><span data-ttu-id="3ee22-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="3ee22-106">Input</span></span>

### <a name="actual--bool"></a><span data-ttu-id="3ee22-107">réel : [bool](xref:microsoft.quantum.lang-ref.bool)[]</span><span class="sxs-lookup"><span data-stu-id="3ee22-107">actual : [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span></span>

<span data-ttu-id="3ee22-108">Tableau produit par un cas de test présentant un intérêt.</span><span class="sxs-lookup"><span data-stu-id="3ee22-108">The array that is produced by a test case of interest.</span></span>


### <a name="expected--bool"></a><span data-ttu-id="3ee22-109">ATTENDU : [bool](xref:microsoft.quantum.lang-ref.bool)[]</span><span class="sxs-lookup"><span data-stu-id="3ee22-109">expected : [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span></span>

<span data-ttu-id="3ee22-110">Tableau attendu à partir d’un cas de test présentant un intérêt.</span><span class="sxs-lookup"><span data-stu-id="3ee22-110">The array that is expected from a test case of interest.</span></span>


### <a name="message--string"></a><span data-ttu-id="3ee22-111">message : [chaîne](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="3ee22-111">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="3ee22-112">Message à imprimer si les tableaux ne sont pas égaux.</span><span class="sxs-lookup"><span data-stu-id="3ee22-112">A message to be printed if the arrays are not equal.</span></span>



## <a name="output--unit"></a><span data-ttu-id="3ee22-113">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="3ee22-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

