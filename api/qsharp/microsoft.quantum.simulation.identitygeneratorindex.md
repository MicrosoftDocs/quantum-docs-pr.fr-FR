---
uid: Microsoft.Quantum.Simulation.IdentityGeneratorIndex
title: IdentityGeneratorIndex fonction)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: IdentityGeneratorIndex
qsharp.summary: Returns a generator index consistent with the zero Hamiltonian, `H = 0`, which corresponds to the identity evolution operation.
ms.openlocfilehash: b389ca1e0737463e6ccd5ce885b849c6b32d65d1
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98844339"
---
# <a name="identitygeneratorindex-function"></a><span data-ttu-id="dc97f-102">IdentityGeneratorIndex fonction)</span><span class="sxs-lookup"><span data-stu-id="dc97f-102">IdentityGeneratorIndex function</span></span>

<span data-ttu-id="dc97f-103">Espace de noms : [Microsoft. Quantum. simulation](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="dc97f-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="dc97f-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="dc97f-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="dc97f-105">Retourne un index de générateur cohérent avec le zéro Hamilton, `H = 0` , qui correspond à l’opération d’évolution de l’identité.</span><span class="sxs-lookup"><span data-stu-id="dc97f-105">Returns a generator index consistent with the zero Hamiltonian, `H = 0`, which corresponds to the identity evolution operation.</span></span>

```qsharp
function IdentityGeneratorIndex (idxTerm : Int) : Microsoft.Quantum.Simulation.GeneratorIndex
```


## <a name="input"></a><span data-ttu-id="dc97f-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="dc97f-106">Input</span></span>

### <a name="idxterm--int"></a><span data-ttu-id="dc97f-107">idxTerm : [entier](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="dc97f-107">idxTerm : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="dc97f-108">Cette entrée est ignorée et est définie pour une cohérence avec le <xref:microsoft.quantum.simulation.generatorsystem> type défini par l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="dc97f-108">This input is ignored, and is defined for consistency with the <xref:microsoft.quantum.simulation.generatorsystem> user-defined type.</span></span>



## <a name="output--generatorindex"></a><span data-ttu-id="dc97f-109">Sortie : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="dc97f-109">Output : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="dc97f-110">Index de générateur représentant l’évolution sous la $H de la Hamilton-$0.</span><span class="sxs-lookup"><span data-stu-id="dc97f-110">A generator index representing evolution under the Hamiltonian $H = 0$.</span></span>