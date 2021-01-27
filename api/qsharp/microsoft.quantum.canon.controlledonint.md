---
uid: Microsoft.Quantum.Canon.ControlledOnInt
title: ControlledOnInt fonction)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ControlledOnInt
qsharp.summary: Returns a unitary operator that applies an oracle on the target register if the control register state corresponds to a specified positive integer.
ms.openlocfilehash: 6c7f46c44f2a2427f702e463195f26660cb4fca1
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840782"
---
# <a name="controlledonint-function"></a><span data-ttu-id="324be-102">ControlledOnInt fonction)</span><span class="sxs-lookup"><span data-stu-id="324be-102">ControlledOnInt function</span></span>

<span data-ttu-id="324be-103">Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="324be-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="324be-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="324be-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="324be-105">Retourne un opérateur unitaire qui applique Oracle sur le registre cible si l’état du registre de contrôle correspond à un entier positif spécifié.</span><span class="sxs-lookup"><span data-stu-id="324be-105">Returns a unitary operator that applies an oracle on the target register if the control register state corresponds to a specified positive integer.</span></span>

```qsharp
function ControlledOnInt<'T> (numberState : Int, oracle : ('T => Unit is Adj + Ctl)) : ((Qubit[], 'T) => Unit is Adj + Ctl)
```


## <a name="input"></a><span data-ttu-id="324be-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="324be-106">Input</span></span>

### <a name="numberstate--int"></a><span data-ttu-id="324be-107">numberState : [entier](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="324be-107">numberState : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="324be-108">Entier positif.</span><span class="sxs-lookup"><span data-stu-id="324be-108">Positive integer.</span></span>


### <a name="oracle--t--unit--is-adj--ctl"></a><span data-ttu-id="324be-109">Oracle : 't => [unité](xref:microsoft.quantum.lang-ref.unit)  est Adj + CTL</span><span class="sxs-lookup"><span data-stu-id="324be-109">oracle : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="324be-110">Opérateur unitaire.</span><span class="sxs-lookup"><span data-stu-id="324be-110">Unitary operator.</span></span>



## <a name="output--qubitt--unit--is-adj--ctl"></a><span data-ttu-id="324be-111">Sortie : ([qubit](xref:microsoft.quantum.lang-ref.qubit)[], t) => [unité](xref:microsoft.quantum.lang-ref.unit)  est Adj + CTL</span><span class="sxs-lookup"><span data-stu-id="324be-111">Output : ([Qubit](xref:microsoft.quantum.lang-ref.qubit)[],'T) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="324be-112">Opérateur unitaire qui s’applique au `oracle` Registre cible si l’état du registre de contrôle correspond à l’état du nombre `numberState` .</span><span class="sxs-lookup"><span data-stu-id="324be-112">A unitary operator that applies `oracle` on the target register if the control register state corresponds to the number state `numberState`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="324be-113">Paramètres de type</span><span class="sxs-lookup"><span data-stu-id="324be-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="324be-114">Peut</span><span class="sxs-lookup"><span data-stu-id="324be-114">'T</span></span>



## <a name="remarks"></a><span data-ttu-id="324be-115">Notes</span><span class="sxs-lookup"><span data-stu-id="324be-115">Remarks</span></span>

<span data-ttu-id="324be-116">La valeur de `numberState` est interprétée à l’aide d’un encodage Little endian.</span><span class="sxs-lookup"><span data-stu-id="324be-116">The value of `numberState` is interpreted using a little-endian encoding.</span></span>