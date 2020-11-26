---
uid: Microsoft.Quantum.Canon.ApplyControlledOnBitString
title: Opération ApplyControlledOnBitString
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyControlledOnBitString
qsharp.summary: Applies a unitary operation on the target register, controlled on a a state specified by a given bit mask.
ms.openlocfilehash: 6947d2dbdec4cfbb592143024a7c8ccd53a32029
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96219071"
---
# <a name="applycontrolledonbitstring-operation"></a><span data-ttu-id="ae54d-102">Opération ApplyControlledOnBitString</span><span class="sxs-lookup"><span data-stu-id="ae54d-102">ApplyControlledOnBitString operation</span></span>

<span data-ttu-id="ae54d-103">Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="ae54d-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="ae54d-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="ae54d-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="ae54d-105">Applique une opération unitaire sur le registre cible, contrôlée sur un état spécifié par un masque de bits donné.</span><span class="sxs-lookup"><span data-stu-id="ae54d-105">Applies a unitary operation on the target register, controlled on a a state specified by a given bit mask.</span></span>

```qsharp
operation ApplyControlledOnBitString<'T> (bits : Bool[], oracle : ('T => Unit is Adj + Ctl), controlRegister : Qubit[], targetRegister : 'T) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="ae54d-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="ae54d-106">Input</span></span>

### <a name="bits--bool"></a><span data-ttu-id="ae54d-107">bits : [bool](xref:microsoft.quantum.lang-ref.bool)[]</span><span class="sxs-lookup"><span data-stu-id="ae54d-107">bits : [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span></span>

<span data-ttu-id="ae54d-108">Chaîne de bits pour contrôler l’opération unitaire donnée.</span><span class="sxs-lookup"><span data-stu-id="ae54d-108">The bit string to control the given unitary operation on.</span></span>


### <a name="oracle--t--unit--is-adj--ctl"></a><span data-ttu-id="ae54d-109">Oracle : 't => [unité](xref:microsoft.quantum.lang-ref.unit)  est Adj + CTL</span><span class="sxs-lookup"><span data-stu-id="ae54d-109">oracle : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="ae54d-110">Opération unitaire à appliquer sur le registre cible.</span><span class="sxs-lookup"><span data-stu-id="ae54d-110">The unitary operation to be applied on the target register.</span></span>


### <a name="controlregister--qubit"></a><span data-ttu-id="ae54d-111">controlRegister : [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="ae54d-111">controlRegister : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="ae54d-112">Registre quantique qui contrôle l’application de `oracle` .</span><span class="sxs-lookup"><span data-stu-id="ae54d-112">A quantum register that controls application of `oracle`.</span></span>


### <a name="targetregister--t"></a><span data-ttu-id="ae54d-113">targetRegister : 't</span><span class="sxs-lookup"><span data-stu-id="ae54d-113">targetRegister : 'T</span></span>

<span data-ttu-id="ae54d-114">Registre cible à passer `oracle` en tant qu’entrée.</span><span class="sxs-lookup"><span data-stu-id="ae54d-114">The target register to be passed to `oracle` as an input.</span></span>



## <a name="output--unit"></a><span data-ttu-id="ae54d-115">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="ae54d-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="ae54d-116">Paramètres de type</span><span class="sxs-lookup"><span data-stu-id="ae54d-116">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="ae54d-117">Peut</span><span class="sxs-lookup"><span data-stu-id="ae54d-117">'T</span></span>



## <a name="remarks"></a><span data-ttu-id="ae54d-118">Notes</span><span class="sxs-lookup"><span data-stu-id="ae54d-118">Remarks</span></span>

<span data-ttu-id="ae54d-119">Le modèle donné par `bits` peut être plus petit que `controlRegister` , auquel cas des qubits de contrôle supplémentaires sont ignorés (c’est-à-dire qu’ils ne sont ni contrôlés sur $ \ket {0} $, ni sur $ \ket {1} $).</span><span class="sxs-lookup"><span data-stu-id="ae54d-119">The pattern given by `bits` may be shorter than `controlRegister`, in which case additional control qubits are ignored (that is, neither controlled on $\ket{0}$ nor $\ket{1}$).</span></span>
<span data-ttu-id="ae54d-120">Si `bits` est plus long que `controlRegister` , une erreur est générée.</span><span class="sxs-lookup"><span data-stu-id="ae54d-120">If `bits` is longer than `controlRegister`, an error is raised.</span></span>

<span data-ttu-id="ae54d-121">Par exemple, `bits = [0,1,0,0,1]` signifie que `oracle` est appliqué si et seulement si `controlRegister` est dans l’État $ \ket {0} \ket {1} \ket {0} \ket {0} \ket {1} $.</span><span class="sxs-lookup"><span data-stu-id="ae54d-121">For example, `bits = [0,1,0,0,1]` means that `oracle` is applied if and only if `controlRegister` is in the state $\ket{0}\ket{1}\ket{0}\ket{0}\ket{1}$.</span></span>