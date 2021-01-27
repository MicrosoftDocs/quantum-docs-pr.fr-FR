---
uid: Microsoft.Quantum.Diagnostics.AllEqualityFactB
title: AllEqualityFactB fonction)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AllEqualityFactB
qsharp.summary: Asserts that two arrays of boolean values are equal.
ms.openlocfilehash: 725291e8b5d12683ad580d5938dadd561831e88e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853559"
---
# <a name="allequalityfactb-function"></a><span data-ttu-id="809d8-102">AllEqualityFactB fonction)</span><span class="sxs-lookup"><span data-stu-id="809d8-102">AllEqualityFactB function</span></span>

<span data-ttu-id="809d8-103">Espace de noms : [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="809d8-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="809d8-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="809d8-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="809d8-105">Déclare que deux tableaux de valeurs booléennes sont égaux.</span><span class="sxs-lookup"><span data-stu-id="809d8-105">Asserts that two arrays of boolean values are equal.</span></span>

```qsharp
function AllEqualityFactB (actual : Bool[], expected : Bool[], message : String) : Unit
```


## <a name="input"></a><span data-ttu-id="809d8-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="809d8-106">Input</span></span>

### <a name="actual--bool"></a><span data-ttu-id="809d8-107">réel : [bool](xref:microsoft.quantum.lang-ref.bool)[]</span><span class="sxs-lookup"><span data-stu-id="809d8-107">actual : [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span></span>

<span data-ttu-id="809d8-108">Tableau produit par un cas de test présentant un intérêt.</span><span class="sxs-lookup"><span data-stu-id="809d8-108">The array that is produced by a test case of interest.</span></span>


### <a name="expected--bool"></a><span data-ttu-id="809d8-109">ATTENDU : [bool](xref:microsoft.quantum.lang-ref.bool)[]</span><span class="sxs-lookup"><span data-stu-id="809d8-109">expected : [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span></span>

<span data-ttu-id="809d8-110">Tableau attendu à partir d’un cas de test présentant un intérêt.</span><span class="sxs-lookup"><span data-stu-id="809d8-110">The array that is expected from a test case of interest.</span></span>


### <a name="message--string"></a><span data-ttu-id="809d8-111">message : [chaîne](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="809d8-111">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="809d8-112">Message à imprimer si les tableaux ne sont pas égaux.</span><span class="sxs-lookup"><span data-stu-id="809d8-112">A message to be printed if the arrays are not equal.</span></span>



## <a name="output--unit"></a><span data-ttu-id="809d8-113">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="809d8-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

