---
uid: Microsoft.Quantum.Arithmetic.AddI
title: Opération AddI
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: AddI
qsharp.summary: Automatically chooses between addition with carry and without, depending on the register size of `ys`.
ms.openlocfilehash: 9a90d15defd57cf2836a6fda5b52ddaa816fd55e
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96191021"
---
# <a name="addi-operation"></a><span data-ttu-id="7c5ad-102">Opération AddI</span><span class="sxs-lookup"><span data-stu-id="7c5ad-102">AddI operation</span></span>

<span data-ttu-id="7c5ad-103">Espace de noms : [Microsoft. Quantum. Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="7c5ad-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="7c5ad-104">Package : [Microsoft. Quantum. Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span><span class="sxs-lookup"><span data-stu-id="7c5ad-104">Package: [Microsoft.Quantum.Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span></span>


<span data-ttu-id="7c5ad-105">Choisit automatiquement entre l’ajout avec Carry et sans, en fonction de la taille du registre de `ys` .</span><span class="sxs-lookup"><span data-stu-id="7c5ad-105">Automatically chooses between addition with carry and without, depending on the register size of `ys`.</span></span>

```qsharp
operation AddI (xs : Microsoft.Quantum.Arithmetic.LittleEndian, ys : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="7c5ad-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="7c5ad-106">Input</span></span>

### <a name="xs--littleendian"></a><span data-ttu-id="7c5ad-107">XS : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="7c5ad-107">xs : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="7c5ad-108">$n addend $-bit.</span><span class="sxs-lookup"><span data-stu-id="7c5ad-108">$n$-bit addend.</span></span>


### <a name="ys--littleendian"></a><span data-ttu-id="7c5ad-109">distinctes : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="7c5ad-109">ys : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="7c5ad-110">Addend avec au moins $n $ qubits.</span><span class="sxs-lookup"><span data-stu-id="7c5ad-110">Addend with at least $n$ qubits.</span></span> <span data-ttu-id="7c5ad-111">Contiendra le résultat.</span><span class="sxs-lookup"><span data-stu-id="7c5ad-111">Will hold the result.</span></span>



## <a name="output--unit"></a><span data-ttu-id="7c5ad-112">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="7c5ad-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

