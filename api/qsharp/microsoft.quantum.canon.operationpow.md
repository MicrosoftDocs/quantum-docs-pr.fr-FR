---
uid: Microsoft.Quantum.Canon.OperationPow
title: OperationPow fonction)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: OperationPow
qsharp.summary: >-
  Raises an operation to a power.

  That is, given an operation representing a gate $U$, returns a new operation $U^m$ for a power $m$.
ms.openlocfilehash: 5cf9017175f44a8a0b8f865624a6c312d25aded1
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92703954"
---
# <a name="operationpow-function"></a><span data-ttu-id="9c067-102">OperationPow fonction)</span><span class="sxs-lookup"><span data-stu-id="9c067-102">OperationPow function</span></span>

<span data-ttu-id="9c067-103">Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="9c067-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="9c067-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="9c067-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="9c067-105">Élève une opération à une puissance.</span><span class="sxs-lookup"><span data-stu-id="9c067-105">Raises an operation to a power.</span></span>

<span data-ttu-id="9c067-106">Autrement dit, étant donné une opération représentant une porte $U $, retourne une nouvelle opération $U ^ m $ pour une alimentation $m $.</span><span class="sxs-lookup"><span data-stu-id="9c067-106">That is, given an operation representing a gate $U$, returns a new operation $U^m$ for a power $m$.</span></span>

```qsharp
function OperationPow<'T> (op : ('T => Unit), power : Int) : ('T => Unit)
```


## <a name="input"></a><span data-ttu-id="9c067-107">Entrée</span><span class="sxs-lookup"><span data-stu-id="9c067-107">Input</span></span>

### <a name="op--t--unit"></a><span data-ttu-id="9c067-108">OP : 't => [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="9c067-108">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="9c067-109">Une opération $U $ représentant la porte à répéter.</span><span class="sxs-lookup"><span data-stu-id="9c067-109">An operation $U$ representing the gate to be repeated.</span></span>


### <a name="power--int"></a><span data-ttu-id="9c067-110">puissance : [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="9c067-110">power : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="9c067-111">Nombre de fois où $U $ doit être répétée.</span><span class="sxs-lookup"><span data-stu-id="9c067-111">The number of times that $U$ is to be repeated.</span></span>



## <a name="output--t--unit"></a><span data-ttu-id="9c067-112">Sortie : 't => [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="9c067-112">Output : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="9c067-113">Nouvelle opération représentant $U ^ m $, où $m = \texttt{Power} $.</span><span class="sxs-lookup"><span data-stu-id="9c067-113">A new operation representing $U^m$, where $m = \texttt{power}$.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="9c067-114">Paramètres de type</span><span class="sxs-lookup"><span data-stu-id="9c067-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="9c067-115">Peut</span><span class="sxs-lookup"><span data-stu-id="9c067-115">'T</span></span>

<span data-ttu-id="9c067-116">Type de l’opération à mettre sous tension.</span><span class="sxs-lookup"><span data-stu-id="9c067-116">The type of the operation to be powered.</span></span>

## <a name="see-also"></a><span data-ttu-id="9c067-117">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="9c067-117">See Also</span></span>

- [<span data-ttu-id="9c067-118">Microsoft. Quantum. Canon. OperationPowC</span><span class="sxs-lookup"><span data-stu-id="9c067-118">Microsoft.Quantum.Canon.OperationPowC</span></span>](xref:Microsoft.Quantum.Canon.OperationPowC)
- [<span data-ttu-id="9c067-119">Microsoft. Quantum. Canon. OperationPowA</span><span class="sxs-lookup"><span data-stu-id="9c067-119">Microsoft.Quantum.Canon.OperationPowA</span></span>](xref:Microsoft.Quantum.Canon.OperationPowA)
- [<span data-ttu-id="9c067-120">Microsoft. Quantum. Canon. OperationPowCA</span><span class="sxs-lookup"><span data-stu-id="9c067-120">Microsoft.Quantum.Canon.OperationPowCA</span></span>](xref:Microsoft.Quantum.Canon.OperationPowCA)