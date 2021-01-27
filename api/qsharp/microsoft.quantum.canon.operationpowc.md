---
uid: Microsoft.Quantum.Canon.OperationPowC
title: OperationPowC fonction)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: OperationPowC
qsharp.summary: >-
  Raises an operation to a power. The modifier `C` indicates that the operation is controllable.

  That is, given an operation representing a gate $U$, returns a new operation $U^m$ for a power $m$.
ms.openlocfilehash: 05b0d5b286e16c308d8c3df8fb8fa1ac8c9868ca
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98852352"
---
# <a name="operationpowc-function"></a><span data-ttu-id="0f30d-102">OperationPowC fonction)</span><span class="sxs-lookup"><span data-stu-id="0f30d-102">OperationPowC function</span></span>

<span data-ttu-id="0f30d-103">Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="0f30d-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="0f30d-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="0f30d-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="0f30d-105">Élève une opération à une puissance.</span><span class="sxs-lookup"><span data-stu-id="0f30d-105">Raises an operation to a power.</span></span>
<span data-ttu-id="0f30d-106">Le modificateur `C` indique que l’opération est contrôlable.</span><span class="sxs-lookup"><span data-stu-id="0f30d-106">The modifier `C` indicates that the operation is controllable.</span></span>

<span data-ttu-id="0f30d-107">Autrement dit, étant donné une opération représentant une porte $U $, retourne une nouvelle opération $U ^ m $ pour une alimentation $m $.</span><span class="sxs-lookup"><span data-stu-id="0f30d-107">That is, given an operation representing a gate $U$, returns a new operation $U^m$ for a power $m$.</span></span>

```qsharp
function OperationPowC<'T> (op : ('T => Unit is Ctl), power : Int) : ('T => Unit is Ctl)
```


## <a name="input"></a><span data-ttu-id="0f30d-108">Entrée</span><span class="sxs-lookup"><span data-stu-id="0f30d-108">Input</span></span>

### <a name="op--t--unit--is-ctl"></a><span data-ttu-id="0f30d-109">OP : t => [unité](xref:microsoft.quantum.lang-ref.unit)  est CTL</span><span class="sxs-lookup"><span data-stu-id="0f30d-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="0f30d-110">Une opération $U $ représentant la porte à répéter.</span><span class="sxs-lookup"><span data-stu-id="0f30d-110">An operation $U$ representing the gate to be repeated.</span></span>


### <a name="power--int"></a><span data-ttu-id="0f30d-111">puissance : [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="0f30d-111">power : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="0f30d-112">Nombre de fois où $U $ doit être répétée.</span><span class="sxs-lookup"><span data-stu-id="0f30d-112">The number of times that $U$ is to be repeated.</span></span>



## <a name="output--t--unit--is-ctl"></a><span data-ttu-id="0f30d-113">Sortie : 't => [unité](xref:microsoft.quantum.lang-ref.unit)  est CTL</span><span class="sxs-lookup"><span data-stu-id="0f30d-113">Output : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="0f30d-114">Nouvelle opération représentant $U ^ m $, où $m = \texttt{Power} $.</span><span class="sxs-lookup"><span data-stu-id="0f30d-114">A new operation representing $U^m$, where $m = \texttt{power}$.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="0f30d-115">Paramètres de type</span><span class="sxs-lookup"><span data-stu-id="0f30d-115">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="0f30d-116">Peut</span><span class="sxs-lookup"><span data-stu-id="0f30d-116">'T</span></span>

<span data-ttu-id="0f30d-117">Type de l’opération à mettre sous tension.</span><span class="sxs-lookup"><span data-stu-id="0f30d-117">The type of the operation to be powered.</span></span>

## <a name="see-also"></a><span data-ttu-id="0f30d-118">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="0f30d-118">See Also</span></span>

- [<span data-ttu-id="0f30d-119">Microsoft. Quantum. Canon. OperationPow</span><span class="sxs-lookup"><span data-stu-id="0f30d-119">Microsoft.Quantum.Canon.OperationPow</span></span>](xref:Microsoft.Quantum.Canon.OperationPow)