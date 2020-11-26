---
uid: Microsoft.Quantum.Canon.ApplyAnd
title: Opération ApplyAnd
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyAnd
qsharp.summary: Inverts a given target qubit if and only if both control qubits are in the 1 state, using measurement to perform the adjoint operation.
ms.openlocfilehash: b749013584c89273375da002ac36b3575085b7f2
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96219292"
---
# <a name="applyand-operation"></a><span data-ttu-id="bd725-102">Opération ApplyAnd</span><span class="sxs-lookup"><span data-stu-id="bd725-102">ApplyAnd operation</span></span>

<span data-ttu-id="bd725-103">Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="bd725-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="bd725-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="bd725-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="bd725-105">Inverse un qubit cible donné si et seulement si les deux contrôles qubits sont dans l’État 1, à l’aide de mesures pour exécuter l’opération joint.</span><span class="sxs-lookup"><span data-stu-id="bd725-105">Inverts a given target qubit if and only if both control qubits are in the 1 state, using measurement to perform the adjoint operation.</span></span>

```qsharp
operation ApplyAnd (control1 : Qubit, control2 : Qubit, target : Qubit) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="bd725-106">Description</span><span class="sxs-lookup"><span data-stu-id="bd725-106">Description</span></span>

<span data-ttu-id="bd725-107">Inverse `target` si et seulement si les deux contrôles ont la valeur 1, mais suppose que `target` est dans l’État 0.</span><span class="sxs-lookup"><span data-stu-id="bd725-107">Inverts `target` if and only if both controls are 1, but assumes that `target` is in state 0.</span></span>  <span data-ttu-id="bd725-108">L’opération a T-Count 4, T-Depth 2 et ne nécessite aucune qubit d’assistance et peut donc être préférable à une opération CCNOT, si `target` est connu pour être 0.</span><span class="sxs-lookup"><span data-stu-id="bd725-108">The operation has T-count 4, T-depth 2 and requires no helper qubit, and may therefore be preferable to a CCNOT operation, if `target` is known to be 0.</span></span>  <span data-ttu-id="bd725-109">Le voisin de cette opération est basé sur des mesures et ne nécessite pas de grille T.</span><span class="sxs-lookup"><span data-stu-id="bd725-109">The adjoint of this operation is measurement based and requires no T gates.</span></span>

<span data-ttu-id="bd725-110">L’application contrôlée de cette opération ne nécessite pas de qubit d’assistance, de `2^c` `Rz` portails et n’est pas optimisée pour plus de précision, où `c` est le nombre de qubits de contrôle globaux, y compris les deux contrôles de l' `ApplyAnd` opération.</span><span class="sxs-lookup"><span data-stu-id="bd725-110">The controlled application of this operation requires no helper qubit, `2^c` `Rz` gates and is not optimized for depth, where `c` is the number of overall control qubits including the two controls from the `ApplyAnd` operation.</span></span>  <span data-ttu-id="bd725-111">L’application contrôlée par l’application voisine requiert des `2^c - 1` `Rz` portes (avec un angle deux fois la taille de l’opération non voisine), aucune qubit d’assistance et n’est pas optimisée pour plus de profondeur.</span><span class="sxs-lookup"><span data-stu-id="bd725-111">The adjoint controlled application requires `2^c - 1` `Rz` gates (with an angle twice the size of the non-adjoint operation), no helper qubit and is not optimized for depth.</span></span>

## <a name="input"></a><span data-ttu-id="bd725-112">Entrée</span><span class="sxs-lookup"><span data-stu-id="bd725-112">Input</span></span>

### <a name="control1--qubit"></a><span data-ttu-id="bd725-113">Control1 : [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="bd725-113">control1 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="bd725-114">Premier contrôle qubit</span><span class="sxs-lookup"><span data-stu-id="bd725-114">First control qubit</span></span>


### <a name="control2--qubit"></a><span data-ttu-id="bd725-115">Control2 : [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="bd725-115">control2 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="bd725-116">Deuxième qubit de contrôle</span><span class="sxs-lookup"><span data-stu-id="bd725-116">Second control qubit</span></span>


### <a name="target--qubit"></a><span data-ttu-id="bd725-117">cible : [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="bd725-117">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="bd725-118">Qubit auxiliaire cible ; doit être dans l’État 0</span><span class="sxs-lookup"><span data-stu-id="bd725-118">Target auxiliary qubit; must be in state 0</span></span>



## <a name="output--unit"></a><span data-ttu-id="bd725-119">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="bd725-119">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="references"></a><span data-ttu-id="bd725-120">Références</span><span class="sxs-lookup"><span data-stu-id="bd725-120">References</span></span>

- <span data-ttu-id="bd725-121">Cody Jones : « nouvelles constructions pour la porte Toffoli à tolérance de pannes », phys. Rev. A 87, 022328, 2013 [arXiv : 1212.5069](https://arxiv.org/abs/1212.5069) doi : 10.1103/PhysRevA. 87.022328</span><span class="sxs-lookup"><span data-stu-id="bd725-121">Cody Jones: "Novel constructions for the fault-tolerant Toffoli gate", Phys. Rev. A 87, 022328, 2013 [arXiv:1212.5069](https://arxiv.org/abs/1212.5069) doi:10.1103/PhysRevA.87.022328</span></span>
- <span data-ttu-id="bd725-122">Craig Gidney : « diviser le coût de l’ajout quantique », Quantum 2, page 74, 2018 [arXiv : 1709.06648](https://arxiv.org/abs/1709.06648) doi : 10.1103/PhysRevA. 85.044302</span><span class="sxs-lookup"><span data-stu-id="bd725-122">Craig Gidney: "Halving the cost of quantum addition", Quantum 2, page 74, 2018 [arXiv:1709.06648](https://arxiv.org/abs/1709.06648) doi:10.1103/PhysRevA.85.044302</span></span>
- <span data-ttu-id="bd725-123">Mathias Soeken : « circuits Oracle Quantum et modèle d’arborescence de Noël », [article de blog du 19 décembre 2019](https://msoeken.github.io/blog_qac.html) (Remarque : explique la construction à plusieurs contrôleurs)</span><span class="sxs-lookup"><span data-stu-id="bd725-123">Mathias Soeken: "Quantum Oracle Circuits and the Christmas Tree Pattern", [Blog article from December 19, 2019](https://msoeken.github.io/blog_qac.html) (note: explains the multiple controlled construction)</span></span>