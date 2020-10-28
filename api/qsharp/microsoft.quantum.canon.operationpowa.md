---
uid: Microsoft.Quantum.Canon.OperationPowA
title: OperationPowA fonction)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: OperationPowA
qsharp.summary: >-
  Raises an operation to a power. The modifier `A` indicates that the operation is adjointable.

  That is, given an operation representing a gate $U$, returns a new operation $U^m$ for a power $m$.
ms.openlocfilehash: 66df354c6de7e48624712276882759043b78466c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92703930"
---
# <a name="operationpowa-function"></a><span data-ttu-id="1d3ac-102">OperationPowA fonction)</span><span class="sxs-lookup"><span data-stu-id="1d3ac-102">OperationPowA function</span></span>

<span data-ttu-id="1d3ac-103">Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="1d3ac-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="1d3ac-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="1d3ac-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="1d3ac-105">Élève une opération à une puissance.</span><span class="sxs-lookup"><span data-stu-id="1d3ac-105">Raises an operation to a power.</span></span>
<span data-ttu-id="1d3ac-106">Le modificateur `A` indique que l’opération est adjointable.</span><span class="sxs-lookup"><span data-stu-id="1d3ac-106">The modifier `A` indicates that the operation is adjointable.</span></span>

<span data-ttu-id="1d3ac-107">Autrement dit, étant donné une opération représentant une porte $U $, retourne une nouvelle opération $U ^ m $ pour une alimentation $m $.</span><span class="sxs-lookup"><span data-stu-id="1d3ac-107">That is, given an operation representing a gate $U$, returns a new operation $U^m$ for a power $m$.</span></span>

```qsharp
function OperationPowA<'T> (op : ('T => Unit is Adj), power : Int) : ('T => Unit is Adj)
```


## <a name="input"></a><span data-ttu-id="1d3ac-108">Entrée</span><span class="sxs-lookup"><span data-stu-id="1d3ac-108">Input</span></span>

### <a name="op--t--unit-adj"></a><span data-ttu-id="1d3ac-109">OP : t => ajustement d' [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="1d3ac-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="1d3ac-110">Une opération $U $ représentant la porte à répéter.</span><span class="sxs-lookup"><span data-stu-id="1d3ac-110">An operation $U$ representing the gate to be repeated.</span></span>


### <a name="power--int"></a><span data-ttu-id="1d3ac-111">puissance : [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="1d3ac-111">power : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="1d3ac-112">Nombre de fois où $U $ doit être répétée.</span><span class="sxs-lookup"><span data-stu-id="1d3ac-112">The number of times that $U$ is to be repeated.</span></span>



## <a name="output--t--unit-adj"></a><span data-ttu-id="1d3ac-113">Sortie : 't => ajustement d' [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="1d3ac-113">Output : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="1d3ac-114">Nouvelle opération représentant $U ^ m $, où $m = \texttt{Power} $.</span><span class="sxs-lookup"><span data-stu-id="1d3ac-114">A new operation representing $U^m$, where $m = \texttt{power}$.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="1d3ac-115">Paramètres de type</span><span class="sxs-lookup"><span data-stu-id="1d3ac-115">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="1d3ac-116">Peut</span><span class="sxs-lookup"><span data-stu-id="1d3ac-116">'T</span></span>

<span data-ttu-id="1d3ac-117">Type de l’opération à mettre sous tension.</span><span class="sxs-lookup"><span data-stu-id="1d3ac-117">The type of the operation to be powered.</span></span>

## <a name="see-also"></a><span data-ttu-id="1d3ac-118">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="1d3ac-118">See Also</span></span>

- [<span data-ttu-id="1d3ac-119">Microsoft. Quantum. Canon. OperationPow</span><span class="sxs-lookup"><span data-stu-id="1d3ac-119">Microsoft.Quantum.Canon.OperationPow</span></span>](xref:Microsoft.Quantum.Canon.OperationPow)