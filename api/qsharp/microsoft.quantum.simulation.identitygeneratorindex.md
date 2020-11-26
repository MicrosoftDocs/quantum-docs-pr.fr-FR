---
uid: Microsoft.Quantum.Simulation.IdentityGeneratorIndex
title: IdentityGeneratorIndex fonction)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: IdentityGeneratorIndex
qsharp.summary: Returns a generator index consistent with the zero Hamiltonian, `H = 0`, which corresponds to the identity evolution operation.
ms.openlocfilehash: 2dd3c705b0496df1719dc677e4defea5e435b839
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96229288"
---
# <a name="identitygeneratorindex-function"></a><span data-ttu-id="e4e7b-102">IdentityGeneratorIndex fonction)</span><span class="sxs-lookup"><span data-stu-id="e4e7b-102">IdentityGeneratorIndex function</span></span>

<span data-ttu-id="e4e7b-103">Espace de noms : [Microsoft. Quantum. simulation](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="e4e7b-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="e4e7b-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="e4e7b-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="e4e7b-105">Retourne un index de générateur cohérent avec le zéro Hamilton, `H = 0` , qui correspond à l’opération d’évolution de l’identité.</span><span class="sxs-lookup"><span data-stu-id="e4e7b-105">Returns a generator index consistent with the zero Hamiltonian, `H = 0`, which corresponds to the identity evolution operation.</span></span>

```qsharp
function IdentityGeneratorIndex (idxTerm : Int) : Microsoft.Quantum.Simulation.GeneratorIndex
```


## <a name="input"></a><span data-ttu-id="e4e7b-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="e4e7b-106">Input</span></span>

### <a name="idxterm--int"></a><span data-ttu-id="e4e7b-107">idxTerm : [entier](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="e4e7b-107">idxTerm : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="e4e7b-108">Cette entrée est ignorée et est définie pour une cohérence avec le <xref:microsoft.quantum.simulation.generatorsystem> type défini par l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="e4e7b-108">This input is ignored, and is defined for consistency with the <xref:microsoft.quantum.simulation.generatorsystem> user-defined type.</span></span>



## <a name="output--generatorindex"></a><span data-ttu-id="e4e7b-109">Sortie : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="e4e7b-109">Output : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="e4e7b-110">Index de générateur représentant l’évolution sous la $H de la Hamilton-$0.</span><span class="sxs-lookup"><span data-stu-id="e4e7b-110">A generator index representing evolution under the Hamiltonian $H = 0$.</span></span>