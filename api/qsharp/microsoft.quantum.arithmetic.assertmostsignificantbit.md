---
uid: Microsoft.Quantum.Arithmetic.AssertMostSignificantBit
title: Opération AssertMostSignificantBit
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: AssertMostSignificantBit
qsharp.summary: Asserts that the most significant qubit of a qubit register representing an unsigned integer is in a particular state.
ms.openlocfilehash: b0b52a4ba7492d68896669aeb0b6b550d2f27f64
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843425"
---
# <a name="assertmostsignificantbit-operation"></a><span data-ttu-id="af68a-102">Opération AssertMostSignificantBit</span><span class="sxs-lookup"><span data-stu-id="af68a-102">AssertMostSignificantBit operation</span></span>

<span data-ttu-id="af68a-103">Espace de noms : [Microsoft. Quantum. Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="af68a-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="af68a-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="af68a-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="af68a-105">Déclare que le qubit le plus significatif d’un registre qubit qui représente un entier non signé est dans un état particulier.</span><span class="sxs-lookup"><span data-stu-id="af68a-105">Asserts that the most significant qubit of a qubit register representing an unsigned integer is in a particular state.</span></span>

```qsharp
operation AssertMostSignificantBit (value : Result, number : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="af68a-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="af68a-106">Input</span></span>

### <a name="value--__invalidresult__"></a><span data-ttu-id="af68a-107">valeur : __non <Result> valide__</span><span class="sxs-lookup"><span data-stu-id="af68a-107">value : __invalid<Result>__</span></span>

<span data-ttu-id="af68a-108">Valeur du bit le plus élevé déclaré.</span><span class="sxs-lookup"><span data-stu-id="af68a-108">The value of the highest bit being asserted.</span></span>


### <a name="number--littleendian"></a><span data-ttu-id="af68a-109">nombre : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="af68a-109">number : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="af68a-110">Entier non signé dont le bit le plus élevé est vérifié.</span><span class="sxs-lookup"><span data-stu-id="af68a-110">Unsigned integer of which the highest bit is checked.</span></span>



## <a name="output--unit"></a><span data-ttu-id="af68a-111">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="af68a-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="af68a-112">Notes</span><span class="sxs-lookup"><span data-stu-id="af68a-112">Remarks</span></span>

<span data-ttu-id="af68a-113">La version contrôlée de cette opération ignore les contrôles.</span><span class="sxs-lookup"><span data-stu-id="af68a-113">The controlled version of this operation ignores controls.</span></span>

## <a name="see-also"></a><span data-ttu-id="af68a-114">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="af68a-114">See Also</span></span>

- [<span data-ttu-id="af68a-115">Microsoft. Quantum. Intrinsic. Assert</span><span class="sxs-lookup"><span data-stu-id="af68a-115">Microsoft.Quantum.Intrinsic.Assert</span></span>](xref:Microsoft.Quantum.Intrinsic.Assert)