---
uid: Microsoft.Quantum.Research.Chemistry._DeltaParityCNOTbitstring
title: _DeltaParityCNOTbitstring fonction)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Research.Chemistry
qsharp.name: _DeltaParityCNOTbitstring
qsharp.summary: Classical processing step of `ApplyDeltaParity`. This computes a list of control qubits for evaluating parity difference between any two PQRS... terms of even length.
ms.openlocfilehash: 3dd2d299a094577d377780d731e76287815e8d03
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98847598"
---
# <a name="_deltaparitycnotbitstring-function"></a><span data-ttu-id="0cd44-102">_DeltaParityCNOTbitstring fonction)</span><span class="sxs-lookup"><span data-stu-id="0cd44-102">_DeltaParityCNOTbitstring function</span></span>

<span data-ttu-id="0cd44-103">Espace de noms : [Microsoft. Quantum. Research. chimie](xref:Microsoft.Quantum.Research.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="0cd44-103">Namespace: [Microsoft.Quantum.Research.Chemistry](xref:Microsoft.Quantum.Research.Chemistry)</span></span>

<span data-ttu-id="0cd44-104">Package : [Microsoft. Quantum. Research. chimie](https://nuget.org/packages/Microsoft.Quantum.Research.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="0cd44-104">Package: [Microsoft.Quantum.Research.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Research.Chemistry)</span></span>


<span data-ttu-id="0cd44-105">Étape de traitement classique de `ApplyDeltaParity` .</span><span class="sxs-lookup"><span data-stu-id="0cd44-105">Classical processing step of `ApplyDeltaParity`.</span></span>
<span data-ttu-id="0cd44-106">Cela calcule une liste de qubits de contrôle pour l’évaluation de la différence de parité entre deux PQRS... termes de longueur égale.</span><span class="sxs-lookup"><span data-stu-id="0cd44-106">This computes a list of control qubits for evaluating parity difference between any two PQRS... terms of even length.</span></span>

```qsharp
function _DeltaParityCNOTbitstring (prevFermionicTerm : Int[], nextFermionicTerm : Int[]) : (Int, Bool[])
```


## <a name="input"></a><span data-ttu-id="0cd44-107">Entrée</span><span class="sxs-lookup"><span data-stu-id="0cd44-107">Input</span></span>

### <a name="prevfermionicterm--int"></a><span data-ttu-id="0cd44-108">prevFermionicTerm : [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="0cd44-108">prevFermionicTerm : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>




### <a name="nextfermionicterm--int"></a><span data-ttu-id="0cd44-109">nextFermionicTerm : [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="0cd44-109">nextFermionicTerm : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>





## <a name="output--intbool"></a><span data-ttu-id="0cd44-110">Sortie : ([int](xref:microsoft.quantum.lang-ref.int),[bool](xref:microsoft.quantum.lang-ref.bool)[])</span><span class="sxs-lookup"><span data-stu-id="0cd44-110">Output : ([Int](xref:microsoft.quantum.lang-ref.int),[Bool](xref:microsoft.quantum.lang-ref.bool)[])</span></span>



## <a name="remarks"></a><span data-ttu-id="0cd44-111">Notes</span><span class="sxs-lookup"><span data-stu-id="0cd44-111">Remarks</span></span>

<span data-ttu-id="0cd44-112">Cela suppose que la longueur des termes est égale à.</span><span class="sxs-lookup"><span data-stu-id="0cd44-112">This assumes that the length of terms is even.</span></span>
<span data-ttu-id="0cd44-113">Calcule la liste des contrôles pour la différence de parité entre deux termes quelconques.</span><span class="sxs-lookup"><span data-stu-id="0cd44-113">Computes list of controls for parity difference between any two terms.</span></span>
<span data-ttu-id="0cd44-114">Cela suppose que les listes d’entrée sont triées dans l’ordre croissant.</span><span class="sxs-lookup"><span data-stu-id="0cd44-114">This assumes that the input lists is sorted in ascending order.</span></span>