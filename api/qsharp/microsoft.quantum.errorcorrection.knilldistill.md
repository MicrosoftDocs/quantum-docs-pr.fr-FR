---
uid: Microsoft.Quantum.ErrorCorrection.KnillDistill
title: Opération KnillDistill
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: KnillDistill
qsharp.summary: Implements the Knill magic state distillation algorithm.
ms.openlocfilehash: 4eff99eebb1e271d240513f827c6e93973ef79a6
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853115"
---
# <a name="knilldistill-operation"></a><span data-ttu-id="939d0-102">Opération KnillDistill</span><span class="sxs-lookup"><span data-stu-id="939d0-102">KnillDistill operation</span></span>

<span data-ttu-id="939d0-103">Espace de noms : [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="939d0-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="939d0-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="939d0-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="939d0-105">Implémente l’algorithme de distillation Magic State Knill.</span><span class="sxs-lookup"><span data-stu-id="939d0-105">Implements the Knill magic state distillation algorithm.</span></span>

```qsharp
operation KnillDistill (roughMagic : Qubit[]) : Bool
```


## <a name="description"></a><span data-ttu-id="939d0-106">Description</span><span class="sxs-lookup"><span data-stu-id="939d0-106">Description</span></span>

<span data-ttu-id="939d0-107">À partir de 15 copies approximatives d’un État magique $ $ \begin{align} \cos\frac{\pi} {8} \ket {0} + \sin \frac{\pi} \ket \end{align} {8} {1} , $ $ donne une copie de qualité supérieure.</span><span class="sxs-lookup"><span data-stu-id="939d0-107">Given 15 approximate copies of a magic state $$ \begin{align} \cos\frac{\pi}{8} \ket{0} + \sin \frac{\pi}{8} \ket{1} \end{align}, $$ yields one higher-quality copy.</span></span>

## <a name="input"></a><span data-ttu-id="939d0-108">Entrée</span><span class="sxs-lookup"><span data-stu-id="939d0-108">Input</span></span>

### <a name="roughmagic--qubit"></a><span data-ttu-id="939d0-109">roughMagic : [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="939d0-109">roughMagic : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="939d0-110">Un registre de quinze qubits contenant des copies approximatives d’un État magique.</span><span class="sxs-lookup"><span data-stu-id="939d0-110">A register of fifteen qubits containing approximate copies of a magic state.</span></span> <span data-ttu-id="939d0-111">L’application suivante de cette procédure de distillation `roughMagic[0]` contient une copie de qualité supérieure et le reste du Registre est réinitialisé à l’État $ \ket{00\cdots 0} $.</span><span class="sxs-lookup"><span data-stu-id="939d0-111">Following application of this distillation procedure, `roughMagic[0]` will contain one higher-quality copy, and the rest of the register will be reset to the $\ket{00\cdots 0}$ state.</span></span>



## <a name="output--bool"></a><span data-ttu-id="939d0-112">Sortie : [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="939d0-112">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="939d0-113">Si `true` la valeur est, la procédure a réussi et la copie de qualité supérieure doit être acceptée.</span><span class="sxs-lookup"><span data-stu-id="939d0-113">If `true`, then the procedure succeeded and the higher-quality copy should be accepted.</span></span> <span data-ttu-id="939d0-114">Si `false` la méthode est, la procédure a échoué et l’état du registre doit être considéré comme non défini.</span><span class="sxs-lookup"><span data-stu-id="939d0-114">If `false`, the procedure failed, and the state of the register should be considered undefined.</span></span>

## <a name="remarks"></a><span data-ttu-id="939d0-115">Notes</span><span class="sxs-lookup"><span data-stu-id="939d0-115">Remarks</span></span>

<span data-ttu-id="939d0-116">Nous suivons l’algorithme de Knill.</span><span class="sxs-lookup"><span data-stu-id="939d0-116">We follow the algorithm of Knill.</span></span>
<span data-ttu-id="939d0-117">Toutefois, l’implémentation actuelle est loin d’être optimale, car elle utilise un trop grand nombre de qubits.</span><span class="sxs-lookup"><span data-stu-id="939d0-117">However, the present implementation is far from being optimal, as it uses too many qubits.</span></span>
<span data-ttu-id="939d0-118">Les États magiques sont injectés dans cette routine, auquel cas il y a de meilleurs protocoles.</span><span class="sxs-lookup"><span data-stu-id="939d0-118">The magic states are injected in this routine, in which case there are better protocols.</span></span>

## <a name="references"></a><span data-ttu-id="939d0-119">Références</span><span class="sxs-lookup"><span data-stu-id="939d0-119">References</span></span>

- [<span data-ttu-id="939d0-120">Knill</span><span class="sxs-lookup"><span data-stu-id="939d0-120">Knill</span></span>](https://arxiv.org/abs/quant-ph/0402171)