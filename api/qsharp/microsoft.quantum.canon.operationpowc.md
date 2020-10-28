---
uid: Microsoft.Quantum.Canon.OperationPowC
title: OperationPowC fonction)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: OperationPowC
qsharp.summary: >-
  Raises an operation to a power. The modifier `C` indicates that the operation is controllable.

  That is, given an operation representing a gate $U$, returns a new operation $U^m$ for a power $m$.
ms.openlocfilehash: f3c51410fb7c091385b64a1c4c99b3972d5055b1
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92703918"
---
# <a name="operationpowc-function"></a><span data-ttu-id="8254a-102">OperationPowC fonction)</span><span class="sxs-lookup"><span data-stu-id="8254a-102">OperationPowC function</span></span>

<span data-ttu-id="8254a-103">Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="8254a-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="8254a-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="8254a-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="8254a-105">Élève une opération à une puissance.</span><span class="sxs-lookup"><span data-stu-id="8254a-105">Raises an operation to a power.</span></span>
<span data-ttu-id="8254a-106">Le modificateur `C` indique que l’opération est contrôlable.</span><span class="sxs-lookup"><span data-stu-id="8254a-106">The modifier `C` indicates that the operation is controllable.</span></span>

<span data-ttu-id="8254a-107">Autrement dit, étant donné une opération représentant une porte $U $, retourne une nouvelle opération $U ^ m $ pour une alimentation $m $.</span><span class="sxs-lookup"><span data-stu-id="8254a-107">That is, given an operation representing a gate $U$, returns a new operation $U^m$ for a power $m$.</span></span>

```qsharp
function OperationPowC<'T> (op : ('T => Unit is Ctl), power : Int) : ('T => Unit is Ctl)
```


## <a name="input"></a><span data-ttu-id="8254a-108">Entrée</span><span class="sxs-lookup"><span data-stu-id="8254a-108">Input</span></span>

### <a name="op--t--unit-ctl"></a><span data-ttu-id="8254a-109">OP : t => CTL de l' [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="8254a-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>

<span data-ttu-id="8254a-110">Une opération $U $ représentant la porte à répéter.</span><span class="sxs-lookup"><span data-stu-id="8254a-110">An operation $U$ representing the gate to be repeated.</span></span>


### <a name="power--int"></a><span data-ttu-id="8254a-111">puissance : [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="8254a-111">power : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="8254a-112">Nombre de fois où $U $ doit être répétée.</span><span class="sxs-lookup"><span data-stu-id="8254a-112">The number of times that $U$ is to be repeated.</span></span>



## <a name="output--t--unit-ctl"></a><span data-ttu-id="8254a-113">Sortie : 't => CTL de l' [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="8254a-113">Output : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>

<span data-ttu-id="8254a-114">Nouvelle opération représentant $U ^ m $, où $m = \texttt{Power} $.</span><span class="sxs-lookup"><span data-stu-id="8254a-114">A new operation representing $U^m$, where $m = \texttt{power}$.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="8254a-115">Paramètres de type</span><span class="sxs-lookup"><span data-stu-id="8254a-115">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="8254a-116">Peut</span><span class="sxs-lookup"><span data-stu-id="8254a-116">'T</span></span>

<span data-ttu-id="8254a-117">Type de l’opération à mettre sous tension.</span><span class="sxs-lookup"><span data-stu-id="8254a-117">The type of the operation to be powered.</span></span>

## <a name="see-also"></a><span data-ttu-id="8254a-118">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="8254a-118">See Also</span></span>

- [<span data-ttu-id="8254a-119">Microsoft. Quantum. Canon. OperationPow</span><span class="sxs-lookup"><span data-stu-id="8254a-119">Microsoft.Quantum.Canon.OperationPow</span></span>](xref:Microsoft.Quantum.Canon.OperationPow)