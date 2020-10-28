---
uid: Microsoft.Quantum.Canon.OperationPowCA
title: OperationPowCA fonction)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: OperationPowCA
qsharp.summary: >-
  Raises an operation to a power. The modifier `A` indicates that the operation is controllable and adjointable.

  That is, given an operation representing a gate $U$, returns a new operation $U^m$ for a power $m$.
ms.openlocfilehash: 753063452616747309e3e228ce8a702f4378c61f
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92703912"
---
# <a name="operationpowca-function"></a><span data-ttu-id="eaea2-102">OperationPowCA fonction)</span><span class="sxs-lookup"><span data-stu-id="eaea2-102">OperationPowCA function</span></span>

<span data-ttu-id="eaea2-103">Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="eaea2-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="eaea2-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="eaea2-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="eaea2-105">Élève une opération à une puissance.</span><span class="sxs-lookup"><span data-stu-id="eaea2-105">Raises an operation to a power.</span></span>
<span data-ttu-id="eaea2-106">Le modificateur `A` indique que l’opération est contrôlable et adjointable.</span><span class="sxs-lookup"><span data-stu-id="eaea2-106">The modifier `A` indicates that the operation is controllable and adjointable.</span></span>

<span data-ttu-id="eaea2-107">Autrement dit, étant donné une opération représentant une porte $U $, retourne une nouvelle opération $U ^ m $ pour une alimentation $m $.</span><span class="sxs-lookup"><span data-stu-id="eaea2-107">That is, given an operation representing a gate $U$, returns a new operation $U^m$ for a power $m$.</span></span>

```qsharp
function OperationPowCA<'T> (op : ('T => Unit is Ctl + Adj), power : Int) : ('T => Unit is Ctl + Adj)
```


## <a name="input"></a><span data-ttu-id="eaea2-108">Entrée</span><span class="sxs-lookup"><span data-stu-id="eaea2-108">Input</span></span>

### <a name="op--t--unit-ctl--adj"></a><span data-ttu-id="eaea2-109">OP : 't => d' [unité](xref:microsoft.quantum.lang-ref.unit) CTL + adj</span><span class="sxs-lookup"><span data-stu-id="eaea2-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl + Adj</span></span>

<span data-ttu-id="eaea2-110">Une opération $U $ représentant la porte à répéter.</span><span class="sxs-lookup"><span data-stu-id="eaea2-110">An operation $U$ representing the gate to be repeated.</span></span>


### <a name="power--int"></a><span data-ttu-id="eaea2-111">puissance : [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="eaea2-111">power : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="eaea2-112">Nombre de fois où $U $ doit être répétée.</span><span class="sxs-lookup"><span data-stu-id="eaea2-112">The number of times that $U$ is to be repeated.</span></span>



## <a name="output--t--unit-ctl--adj"></a><span data-ttu-id="eaea2-113">Sortie : 't = [> liste](xref:microsoft.quantum.lang-ref.unit) CTL + adj</span><span class="sxs-lookup"><span data-stu-id="eaea2-113">Output : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl + Adj</span></span>

<span data-ttu-id="eaea2-114">Nouvelle opération représentant $U ^ m $, où $m = \texttt{Power} $.</span><span class="sxs-lookup"><span data-stu-id="eaea2-114">A new operation representing $U^m$, where $m = \texttt{power}$.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="eaea2-115">Paramètres de type</span><span class="sxs-lookup"><span data-stu-id="eaea2-115">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="eaea2-116">Peut</span><span class="sxs-lookup"><span data-stu-id="eaea2-116">'T</span></span>

<span data-ttu-id="eaea2-117">Type de l’opération à mettre sous tension.</span><span class="sxs-lookup"><span data-stu-id="eaea2-117">The type of the operation to be powered.</span></span>

## <a name="see-also"></a><span data-ttu-id="eaea2-118">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="eaea2-118">See Also</span></span>

- [<span data-ttu-id="eaea2-119">Microsoft. Quantum. Canon. OperationPow</span><span class="sxs-lookup"><span data-stu-id="eaea2-119">Microsoft.Quantum.Canon.OperationPow</span></span>](xref:Microsoft.Quantum.Canon.OperationPow)