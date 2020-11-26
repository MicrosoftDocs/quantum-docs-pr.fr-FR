---
uid: Microsoft.Quantum.Canon.OperationPowC
title: OperationPowC fonction)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: OperationPowC
qsharp.summary: >-
  Raises an operation to a power. The modifier `C` indicates that the operation is controllable.

  That is, given an operation representing a gate $U$, returns a new operation $U^m$ for a power $m$.
ms.openlocfilehash: 71f66dd0098ab58d327fc33dbe5af191df0d3dc3
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96205726"
---
# <a name="operationpowc-function"></a><span data-ttu-id="0a55b-102">OperationPowC fonction)</span><span class="sxs-lookup"><span data-stu-id="0a55b-102">OperationPowC function</span></span>

<span data-ttu-id="0a55b-103">Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="0a55b-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="0a55b-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="0a55b-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="0a55b-105">Élève une opération à une puissance.</span><span class="sxs-lookup"><span data-stu-id="0a55b-105">Raises an operation to a power.</span></span>
<span data-ttu-id="0a55b-106">Le modificateur `C` indique que l’opération est contrôlable.</span><span class="sxs-lookup"><span data-stu-id="0a55b-106">The modifier `C` indicates that the operation is controllable.</span></span>

<span data-ttu-id="0a55b-107">Autrement dit, étant donné une opération représentant une porte $U $, retourne une nouvelle opération $U ^ m $ pour une alimentation $m $.</span><span class="sxs-lookup"><span data-stu-id="0a55b-107">That is, given an operation representing a gate $U$, returns a new operation $U^m$ for a power $m$.</span></span>

```qsharp
function OperationPowC<'T> (op : ('T => Unit is Ctl), power : Int) : ('T => Unit is Ctl)
```


## <a name="input"></a><span data-ttu-id="0a55b-108">Entrée</span><span class="sxs-lookup"><span data-stu-id="0a55b-108">Input</span></span>

### <a name="op--t--unit--is-ctl"></a><span data-ttu-id="0a55b-109">OP : t => [unité](xref:microsoft.quantum.lang-ref.unit)  est CTL</span><span class="sxs-lookup"><span data-stu-id="0a55b-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="0a55b-110">Une opération $U $ représentant la porte à répéter.</span><span class="sxs-lookup"><span data-stu-id="0a55b-110">An operation $U$ representing the gate to be repeated.</span></span>


### <a name="power--int"></a><span data-ttu-id="0a55b-111">puissance : [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="0a55b-111">power : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="0a55b-112">Nombre de fois où $U $ doit être répétée.</span><span class="sxs-lookup"><span data-stu-id="0a55b-112">The number of times that $U$ is to be repeated.</span></span>



## <a name="output--t--unit--is-ctl"></a><span data-ttu-id="0a55b-113">Sortie : 't => [unité](xref:microsoft.quantum.lang-ref.unit)  est CTL</span><span class="sxs-lookup"><span data-stu-id="0a55b-113">Output : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="0a55b-114">Nouvelle opération représentant $U ^ m $, où $m = \texttt{Power} $.</span><span class="sxs-lookup"><span data-stu-id="0a55b-114">A new operation representing $U^m$, where $m = \texttt{power}$.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="0a55b-115">Paramètres de type</span><span class="sxs-lookup"><span data-stu-id="0a55b-115">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="0a55b-116">Peut</span><span class="sxs-lookup"><span data-stu-id="0a55b-116">'T</span></span>

<span data-ttu-id="0a55b-117">Type de l’opération à mettre sous tension.</span><span class="sxs-lookup"><span data-stu-id="0a55b-117">The type of the operation to be powered.</span></span>

## <a name="see-also"></a><span data-ttu-id="0a55b-118">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="0a55b-118">See Also</span></span>

- [<span data-ttu-id="0a55b-119">Microsoft. Quantum. Canon. OperationPow</span><span class="sxs-lookup"><span data-stu-id="0a55b-119">Microsoft.Quantum.Canon.OperationPow</span></span>](xref:Microsoft.Quantum.Canon.OperationPow)