---
uid: Microsoft.Quantum.Simulation.IdentityGeneratorIndex
title: IdentityGeneratorIndex fonction)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: IdentityGeneratorIndex
qsharp.summary: Returns a generator index consistent with the zero Hamiltonian, `H = 0`, which corresponds to the identity evolution operation.
ms.openlocfilehash: d2af2dafaf75a68546cb3f16c04cf4c7ee50c6ff
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92708882"
---
# <a name="identitygeneratorindex-function"></a><span data-ttu-id="d4577-102">IdentityGeneratorIndex fonction)</span><span class="sxs-lookup"><span data-stu-id="d4577-102">IdentityGeneratorIndex function</span></span>

<span data-ttu-id="d4577-103">Espace de noms : [Microsoft. Quantum. simulation](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="d4577-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="d4577-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="d4577-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="d4577-105">Retourne un index de générateur cohérent avec le zéro Hamilton, `H = 0` , qui correspond à l’opération d’évolution de l’identité.</span><span class="sxs-lookup"><span data-stu-id="d4577-105">Returns a generator index consistent with the zero Hamiltonian, `H = 0`, which corresponds to the identity evolution operation.</span></span>

```qsharp
function IdentityGeneratorIndex (idxTerm : Int) : Microsoft.Quantum.Simulation.GeneratorIndex
```


## <a name="input"></a><span data-ttu-id="d4577-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="d4577-106">Input</span></span>

### <a name="idxterm--int"></a><span data-ttu-id="d4577-107">idxTerm : [entier](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="d4577-107">idxTerm : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="d4577-108">Cette entrée est ignorée et est définie pour une cohérence avec le <xref:microsoft.quantum.simulation.generatorsystem> type défini par l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="d4577-108">This input is ignored, and is defined for consistency with the <xref:microsoft.quantum.simulation.generatorsystem> user-defined type.</span></span>



## <a name="output--generatorindex"></a><span data-ttu-id="d4577-109">Sortie : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="d4577-109">Output : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="d4577-110">Index de générateur représentant l’évolution sous la $H de la Hamilton-$0.</span><span class="sxs-lookup"><span data-stu-id="d4577-110">A generator index representing evolution under the Hamiltonian $H = 0$.</span></span>