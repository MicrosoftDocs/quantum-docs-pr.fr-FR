---
uid: Microsoft.Quantum.Canon.ApplyControlledOnInt
title: Opération ApplyControlledOnInt
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyControlledOnInt
qsharp.summary: Applies a unitary operation on the target register if the control register state corresponds to a specified positive integer.
ms.openlocfilehash: 499a25104742b2d03886065baad4d535ea92e83b
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845100"
---
# <a name="applycontrolledonint-operation"></a><span data-ttu-id="271d9-102">Opération ApplyControlledOnInt</span><span class="sxs-lookup"><span data-stu-id="271d9-102">ApplyControlledOnInt operation</span></span>

<span data-ttu-id="271d9-103">Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="271d9-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="271d9-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="271d9-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="271d9-105">Applique une opération unitaire sur le registre cible si l’état du registre de contrôle correspond à un entier positif spécifié.</span><span class="sxs-lookup"><span data-stu-id="271d9-105">Applies a unitary operation on the target register if the control register state corresponds to a specified positive integer.</span></span>

```qsharp
operation ApplyControlledOnInt<'T> (numberState : Int, oracle : ('T => Unit is Adj + Ctl), controlRegister : Qubit[], targetRegister : 'T) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="271d9-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="271d9-106">Input</span></span>

### <a name="numberstate--int"></a><span data-ttu-id="271d9-107">numberState : [entier](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="271d9-107">numberState : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="271d9-108">Entier non négatif sur lequel l’opération `oracle` doit être contrôlée.</span><span class="sxs-lookup"><span data-stu-id="271d9-108">A nonnegative integer on which the operation `oracle` should be controlled.</span></span>


### <a name="oracle--t--unit--is-adj--ctl"></a><span data-ttu-id="271d9-109">Oracle : 't => [unité](xref:microsoft.quantum.lang-ref.unit)  est Adj + CTL</span><span class="sxs-lookup"><span data-stu-id="271d9-109">oracle : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="271d9-110">Opération unitaire à contrôler.</span><span class="sxs-lookup"><span data-stu-id="271d9-110">A unitary operation to be controlled.</span></span>


### <a name="controlregister--qubit"></a><span data-ttu-id="271d9-111">controlRegister : [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="271d9-111">controlRegister : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="271d9-112">Registre quantique qui contrôle l’application de `oracle` .</span><span class="sxs-lookup"><span data-stu-id="271d9-112">A quantum register that controls application of `oracle`.</span></span>


### <a name="targetregister--t"></a><span data-ttu-id="271d9-113">targetRegister : 't</span><span class="sxs-lookup"><span data-stu-id="271d9-113">targetRegister : 'T</span></span>

<span data-ttu-id="271d9-114">Registre sur lequel appliquer `oracle` .</span><span class="sxs-lookup"><span data-stu-id="271d9-114">A register on which to apply `oracle`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="271d9-115">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="271d9-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="271d9-116">Paramètres de type</span><span class="sxs-lookup"><span data-stu-id="271d9-116">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="271d9-117">Peut</span><span class="sxs-lookup"><span data-stu-id="271d9-117">'T</span></span>



## <a name="remarks"></a><span data-ttu-id="271d9-118">Notes</span><span class="sxs-lookup"><span data-stu-id="271d9-118">Remarks</span></span>

<span data-ttu-id="271d9-119">La valeur de `numberState` est interprétée à l’aide d’un encodage Little endian.</span><span class="sxs-lookup"><span data-stu-id="271d9-119">The value of `numberState` is interpreted using a little-endian encoding.</span></span>

<span data-ttu-id="271d9-120">`numberState` doit être au maximum de $2 ^ \texttt{Length (controlRegister)}-$1.</span><span class="sxs-lookup"><span data-stu-id="271d9-120">`numberState` must be at most $2^\texttt{Length(controlRegister)} - 1$.</span></span>
<span data-ttu-id="271d9-121">Par exemple, `numberState = 537` signifie que `oracle` est appliqué si et seulement si `controlRegister` est dans l’État $ \ket {537} $.</span><span class="sxs-lookup"><span data-stu-id="271d9-121">For example, `numberState = 537` means that `oracle` is applied if and only if `controlRegister` is in the state $\ket{537}$.</span></span>