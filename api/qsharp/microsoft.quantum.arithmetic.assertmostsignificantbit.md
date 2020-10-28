---
uid: Microsoft.Quantum.Arithmetic.AssertMostSignificantBit
title: Opération AssertMostSignificantBit
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: AssertMostSignificantBit
qsharp.summary: Asserts that the most significant qubit of a qubit register representing an unsigned integer is in a particular state.
ms.openlocfilehash: 408e50ed9f2e6c8ba35db20855608d2bd1f24eea
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92707451"
---
# <a name="assertmostsignificantbit-operation"></a><span data-ttu-id="d3952-102">Opération AssertMostSignificantBit</span><span class="sxs-lookup"><span data-stu-id="d3952-102">AssertMostSignificantBit operation</span></span>

<span data-ttu-id="d3952-103">Espace de noms : [Microsoft. Quantum. Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="d3952-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="d3952-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="d3952-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="d3952-105">Déclare que le qubit le plus significatif d’un registre qubit qui représente un entier non signé est dans un état particulier.</span><span class="sxs-lookup"><span data-stu-id="d3952-105">Asserts that the most significant qubit of a qubit register representing an unsigned integer is in a particular state.</span></span>

```qsharp
operation AssertMostSignificantBit (value : Result, number : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="input"></a><span data-ttu-id="d3952-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="d3952-106">Input</span></span>

### <a name="value--__invalidresult__"></a><span data-ttu-id="d3952-107">valeur : __non <Result> valide__</span><span class="sxs-lookup"><span data-stu-id="d3952-107">value : __invalid<Result>__</span></span>

<span data-ttu-id="d3952-108">Valeur du bit le plus élevé déclaré.</span><span class="sxs-lookup"><span data-stu-id="d3952-108">The value of the highest bit being asserted.</span></span>


### <a name="number--littleendian"></a><span data-ttu-id="d3952-109">nombre : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="d3952-109">number : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="d3952-110">Entier non signé dont le bit le plus élevé est vérifié.</span><span class="sxs-lookup"><span data-stu-id="d3952-110">Unsigned integer of which the highest bit is checked.</span></span>



## <a name="output--unit"></a><span data-ttu-id="d3952-111">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="d3952-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="d3952-112">Notes</span><span class="sxs-lookup"><span data-stu-id="d3952-112">Remarks</span></span>

<span data-ttu-id="d3952-113">La version contrôlée de cette opération ignore les contrôles.</span><span class="sxs-lookup"><span data-stu-id="d3952-113">The controlled version of this operation ignores controls.</span></span>

## <a name="see-also"></a><span data-ttu-id="d3952-114">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="d3952-114">See Also</span></span>

- [<span data-ttu-id="d3952-115">Microsoft. Quantum. Intrinsic. Assert</span><span class="sxs-lookup"><span data-stu-id="d3952-115">Microsoft.Quantum.Intrinsic.Assert</span></span>](xref:Microsoft.Quantum.Intrinsic.Assert)