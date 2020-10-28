---
uid: Microsoft.Quantum.Arithmetic.AddI
title: Opération AddI
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: AddI
qsharp.summary: Automatically chooses between addition with carry and without, depending on the register size of `ys`.
ms.openlocfilehash: 7ee2b9099ea65b95647422dadc1efe4bf043d147
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92707654"
---
# <a name="addi-operation"></a><span data-ttu-id="070c3-102">Opération AddI</span><span class="sxs-lookup"><span data-stu-id="070c3-102">AddI operation</span></span>

<span data-ttu-id="070c3-103">Espace de noms : [Microsoft. Quantum. Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="070c3-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="070c3-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="070c3-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="070c3-105">Choisit automatiquement entre l’ajout avec Carry et sans, en fonction de la taille du registre de `ys` .</span><span class="sxs-lookup"><span data-stu-id="070c3-105">Automatically chooses between addition with carry and without, depending on the register size of `ys`.</span></span>

```qsharp
operation AddI (xs : Microsoft.Quantum.Arithmetic.LittleEndian, ys : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="input"></a><span data-ttu-id="070c3-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="070c3-106">Input</span></span>

### <a name="xs--littleendian"></a><span data-ttu-id="070c3-107">XS : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="070c3-107">xs : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="070c3-108">$n addend $-bit.</span><span class="sxs-lookup"><span data-stu-id="070c3-108">$n$-bit addend.</span></span>


### <a name="ys--littleendian"></a><span data-ttu-id="070c3-109">distinctes : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="070c3-109">ys : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="070c3-110">Addend avec au moins $n $ qubits.</span><span class="sxs-lookup"><span data-stu-id="070c3-110">Addend with at least $n$ qubits.</span></span> <span data-ttu-id="070c3-111">Contiendra le résultat.</span><span class="sxs-lookup"><span data-stu-id="070c3-111">Will hold the result.</span></span>



## <a name="output--unit"></a><span data-ttu-id="070c3-112">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="070c3-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

