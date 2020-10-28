---
uid: Microsoft.Quantum.Canon.EmbedPauli
title: EmbedPauli fonction)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: EmbedPauli
qsharp.summary: Given a single-qubit Pauli operator and the index of a qubit, returns a multi-qubit Pauli operator with the given single-qubit operator at that index and `PauliI` at every other index.
ms.openlocfilehash: c78406aa4557834ac2bb40cf1847696d075e5135
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92704187"
---
# <a name="embedpauli-function"></a><span data-ttu-id="049fb-102">EmbedPauli fonction)</span><span class="sxs-lookup"><span data-stu-id="049fb-102">EmbedPauli function</span></span>

<span data-ttu-id="049fb-103">Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="049fb-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="049fb-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="049fb-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="049fb-105">À partir d’un opérateur Pauli qubit unique et de l’index d’un qubit, retourne un opérateur de Pauli à plusieurs qubit avec l’opérateur Single-qubit donné au niveau de cet index et `PauliI` à chaque autre index.</span><span class="sxs-lookup"><span data-stu-id="049fb-105">Given a single-qubit Pauli operator and the index of a qubit, returns a multi-qubit Pauli operator with the given single-qubit operator at that index and `PauliI` at every other index.</span></span>

```qsharp
function EmbedPauli (pauli : Pauli, location : Int, n : Int) : Pauli[]
```


## <a name="input"></a><span data-ttu-id="049fb-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="049fb-106">Input</span></span>

### <a name="pauli--pauli"></a><span data-ttu-id="049fb-107">Pauli : [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span><span class="sxs-lookup"><span data-stu-id="049fb-107">pauli : [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span></span>

<span data-ttu-id="049fb-108">Opérateur Pauli qubit unique à placer à l’emplacement donné.</span><span class="sxs-lookup"><span data-stu-id="049fb-108">A single-qubit Pauli operator to be placed at the given location.</span></span>


### <a name="location--int"></a><span data-ttu-id="049fb-109">emplacement : [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="049fb-109">location : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="049fb-110">Index tel que `output[location] == pauli` , où `output` est la sortie de cette fonction.</span><span class="sxs-lookup"><span data-stu-id="049fb-110">An index such that `output[location] == pauli`, where `output` is the output of this function.</span></span>


### <a name="n--int"></a><span data-ttu-id="049fb-111">n : [entier](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="049fb-111">n : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="049fb-112">Longueur du tableau à retourner.</span><span class="sxs-lookup"><span data-stu-id="049fb-112">Length of the array to be returned.</span></span>



## <a name="output--pauli"></a><span data-ttu-id="049fb-113">Sortie : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span><span class="sxs-lookup"><span data-stu-id="049fb-113">Output : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span></span>

