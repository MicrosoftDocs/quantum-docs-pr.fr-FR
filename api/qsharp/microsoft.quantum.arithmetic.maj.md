---
uid: Microsoft.Quantum.Arithmetic.MAJ
title: Opération de MAJ
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: MAJ
qsharp.summary: This applies the in-place majority operation to 3 qubits.
ms.openlocfilehash: c1801d1d7ed04ead11b672f24d44a94989cf8f1d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92707206"
---
# <a name="maj-operation"></a><span data-ttu-id="a748a-102">Opération de MAJ</span><span class="sxs-lookup"><span data-stu-id="a748a-102">MAJ operation</span></span>

<span data-ttu-id="a748a-103">Espace de noms : [Microsoft. Quantum. Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="a748a-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="a748a-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="a748a-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="a748a-105">Cela applique la majorité en place à 3 qubits.</span><span class="sxs-lookup"><span data-stu-id="a748a-105">This applies the in-place majority operation to 3 qubits.</span></span>

```qsharp
operation MAJ (input0 : Qubit, input1 : Qubit, target : Qubit) : Unit
```


## <a name="description"></a><span data-ttu-id="a748a-106">Description</span><span class="sxs-lookup"><span data-stu-id="a748a-106">Description</span></span>

<span data-ttu-id="a748a-107">Si nous désignerons l’état du qubit cible en tant que $ \ket{z} $, et les États d’entrée du qubits d’entrée comme $ \ket{x} $ et $ \ket{y} $, cette opération effectue la transformation suivante : $ \ket{XYZ} \rightarrow \ket{x \oplus z} \ket{y \oplus z} \ket{\operatorname{MAJ} (x, y, z)} $.</span><span class="sxs-lookup"><span data-stu-id="a748a-107">If we denote the state of the target qubit as $\ket{z}$, and input states of the input qubits as $\ket{x}$ and $\ket{y}$, then this operation performs the following transformation: $\ket{xyz} \rightarrow \ket{x \oplus z} \ket{y \oplus z} \ket{\operatorname{MAJ} (x, y, z)}$.</span></span>

## <a name="input"></a><span data-ttu-id="a748a-108">Entrée</span><span class="sxs-lookup"><span data-stu-id="a748a-108">Input</span></span>

### <a name="input0--qubit"></a><span data-ttu-id="a748a-109">input0 : [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="a748a-109">input0 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="a748a-110">Premier qubit d’entrée.</span><span class="sxs-lookup"><span data-stu-id="a748a-110">The first input qubit.</span></span>


### <a name="input1--qubit"></a><span data-ttu-id="a748a-111">ENTRÉE1 : [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="a748a-111">input1 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="a748a-112">Deuxième qubit d’entrée.</span><span class="sxs-lookup"><span data-stu-id="a748a-112">The second input qubit.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="a748a-113">cible : [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="a748a-113">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="a748a-114">Qubit sur lequel la fonction majoritaire sera appliquée.</span><span class="sxs-lookup"><span data-stu-id="a748a-114">A qubit onto which the majority function will be applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="a748a-115">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="a748a-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>
