---
uid: Microsoft.Quantum.Research.Chemistry._DeltaParityCNOTbitstring
title: _DeltaParityCNOTbitstring fonction)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Research.Chemistry
qsharp.name: _DeltaParityCNOTbitstring
qsharp.summary: Classical processing step of `ApplyDeltaParity`. This computes a list of control qubits for evaluating parity difference between any two PQRS... terms of even length.
ms.openlocfilehash: 0c0da60e3c389f8208f9f7d5c84a09893f3c1bda
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96226075"
---
# <a name="_deltaparitycnotbitstring-function"></a><span data-ttu-id="04d84-102">_DeltaParityCNOTbitstring fonction)</span><span class="sxs-lookup"><span data-stu-id="04d84-102">_DeltaParityCNOTbitstring function</span></span>

<span data-ttu-id="04d84-103">Espace de noms : [Microsoft. Quantum. Research. chimie](xref:Microsoft.Quantum.Research.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="04d84-103">Namespace: [Microsoft.Quantum.Research.Chemistry](xref:Microsoft.Quantum.Research.Chemistry)</span></span>

<span data-ttu-id="04d84-104">Package : [Microsoft. Quantum. Research. chimie](https://nuget.org/packages/Microsoft.Quantum.Research.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="04d84-104">Package: [Microsoft.Quantum.Research.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Research.Chemistry)</span></span>


<span data-ttu-id="04d84-105">Étape de traitement classique de `ApplyDeltaParity` .</span><span class="sxs-lookup"><span data-stu-id="04d84-105">Classical processing step of `ApplyDeltaParity`.</span></span>
<span data-ttu-id="04d84-106">Cela calcule une liste de qubits de contrôle pour l’évaluation de la différence de parité entre deux PQRS... termes de longueur égale.</span><span class="sxs-lookup"><span data-stu-id="04d84-106">This computes a list of control qubits for evaluating parity difference between any two PQRS... terms of even length.</span></span>

```qsharp
function _DeltaParityCNOTbitstring (prevFermionicTerm : Int[], nextFermionicTerm : Int[]) : (Int, Bool[])
```


## <a name="input"></a><span data-ttu-id="04d84-107">Entrée</span><span class="sxs-lookup"><span data-stu-id="04d84-107">Input</span></span>

### <a name="prevfermionicterm--int"></a><span data-ttu-id="04d84-108">prevFermionicTerm : [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="04d84-108">prevFermionicTerm : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>




### <a name="nextfermionicterm--int"></a><span data-ttu-id="04d84-109">nextFermionicTerm : [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="04d84-109">nextFermionicTerm : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>





## <a name="output--intbool"></a><span data-ttu-id="04d84-110">Sortie : ([int](xref:microsoft.quantum.lang-ref.int),[bool](xref:microsoft.quantum.lang-ref.bool)[])</span><span class="sxs-lookup"><span data-stu-id="04d84-110">Output : ([Int](xref:microsoft.quantum.lang-ref.int),[Bool](xref:microsoft.quantum.lang-ref.bool)[])</span></span>



## <a name="remarks"></a><span data-ttu-id="04d84-111">Notes</span><span class="sxs-lookup"><span data-stu-id="04d84-111">Remarks</span></span>

<span data-ttu-id="04d84-112">Cela suppose que la longueur des termes est égale à.</span><span class="sxs-lookup"><span data-stu-id="04d84-112">This assumes that the length of terms is even.</span></span>
<span data-ttu-id="04d84-113">Calcule la liste des contrôles pour la différence de parité entre deux termes quelconques.</span><span class="sxs-lookup"><span data-stu-id="04d84-113">Computes list of controls for parity difference between any two terms.</span></span>
<span data-ttu-id="04d84-114">Cela suppose que les listes d’entrée sont triées dans l’ordre croissant.</span><span class="sxs-lookup"><span data-stu-id="04d84-114">This assumes that the input lists is sorted in ascending order.</span></span>