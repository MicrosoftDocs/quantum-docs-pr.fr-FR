---
uid: Microsoft.Quantum.Diagnostics.AllowAtMostNCallsCA
title: Opération AllowAtMostNCallsCA
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AllowAtMostNCallsCA
qsharp.summary: Between a call to this operation and its adjoint, asserts that a given operation is called at most a certain number of times.
ms.openlocfilehash: bb6ba2615b571b0d9d056b93f8e36d2dec0c4a21
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853537"
---
# <a name="allowatmostncallsca-operation"></a><span data-ttu-id="2331a-102">Opération AllowAtMostNCallsCA</span><span class="sxs-lookup"><span data-stu-id="2331a-102">AllowAtMostNCallsCA operation</span></span>

<span data-ttu-id="2331a-103">Espace de noms : [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="2331a-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="2331a-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="2331a-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="2331a-105">Entre un appel à cette opération et son voisin, déclare qu’une opération donnée est appelée au plus un certain nombre de fois.</span><span class="sxs-lookup"><span data-stu-id="2331a-105">Between a call to this operation and its adjoint, asserts that a given operation is called at most a certain number of times.</span></span>

```qsharp
operation AllowAtMostNCallsCA<'TInput, 'TOutput> (nTimes : Int, op : ('TInput => 'TOutput is Adj + Ctl), message : String) : Unit is Adj
```


## <a name="input"></a><span data-ttu-id="2331a-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="2331a-106">Input</span></span>

### <a name="ntimes--int"></a><span data-ttu-id="2331a-107">nTimes : [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="2331a-107">nTimes : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="2331a-108">Nombre maximal de fois où `op` peut être appelé.</span><span class="sxs-lookup"><span data-stu-id="2331a-108">The maximum number of times that `op` may be called.</span></span>


### <a name="op--tinput--toutput--is-adj--ctl"></a><span data-ttu-id="2331a-109">OP : 'TInput => 'TOutput est Adj + CTL</span><span class="sxs-lookup"><span data-stu-id="2331a-109">op : 'TInput => 'TOutput  is Adj + Ctl</span></span>

<span data-ttu-id="2331a-110">Opération dont les appels doivent être restreints.</span><span class="sxs-lookup"><span data-stu-id="2331a-110">An operation whose calls are to be restricted.</span></span>


### <a name="message--string"></a><span data-ttu-id="2331a-111">message : [chaîne](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="2331a-111">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="2331a-112">Message à afficher en cas d’échec.</span><span class="sxs-lookup"><span data-stu-id="2331a-112">A message to be displayed upon failure.</span></span>



## <a name="output--unit"></a><span data-ttu-id="2331a-113">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="2331a-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="2331a-114">Paramètres de type</span><span class="sxs-lookup"><span data-stu-id="2331a-114">Type Parameters</span></span>

### <a name="tinput"></a><span data-ttu-id="2331a-115">'TInput</span><span class="sxs-lookup"><span data-stu-id="2331a-115">'TInput</span></span>


### <a name="toutput"></a><span data-ttu-id="2331a-116">«TOutput</span><span class="sxs-lookup"><span data-stu-id="2331a-116">'TOutput</span></span>



## <a name="example"></a><span data-ttu-id="2331a-117">Exemple</span><span class="sxs-lookup"><span data-stu-id="2331a-117">Example</span></span>

<span data-ttu-id="2331a-118">L’extrait de code suivant échoue lorsqu’il est exécuté sur des ordinateurs qui prennent en charge ce diagnostic :</span><span class="sxs-lookup"><span data-stu-id="2331a-118">The following snippet will fail when executed on machines which support this diagnostic:</span></span>

```qsharp
using (register = Qubit[4]) {
    within {
        AllowAtMostNCallsCA(3, H, "Too many calls to H.");
    } apply {
        // Fails since this calls H four times, rather than the
        // allowed maximum of three.
        ApplyToEach(H, register);
    }
}
```

## <a name="remarks"></a><span data-ttu-id="2331a-119">Notes</span><span class="sxs-lookup"><span data-stu-id="2331a-119">Remarks</span></span>

<span data-ttu-id="2331a-120">Cette opération peut être remplacée par une absence d’opération sur les cibles qui ne la prennent pas en charge.</span><span class="sxs-lookup"><span data-stu-id="2331a-120">This operation may be replaced by a no-op on targets which do not support it.</span></span>