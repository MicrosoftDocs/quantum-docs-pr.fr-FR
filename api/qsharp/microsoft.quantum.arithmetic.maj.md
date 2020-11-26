---
uid: Microsoft.Quantum.Arithmetic.MAJ
title: Opération de MAJ
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: MAJ
qsharp.summary: This applies the in-place majority operation to 3 qubits.
ms.openlocfilehash: 356689baa6d47b7b93a393f3672991bb589f6921
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96222760"
---
# <a name="maj-operation"></a><span data-ttu-id="4011e-102">Opération de MAJ</span><span class="sxs-lookup"><span data-stu-id="4011e-102">MAJ operation</span></span>

<span data-ttu-id="4011e-103">Espace de noms : [Microsoft. Quantum. Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="4011e-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="4011e-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="4011e-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="4011e-105">Cela applique la majorité en place à 3 qubits.</span><span class="sxs-lookup"><span data-stu-id="4011e-105">This applies the in-place majority operation to 3 qubits.</span></span>

```qsharp
operation MAJ (input0 : Qubit, input1 : Qubit, target : Qubit) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="4011e-106">Description</span><span class="sxs-lookup"><span data-stu-id="4011e-106">Description</span></span>

<span data-ttu-id="4011e-107">Si nous désignerons l’état du qubit cible en tant que $ \ket{z} $, et les États d’entrée du qubits d’entrée comme $ \ket{x} $ et $ \ket{y} $, cette opération effectue la transformation suivante : $ \ket{XYZ} \rightarrow \ket{x \oplus z} \ket{y \oplus z} \ket{\operatorname{MAJ} (x, y, z)} $.</span><span class="sxs-lookup"><span data-stu-id="4011e-107">If we denote the state of the target qubit as $\ket{z}$, and input states of the input qubits as $\ket{x}$ and $\ket{y}$, then this operation performs the following transformation: $\ket{xyz} \rightarrow \ket{x \oplus z} \ket{y \oplus z} \ket{\operatorname{MAJ} (x, y, z)}$.</span></span>

## <a name="input"></a><span data-ttu-id="4011e-108">Entrée</span><span class="sxs-lookup"><span data-stu-id="4011e-108">Input</span></span>

### <a name="input0--qubit"></a><span data-ttu-id="4011e-109">input0 : [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="4011e-109">input0 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="4011e-110">Premier qubit d’entrée.</span><span class="sxs-lookup"><span data-stu-id="4011e-110">The first input qubit.</span></span>


### <a name="input1--qubit"></a><span data-ttu-id="4011e-111">ENTRÉE1 : [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="4011e-111">input1 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="4011e-112">Deuxième qubit d’entrée.</span><span class="sxs-lookup"><span data-stu-id="4011e-112">The second input qubit.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="4011e-113">cible : [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="4011e-113">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="4011e-114">Qubit sur lequel la fonction majoritaire sera appliquée.</span><span class="sxs-lookup"><span data-stu-id="4011e-114">A qubit onto which the majority function will be applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="4011e-115">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="4011e-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

