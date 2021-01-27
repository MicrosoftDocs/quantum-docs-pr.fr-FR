---
uid: Microsoft.Quantum.Canon.ControlledOnBitString
title: ControlledOnBitString fonction)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ControlledOnBitString
qsharp.summary: Returns a unitary operation that applies an oracle on the target register if the control register state corresponds to a specified bit mask.
ms.openlocfilehash: 176170cc972ca67b812b84f79cf97ba5418be9b6
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840804"
---
# <a name="controlledonbitstring-function"></a><span data-ttu-id="d74be-102">ControlledOnBitString fonction)</span><span class="sxs-lookup"><span data-stu-id="d74be-102">ControlledOnBitString function</span></span>

<span data-ttu-id="d74be-103">Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="d74be-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="d74be-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="d74be-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="d74be-105">Retourne une opération unitaire qui applique un Oracle sur le registre cible si l’état du registre de contrôle correspond à un masque de bits spécifié.</span><span class="sxs-lookup"><span data-stu-id="d74be-105">Returns a unitary operation that applies an oracle on the target register if the control register state corresponds to a specified bit mask.</span></span>

```qsharp
function ControlledOnBitString<'T> (bits : Bool[], oracle : ('T => Unit is Adj + Ctl)) : ((Qubit[], 'T) => Unit is Adj + Ctl)
```


## <a name="description"></a><span data-ttu-id="d74be-106">Description</span><span class="sxs-lookup"><span data-stu-id="d74be-106">Description</span></span>

<span data-ttu-id="d74be-107">La sortie de cette fonction est une opération qui peut être représentée par une transformation unitaire $U $ telle que \begin{align} U \ket{b_0 b_1 \cdots b_ {n-1}} \ket{\Psi} = \ket{b_0 B_1 \cdots b_ {n-1}} \otimes \begin{cases} V \ket{\Psi} & \textrm{if} (b_0 b_1 \cdots b_ {n-1}) = \texttt{bits} \\ \\ \ket{\Psi} & \textrm{otherwise} \end{cases}, \end{align} où $V $ est une transformation unitaire qui représente l’action de l' `oracle` opération.</span><span class="sxs-lookup"><span data-stu-id="d74be-107">The output of this function is an operation that can be represented by a unitary transformation $U$ such that \begin{align} U \ket{b_0 b_1 \cdots b_{n - 1}} \ket{\psi} = \ket{b_0 b_1 \cdots b_{n-1}} \otimes \begin{cases} V \ket{\psi} & \textrm{if} (b_0 b_1 \cdots b_{n - 1}) = \texttt{bits} \\\\ \ket{\psi} & \textrm{otherwise} \end{cases}, \end{align} where $V$ is a unitary transformation that represents the action of the `oracle` operation.</span></span>

## <a name="input"></a><span data-ttu-id="d74be-108">Entrée</span><span class="sxs-lookup"><span data-stu-id="d74be-108">Input</span></span>

### <a name="bits--bool"></a><span data-ttu-id="d74be-109">bits : [bool](xref:microsoft.quantum.lang-ref.bool)[]</span><span class="sxs-lookup"><span data-stu-id="d74be-109">bits : [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span></span>

<span data-ttu-id="d74be-110">Chaîne de bits pour contrôler l’opération unitaire donnée.</span><span class="sxs-lookup"><span data-stu-id="d74be-110">The bit string to control the given unitary operation on.</span></span>


### <a name="oracle--t--unit--is-adj--ctl"></a><span data-ttu-id="d74be-111">Oracle : 't => [unité](xref:microsoft.quantum.lang-ref.unit)  est Adj + CTL</span><span class="sxs-lookup"><span data-stu-id="d74be-111">oracle : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="d74be-112">Opération unitaire à appliquer sur le registre cible.</span><span class="sxs-lookup"><span data-stu-id="d74be-112">The unitary operation to be applied on the target register.</span></span>



## <a name="output--qubitt--unit--is-adj--ctl"></a><span data-ttu-id="d74be-113">Sortie : ([qubit](xref:microsoft.quantum.lang-ref.qubit)[], t) => [unité](xref:microsoft.quantum.lang-ref.unit)  est Adj + CTL</span><span class="sxs-lookup"><span data-stu-id="d74be-113">Output : ([Qubit](xref:microsoft.quantum.lang-ref.qubit)[],'T) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="d74be-114">Opération unitaire qui s’applique au `oracle` Registre cible si l’état du registre de contrôle correspond au masque de bits `bits` .</span><span class="sxs-lookup"><span data-stu-id="d74be-114">A unitary operation that applies `oracle` on the target register if the control register state corresponds to the bit mask `bits`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="d74be-115">Paramètres de type</span><span class="sxs-lookup"><span data-stu-id="d74be-115">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="d74be-116">Peut</span><span class="sxs-lookup"><span data-stu-id="d74be-116">'T</span></span>



## <a name="example"></a><span data-ttu-id="d74be-117">Exemple</span><span class="sxs-lookup"><span data-stu-id="d74be-117">Example</span></span>

<span data-ttu-id="d74be-118">Les extraits de code suivants sont équivalents :</span><span class="sxs-lookup"><span data-stu-id="d74be-118">The following code snippets are equivalent:</span></span>

```qsharp
(ControlledOnBitString(bits, oracle))(controlRegister, targetRegister);
```

<span data-ttu-id="d74be-119">and</span><span class="sxs-lookup"><span data-stu-id="d74be-119">and</span></span>

```qsharp
within {
    ApplyPauliFromBitString(PauliX, false, bits, controlRegister);
} apply {
    Controlled oracle(controlRegister, targetRegister);
}
```

<span data-ttu-id="d74be-120">Le code suivant prépare un État $ \frac {1} {2} (\ket {00} -\ket {01} + \ket {10} + \ket {11} ) $ :</span><span class="sxs-lookup"><span data-stu-id="d74be-120">The following code prepares a state $\frac{1}{2}(\ket{00} - \ket{01} + \ket{10} + \ket{11})$:</span></span>

```qsharp
using (register = Qubit[2]) {
    ApplyToEach(H, register);
    (ControlledOnBitString([false], Z))(register[0..0], register[1]);
}
```

## <a name="remarks"></a><span data-ttu-id="d74be-121">Notes</span><span class="sxs-lookup"><span data-stu-id="d74be-121">Remarks</span></span>

<span data-ttu-id="d74be-122">Le modèle donné par `bits` peut être plus petit que `controlRegister` , auquel cas des qubits de contrôle supplémentaires sont ignorés (c’est-à-dire qu’ils ne sont ni contrôlés sur $ \ket {0} $, ni sur $ \ket {1} $).</span><span class="sxs-lookup"><span data-stu-id="d74be-122">The pattern given by `bits` may be shorter than `controlRegister`, in which case additional control qubits are ignored (that is, neither controlled on $\ket{0}$ nor $\ket{1}$).</span></span>
<span data-ttu-id="d74be-123">Si `bits` est plus long que `controlRegister` , une erreur est générée.</span><span class="sxs-lookup"><span data-stu-id="d74be-123">If `bits` is longer than `controlRegister`, an error is raised.</span></span>

<span data-ttu-id="d74be-124">Avec un tableau booléen `bits` et une opération unitaire `oracle` , la sortie de cette fonction est une opération qui effectue les étapes suivantes :</span><span class="sxs-lookup"><span data-stu-id="d74be-124">Given a Boolean array `bits` and a unitary operation `oracle`, the output of this function is an operation that performs the following steps:</span></span>

* <span data-ttu-id="d74be-125">Appliquez une `X` opération à chaque qubit du registre de contrôle qui correspond à `false` l’élément de `bits` ;</span><span class="sxs-lookup"><span data-stu-id="d74be-125">apply an `X` operation to each qubit of the control register that corresponds to `false` element of the `bits`;</span></span>
* <span data-ttu-id="d74be-126">appliquer `Controlled oracle` aux registres de contrôle et cibles ;</span><span class="sxs-lookup"><span data-stu-id="d74be-126">apply `Controlled oracle` to the control and target registers;</span></span>
* <span data-ttu-id="d74be-127">Appliquez une `X` opération à chaque qubit du registre de contrôle qui correspond à l' `false` élément de à `bits` nouveau pour ramener le registre de contrôle à l’état d’origine.</span><span class="sxs-lookup"><span data-stu-id="d74be-127">apply an `X` operation to each qubit of the control register that corresponds to `false` element of the `bits` again to return the control register to the original state.</span></span>

<span data-ttu-id="d74be-128">La sortie du `Controlled` functor est un cas particulier `ControlledOnBitString` où `bits` est égal à `[true, ..., true]` .</span><span class="sxs-lookup"><span data-stu-id="d74be-128">The output of the `Controlled` functor is a special case of `ControlledOnBitString` where `bits` is equal to `[true, ..., true]`.</span></span>