---
uid: Microsoft.Quantum.Canon.TrotterStepSize
title: TrotterStepSize fonction)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: TrotterStepSize
qsharp.summary: Computes Trotter step size in recursive implementation of Trotter simulation algorithm.
ms.openlocfilehash: c7b6432645dcad2bd47c62b91e04e0b42cd04ca9
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840069"
---
# <a name="trotterstepsize-function"></a><span data-ttu-id="1a518-102">TrotterStepSize fonction)</span><span class="sxs-lookup"><span data-stu-id="1a518-102">TrotterStepSize function</span></span>

<span data-ttu-id="1a518-103">Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="1a518-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="1a518-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="1a518-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="1a518-105">Calcule la taille de l’étape trotter dans l’implémentation récursive de l’algorithme de simulation trotter.</span><span class="sxs-lookup"><span data-stu-id="1a518-105">Computes Trotter step size in recursive implementation of Trotter simulation algorithm.</span></span>

```qsharp
function TrotterStepSize (order : Int) : Double
```


## <a name="input"></a><span data-ttu-id="1a518-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="1a518-106">Input</span></span>

### <a name="order--int"></a><span data-ttu-id="1a518-107">commande : [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="1a518-107">order : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>





## <a name="output--double"></a><span data-ttu-id="1a518-108">Sortie : [double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="1a518-108">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>



## <a name="remarks"></a><span data-ttu-id="1a518-109">Notes</span><span class="sxs-lookup"><span data-stu-id="1a518-109">Remarks</span></span>

<span data-ttu-id="1a518-110">Cette opération utilise une convention d’indexation différente de celle de [quant-pH/0508139](https://arxiv.org/abs/quant-ph/0508139).</span><span class="sxs-lookup"><span data-stu-id="1a518-110">This operation uses a different indexing convention than that of [quant-ph/0508139](https://arxiv.org/abs/quant-ph/0508139).</span></span> <span data-ttu-id="1a518-111">En particulier, `DecomposedIntoTimeStepsCA(_, 4)` correspond au scalaire $p _2 (\lambda) $ dans quant-pH/0508139.</span><span class="sxs-lookup"><span data-stu-id="1a518-111">In particular, `DecomposedIntoTimeStepsCA(_, 4)` corresponds to the scalar $p_2(\lambda)$ in quant-ph/0508139.</span></span>