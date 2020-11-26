---
uid: Microsoft.Quantum.Canon.ControlledOnBitString
title: ControlledOnBitString fonction)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ControlledOnBitString
qsharp.summary: Returns a unitary operation that applies an oracle on the target register if the control register state corresponds to a specified bit mask.
ms.openlocfilehash: 9435406506fc99fe211f5dce628b21c18ee4f9fe
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96216657"
---
# <a name="controlledonbitstring-function"></a><span data-ttu-id="1dbac-102">ControlledOnBitString fonction)</span><span class="sxs-lookup"><span data-stu-id="1dbac-102">ControlledOnBitString function</span></span>

<span data-ttu-id="1dbac-103">Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="1dbac-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="1dbac-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="1dbac-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="1dbac-105">Retourne une opération unitaire qui applique un Oracle sur le registre cible si l’état du registre de contrôle correspond à un masque de bits spécifié.</span><span class="sxs-lookup"><span data-stu-id="1dbac-105">Returns a unitary operation that applies an oracle on the target register if the control register state corresponds to a specified bit mask.</span></span>

```qsharp
function ControlledOnBitString<'T> (bits : Bool[], oracle : ('T => Unit is Adj + Ctl)) : ((Qubit[], 'T) => Unit is Adj + Ctl)
```


## <a name="description"></a><span data-ttu-id="1dbac-106">Description</span><span class="sxs-lookup"><span data-stu-id="1dbac-106">Description</span></span>

<span data-ttu-id="1dbac-107">La sortie de cette fonction est une opération qui peut être représentée par une transformation unitaire $U $ telle que \begin{align} U \ket{b_0 b_1 \cdots b_ {n-1}} \ket{\Psi} = \ket{b_0 B_1 \cdots b_ {n-1}} \otimes \begin{cases} V \ket{\Psi} & \textrm{if} (b_0 b_1 \cdots b_ {n-1}) = \texttt{bits} \\ \\ \ket{\Psi} & \textrm{otherwise} \end{cases}, \end{align} où $V $ est une transformation unitaire qui représente l’action de l' `oracle` opération.</span><span class="sxs-lookup"><span data-stu-id="1dbac-107">The output of this function is an operation that can be represented by a unitary transformation $U$ such that \begin{align} U \ket{b_0 b_1 \cdots b_{n - 1}} \ket{\psi} = \ket{b_0 b_1 \cdots b_{n-1}} \otimes \begin{cases} V \ket{\psi} & \textrm{if} (b_0 b_1 \cdots b_{n - 1}) = \texttt{bits} \\\\ \ket{\psi} & \textrm{otherwise} \end{cases}, \end{align} where $V$ is a unitary transformation that represents the action of the `oracle` operation.</span></span>

## <a name="input"></a><span data-ttu-id="1dbac-108">Entrée</span><span class="sxs-lookup"><span data-stu-id="1dbac-108">Input</span></span>

### <a name="bits--bool"></a><span data-ttu-id="1dbac-109">bits : [bool](xref:microsoft.quantum.lang-ref.bool)[]</span><span class="sxs-lookup"><span data-stu-id="1dbac-109">bits : [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span></span>

<span data-ttu-id="1dbac-110">Chaîne de bits pour contrôler l’opération unitaire donnée.</span><span class="sxs-lookup"><span data-stu-id="1dbac-110">The bit string to control the given unitary operation on.</span></span>


### <a name="oracle--t--unit--is-adj--ctl"></a><span data-ttu-id="1dbac-111">Oracle : 't => [unité](xref:microsoft.quantum.lang-ref.unit)  est Adj + CTL</span><span class="sxs-lookup"><span data-stu-id="1dbac-111">oracle : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="1dbac-112">Opération unitaire à appliquer sur le registre cible.</span><span class="sxs-lookup"><span data-stu-id="1dbac-112">The unitary operation to be applied on the target register.</span></span>



## <a name="output--qubitt--unit--is-adj--ctl"></a><span data-ttu-id="1dbac-113">Sortie : ([qubit](xref:microsoft.quantum.lang-ref.qubit)[], t) => [unité](xref:microsoft.quantum.lang-ref.unit)  est Adj + CTL</span><span class="sxs-lookup"><span data-stu-id="1dbac-113">Output : ([Qubit](xref:microsoft.quantum.lang-ref.qubit)[],'T) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="1dbac-114">Opération unitaire qui s’applique au `oracle` Registre cible si l’état du registre de contrôle correspond au masque de bits `bits` .</span><span class="sxs-lookup"><span data-stu-id="1dbac-114">A unitary operation that applies `oracle` on the target register if the control register state corresponds to the bit mask `bits`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="1dbac-115">Paramètres de type</span><span class="sxs-lookup"><span data-stu-id="1dbac-115">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="1dbac-116">Peut</span><span class="sxs-lookup"><span data-stu-id="1dbac-116">'T</span></span>



## <a name="remarks"></a><span data-ttu-id="1dbac-117">Notes</span><span class="sxs-lookup"><span data-stu-id="1dbac-117">Remarks</span></span>

<span data-ttu-id="1dbac-118">Le modèle donné par `bits` peut être plus petit que `controlRegister` , auquel cas des qubits de contrôle supplémentaires sont ignorés (c’est-à-dire qu’ils ne sont ni contrôlés sur $ \ket {0} $, ni sur $ \ket {1} $).</span><span class="sxs-lookup"><span data-stu-id="1dbac-118">The pattern given by `bits` may be shorter than `controlRegister`, in which case additional control qubits are ignored (that is, neither controlled on $\ket{0}$ nor $\ket{1}$).</span></span>
<span data-ttu-id="1dbac-119">Si `bits` est plus long que `controlRegister` , une erreur est générée.</span><span class="sxs-lookup"><span data-stu-id="1dbac-119">If `bits` is longer than `controlRegister`, an error is raised.</span></span>

<span data-ttu-id="1dbac-120">Avec un tableau booléen `bits` et une opération unitaire `oracle` , la sortie de cette fonction est une opération qui effectue les étapes suivantes :</span><span class="sxs-lookup"><span data-stu-id="1dbac-120">Given a Boolean array `bits` and a unitary operation `oracle`, the output of this function is an operation that performs the following steps:</span></span>

* <span data-ttu-id="1dbac-121">Appliquez une `X` opération à chaque qubit du registre de contrôle qui correspond à `false` l’élément de `bits` ;</span><span class="sxs-lookup"><span data-stu-id="1dbac-121">apply an `X` operation to each qubit of the control register that corresponds to `false` element of the `bits`;</span></span>
* <span data-ttu-id="1dbac-122">appliquer `Controlled oracle` aux registres de contrôle et cibles ;</span><span class="sxs-lookup"><span data-stu-id="1dbac-122">apply `Controlled oracle` to the control and target registers;</span></span>
* <span data-ttu-id="1dbac-123">Appliquez une `X` opération à chaque qubit du registre de contrôle qui correspond à l' `false` élément de à `bits` nouveau pour ramener le registre de contrôle à l’état d’origine.</span><span class="sxs-lookup"><span data-stu-id="1dbac-123">apply an `X` operation to each qubit of the control register that corresponds to `false` element of the `bits` again to return the control register to the original state.</span></span>

<span data-ttu-id="1dbac-124">La sortie du `Controlled` functor est un cas particulier `ControlledOnBitString` où `bits` est égal à `[true, ..., true]` .</span><span class="sxs-lookup"><span data-stu-id="1dbac-124">The output of the `Controlled` functor is a special case of `ControlledOnBitString` where `bits` is equal to `[true, ..., true]`.</span></span>