---
uid: Microsoft.Quantum.Canon.ControlledOnInt
title: ControlledOnInt fonction)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ControlledOnInt
qsharp.summary: Returns a unitary operator that applies an oracle on the target register if the control register state corresponds to a specified positive integer.
ms.openlocfilehash: 4c48f3257f91fc50040d02cae7c2f7bdf87ea7c5
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92704310"
---
# <a name="controlledonint-function"></a><span data-ttu-id="80afb-102">ControlledOnInt fonction)</span><span class="sxs-lookup"><span data-stu-id="80afb-102">ControlledOnInt function</span></span>

<span data-ttu-id="80afb-103">Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="80afb-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="80afb-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="80afb-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="80afb-105">Retourne un opérateur unitaire qui applique Oracle sur le registre cible si l’état du registre de contrôle correspond à un entier positif spécifié.</span><span class="sxs-lookup"><span data-stu-id="80afb-105">Returns a unitary operator that applies an oracle on the target register if the control register state corresponds to a specified positive integer.</span></span>

```qsharp
function ControlledOnInt<'T> (numberState : Int, oracle : ('T => Unit is Adj + Ctl)) : ((Qubit[], 'T) => Unit is Adj + Ctl)
```


## <a name="input"></a><span data-ttu-id="80afb-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="80afb-106">Input</span></span>

### <a name="numberstate--int"></a><span data-ttu-id="80afb-107">numberState : [entier](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="80afb-107">numberState : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="80afb-108">Entier positif.</span><span class="sxs-lookup"><span data-stu-id="80afb-108">Positive integer.</span></span>


### <a name="oracle--t--unit-adj--ctl"></a><span data-ttu-id="80afb-109">Oracle : 't = [> Adj](xref:microsoft.quantum.lang-ref.unit) + CTL</span><span class="sxs-lookup"><span data-stu-id="80afb-109">oracle : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="80afb-110">Opérateur unitaire.</span><span class="sxs-lookup"><span data-stu-id="80afb-110">Unitary operator.</span></span>



## <a name="output--qubitt--unit-adj--ctl"></a><span data-ttu-id="80afb-111">Sortie : ([qubit](xref:microsoft.quantum.lang-ref.qubit)[], t) [=> ajuster](xref:microsoft.quantum.lang-ref.unit) + CTL</span><span class="sxs-lookup"><span data-stu-id="80afb-111">Output : ([Qubit](xref:microsoft.quantum.lang-ref.qubit)[],'T) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="80afb-112">Opérateur unitaire qui s’applique au `oracle` Registre cible si l’état du registre de contrôle correspond à l’état du nombre `numberState` .</span><span class="sxs-lookup"><span data-stu-id="80afb-112">A unitary operator that applies `oracle` on the target register if the control register state corresponds to the number state `numberState`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="80afb-113">Paramètres de type</span><span class="sxs-lookup"><span data-stu-id="80afb-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="80afb-114">Peut</span><span class="sxs-lookup"><span data-stu-id="80afb-114">'T</span></span>



## <a name="remarks"></a><span data-ttu-id="80afb-115">Notes</span><span class="sxs-lookup"><span data-stu-id="80afb-115">Remarks</span></span>

<span data-ttu-id="80afb-116">La valeur de `numberState` est interprétée à l’aide d’un encodage Little endian.</span><span class="sxs-lookup"><span data-stu-id="80afb-116">The value of `numberState` is interpreted using a little-endian encoding.</span></span>