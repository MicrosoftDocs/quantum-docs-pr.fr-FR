---
uid: Microsoft.Quantum.Arithmetic.AddI
title: Opération AddI
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: AddI
qsharp.summary: Automatically chooses between addition with carry and without, depending on the register size of `ys`.
ms.openlocfilehash: a17403652cc2b2712defe52112a3ac599330da9f
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843847"
---
# <a name="addi-operation"></a><span data-ttu-id="9bc2b-102">Opération AddI</span><span class="sxs-lookup"><span data-stu-id="9bc2b-102">AddI operation</span></span>

<span data-ttu-id="9bc2b-103">Espace de noms : [Microsoft. Quantum. Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="9bc2b-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="9bc2b-104">Package : [Microsoft. Quantum. Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span><span class="sxs-lookup"><span data-stu-id="9bc2b-104">Package: [Microsoft.Quantum.Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span></span>


<span data-ttu-id="9bc2b-105">Choisit automatiquement entre l’ajout avec Carry et sans, en fonction de la taille du registre de `ys` .</span><span class="sxs-lookup"><span data-stu-id="9bc2b-105">Automatically chooses between addition with carry and without, depending on the register size of `ys`.</span></span>

```qsharp
operation AddI (xs : Microsoft.Quantum.Arithmetic.LittleEndian, ys : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="9bc2b-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="9bc2b-106">Input</span></span>

### <a name="xs--littleendian"></a><span data-ttu-id="9bc2b-107">XS : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="9bc2b-107">xs : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="9bc2b-108">$n addend $-bit.</span><span class="sxs-lookup"><span data-stu-id="9bc2b-108">$n$-bit addend.</span></span>


### <a name="ys--littleendian"></a><span data-ttu-id="9bc2b-109">distinctes : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="9bc2b-109">ys : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="9bc2b-110">Addend avec au moins $n $ qubits.</span><span class="sxs-lookup"><span data-stu-id="9bc2b-110">Addend with at least $n$ qubits.</span></span> <span data-ttu-id="9bc2b-111">Contiendra le résultat.</span><span class="sxs-lookup"><span data-stu-id="9bc2b-111">Will hold the result.</span></span>



## <a name="output--unit"></a><span data-ttu-id="9bc2b-112">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="9bc2b-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

