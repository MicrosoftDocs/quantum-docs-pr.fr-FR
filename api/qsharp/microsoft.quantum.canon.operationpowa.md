---
uid: Microsoft.Quantum.Canon.OperationPowA
title: OperationPowA fonction)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: OperationPowA
qsharp.summary: >-
  Raises an operation to a power. The modifier `A` indicates that the operation is adjointable.

  That is, given an operation representing a gate $U$, returns a new operation $U^m$ for a power $m$.
ms.openlocfilehash: 67491c3302392e9793677727606df1baaf4f205a
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98852369"
---
# <a name="operationpowa-function"></a><span data-ttu-id="c584a-102">OperationPowA fonction)</span><span class="sxs-lookup"><span data-stu-id="c584a-102">OperationPowA function</span></span>

<span data-ttu-id="c584a-103">Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="c584a-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="c584a-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="c584a-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="c584a-105">Élève une opération à une puissance.</span><span class="sxs-lookup"><span data-stu-id="c584a-105">Raises an operation to a power.</span></span>
<span data-ttu-id="c584a-106">Le modificateur `A` indique que l’opération est adjointable.</span><span class="sxs-lookup"><span data-stu-id="c584a-106">The modifier `A` indicates that the operation is adjointable.</span></span>

<span data-ttu-id="c584a-107">Autrement dit, étant donné une opération représentant une porte $U $, retourne une nouvelle opération $U ^ m $ pour une alimentation $m $.</span><span class="sxs-lookup"><span data-stu-id="c584a-107">That is, given an operation representing a gate $U$, returns a new operation $U^m$ for a power $m$.</span></span>

```qsharp
function OperationPowA<'T> (op : ('T => Unit is Adj), power : Int) : ('T => Unit is Adj)
```


## <a name="input"></a><span data-ttu-id="c584a-108">Entrée</span><span class="sxs-lookup"><span data-stu-id="c584a-108">Input</span></span>

### <a name="op--t--unit--is-adj"></a><span data-ttu-id="c584a-109">OP : 'o => [unité](xref:microsoft.quantum.lang-ref.unit)  est adj</span><span class="sxs-lookup"><span data-stu-id="c584a-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="c584a-110">Une opération $U $ représentant la porte à répéter.</span><span class="sxs-lookup"><span data-stu-id="c584a-110">An operation $U$ representing the gate to be repeated.</span></span>


### <a name="power--int"></a><span data-ttu-id="c584a-111">puissance : [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="c584a-111">power : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="c584a-112">Nombre de fois où $U $ doit être répétée.</span><span class="sxs-lookup"><span data-stu-id="c584a-112">The number of times that $U$ is to be repeated.</span></span>



## <a name="output--t--unit--is-adj"></a><span data-ttu-id="c584a-113">Sortie : 't => [unité](xref:microsoft.quantum.lang-ref.unit)  est adj</span><span class="sxs-lookup"><span data-stu-id="c584a-113">Output : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="c584a-114">Nouvelle opération représentant $U ^ m $, où $m = \texttt{Power} $.</span><span class="sxs-lookup"><span data-stu-id="c584a-114">A new operation representing $U^m$, where $m = \texttt{power}$.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="c584a-115">Paramètres de type</span><span class="sxs-lookup"><span data-stu-id="c584a-115">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="c584a-116">Peut</span><span class="sxs-lookup"><span data-stu-id="c584a-116">'T</span></span>

<span data-ttu-id="c584a-117">Type de l’opération à mettre sous tension.</span><span class="sxs-lookup"><span data-stu-id="c584a-117">The type of the operation to be powered.</span></span>

## <a name="see-also"></a><span data-ttu-id="c584a-118">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="c584a-118">See Also</span></span>

- [<span data-ttu-id="c584a-119">Microsoft. Quantum. Canon. OperationPow</span><span class="sxs-lookup"><span data-stu-id="c584a-119">Microsoft.Quantum.Canon.OperationPow</span></span>](xref:Microsoft.Quantum.Canon.OperationPow)