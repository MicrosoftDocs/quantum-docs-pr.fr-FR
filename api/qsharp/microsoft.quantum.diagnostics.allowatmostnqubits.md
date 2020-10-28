---
uid: Microsoft.Quantum.Diagnostics.AllowAtMostNQubits
title: Opération AllowAtMostNQubits
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AllowAtMostNQubits
qsharp.summary: Between a call to this operation and its adjoint, asserts that at most a given number of additional qubits are allocated with using statements.
ms.openlocfilehash: ddbed96df0d95cfd78730c091a6a81ee6e49c349
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92702790"
---
# <a name="allowatmostnqubits-operation"></a><span data-ttu-id="fc5f7-102">Opération AllowAtMostNQubits</span><span class="sxs-lookup"><span data-stu-id="fc5f7-102">AllowAtMostNQubits operation</span></span>

<span data-ttu-id="fc5f7-103">Espace de noms : [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="fc5f7-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="fc5f7-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="fc5f7-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="fc5f7-105">Entre un appel à cette opération et son voisin, déclare qu’au plus un nombre donné de qubits supplémentaires sont alloués avec des instructions using.</span><span class="sxs-lookup"><span data-stu-id="fc5f7-105">Between a call to this operation and its adjoint, asserts that at most a given number of additional qubits are allocated with using statements.</span></span>

```qsharp
operation AllowAtMostNQubits (nQubits : Int, message : String) : Unit
```


## <a name="input"></a><span data-ttu-id="fc5f7-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="fc5f7-106">Input</span></span>

### <a name="nqubits--int"></a><span data-ttu-id="fc5f7-107">nQubits : [entier](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="fc5f7-107">nQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="fc5f7-108">Nombre maximal de qubits qui peuvent être alloués.</span><span class="sxs-lookup"><span data-stu-id="fc5f7-108">The maximum number of qubits that may be allocated.</span></span>


### <a name="message--string"></a><span data-ttu-id="fc5f7-109">message : [chaîne](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="fc5f7-109">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="fc5f7-110">Message à afficher en cas d’échec.</span><span class="sxs-lookup"><span data-stu-id="fc5f7-110">A message to be displayed upon failure.</span></span>



## <a name="output--unit"></a><span data-ttu-id="fc5f7-111">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="fc5f7-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="fc5f7-112">Notes</span><span class="sxs-lookup"><span data-stu-id="fc5f7-112">Remarks</span></span>

<span data-ttu-id="fc5f7-113">Cette opération peut être remplacée par une absence d’opération sur les cibles qui ne la prennent pas en charge.</span><span class="sxs-lookup"><span data-stu-id="fc5f7-113">This operation may be replaced by a no-op on targets which do not support it.</span></span>