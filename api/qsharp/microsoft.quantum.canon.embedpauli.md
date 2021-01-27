---
uid: Microsoft.Quantum.Canon.EmbedPauli
title: EmbedPauli fonction)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: EmbedPauli
qsharp.summary: Given a single-qubit Pauli operator and the index of a qubit, returns a multi-qubit Pauli operator with the given single-qubit operator at that index and `PauliI` at every other index.
ms.openlocfilehash: 0e6a93e22ee495abcc44bdf522e7c72c0981308b
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840532"
---
# <a name="embedpauli-function"></a><span data-ttu-id="800aa-102">EmbedPauli fonction)</span><span class="sxs-lookup"><span data-stu-id="800aa-102">EmbedPauli function</span></span>

<span data-ttu-id="800aa-103">Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="800aa-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="800aa-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="800aa-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="800aa-105">À partir d’un opérateur Pauli qubit unique et de l’index d’un qubit, retourne un opérateur de Pauli à plusieurs qubit avec l’opérateur Single-qubit donné au niveau de cet index et `PauliI` à chaque autre index.</span><span class="sxs-lookup"><span data-stu-id="800aa-105">Given a single-qubit Pauli operator and the index of a qubit, returns a multi-qubit Pauli operator with the given single-qubit operator at that index and `PauliI` at every other index.</span></span>

```qsharp
function EmbedPauli (pauli : Pauli, location : Int, n : Int) : Pauli[]
```


## <a name="input"></a><span data-ttu-id="800aa-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="800aa-106">Input</span></span>

### <a name="pauli--pauli"></a><span data-ttu-id="800aa-107">Pauli : [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span><span class="sxs-lookup"><span data-stu-id="800aa-107">pauli : [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span></span>

<span data-ttu-id="800aa-108">Opérateur Pauli qubit unique à placer à l’emplacement donné.</span><span class="sxs-lookup"><span data-stu-id="800aa-108">A single-qubit Pauli operator to be placed at the given location.</span></span>


### <a name="location--int"></a><span data-ttu-id="800aa-109">emplacement : [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="800aa-109">location : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="800aa-110">Index tel que `output[location] == pauli` , où `output` est la sortie de cette fonction.</span><span class="sxs-lookup"><span data-stu-id="800aa-110">An index such that `output[location] == pauli`, where `output` is the output of this function.</span></span>


### <a name="n--int"></a><span data-ttu-id="800aa-111">n : [entier](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="800aa-111">n : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="800aa-112">Longueur du tableau à retourner.</span><span class="sxs-lookup"><span data-stu-id="800aa-112">Length of the array to be returned.</span></span>



## <a name="output--pauli"></a><span data-ttu-id="800aa-113">Sortie : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span><span class="sxs-lookup"><span data-stu-id="800aa-113">Output : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span></span>



## <a name="example"></a><span data-ttu-id="800aa-114">Exemple</span><span class="sxs-lookup"><span data-stu-id="800aa-114">Example</span></span>

<span data-ttu-id="800aa-115">Pour obtenir le tableau `[PauliI, PauliI, PauliX, PauliI]` :</span><span class="sxs-lookup"><span data-stu-id="800aa-115">To obtain the array `[PauliI, PauliI, PauliX, PauliI]`:</span></span>

```qsharp
EmbedPauli(PauliX, 2, 3);
```