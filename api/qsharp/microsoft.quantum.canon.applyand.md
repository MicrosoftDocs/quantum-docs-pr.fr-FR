---
uid: Microsoft.Quantum.Canon.ApplyAnd
title: Opération ApplyAnd
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyAnd
qsharp.summary: Inverts a given target qubit if and only if both control qubits are in the 1 state, using measurement to perform the adjoint operation.
ms.openlocfilehash: 5a4e18cb0361708e1fc00e8d62c0a6c2415d6bed
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92705502"
---
# <a name="applyand-operation"></a><span data-ttu-id="9669c-102">Opération ApplyAnd</span><span class="sxs-lookup"><span data-stu-id="9669c-102">ApplyAnd operation</span></span>

<span data-ttu-id="9669c-103">Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="9669c-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="9669c-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="9669c-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="9669c-105">Inverse un qubit cible donné si et seulement si les deux contrôles qubits sont dans l’État 1, à l’aide de mesures pour exécuter l’opération joint.</span><span class="sxs-lookup"><span data-stu-id="9669c-105">Inverts a given target qubit if and only if both control qubits are in the 1 state, using measurement to perform the adjoint operation.</span></span>

```qsharp
operation ApplyAnd (control1 : Qubit, control2 : Qubit, target : Qubit) : Unit
```


## <a name="description"></a><span data-ttu-id="9669c-106">Description</span><span class="sxs-lookup"><span data-stu-id="9669c-106">Description</span></span>

<span data-ttu-id="9669c-107">Inverse `target` si et seulement si les deux contrôles ont la valeur 1, mais suppose que `target` est dans l’État 0.</span><span class="sxs-lookup"><span data-stu-id="9669c-107">Inverts `target` if and only if both controls are 1, but assumes that `target` is in state 0.</span></span>  <span data-ttu-id="9669c-108">L’opération a T-Count 4, T-Depth 2 et ne nécessite aucune qubit d’assistance et peut donc être préférable à une opération CCNOT, si `target` est connu pour être 0.</span><span class="sxs-lookup"><span data-stu-id="9669c-108">The operation has T-count 4, T-depth 2 and requires no helper qubit, and may therefore be preferable to a CCNOT operation, if `target` is known to be 0.</span></span>  <span data-ttu-id="9669c-109">Le voisin de cette opération est basé sur des mesures et ne nécessite pas de grille T.</span><span class="sxs-lookup"><span data-stu-id="9669c-109">The adjoint of this operation is measurement based and requires no T gates.</span></span>

<span data-ttu-id="9669c-110">L’application contrôlée de cette opération ne nécessite pas de qubit d’assistance, de `2^c` `Rz` portails et n’est pas optimisée pour plus de précision, où `c` est le nombre de qubits de contrôle globaux, y compris les deux contrôles de l' `ApplyAnd` opération.</span><span class="sxs-lookup"><span data-stu-id="9669c-110">The controlled application of this operation requires no helper qubit, `2^c` `Rz` gates and is not optimized for depth, where `c` is the number of overall control qubits including the two controls from the `ApplyAnd` operation.</span></span>  <span data-ttu-id="9669c-111">L’application contrôlée par l’application voisine requiert des `2^c - 1` `Rz` portes (avec un angle deux fois la taille de l’opération non voisine), aucune qubit d’assistance et n’est pas optimisée pour plus de profondeur.</span><span class="sxs-lookup"><span data-stu-id="9669c-111">The adjoint controlled application requires `2^c - 1` `Rz` gates (with an angle twice the size of the non-adjoint operation), no helper qubit and is not optimized for depth.</span></span>

## <a name="input"></a><span data-ttu-id="9669c-112">Entrée</span><span class="sxs-lookup"><span data-stu-id="9669c-112">Input</span></span>

### <a name="control1--qubit"></a><span data-ttu-id="9669c-113">Control1 : [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="9669c-113">control1 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="9669c-114">Premier contrôle qubit</span><span class="sxs-lookup"><span data-stu-id="9669c-114">First control qubit</span></span>


### <a name="control2--qubit"></a><span data-ttu-id="9669c-115">Control2 : [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="9669c-115">control2 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="9669c-116">Deuxième qubit de contrôle</span><span class="sxs-lookup"><span data-stu-id="9669c-116">Second control qubit</span></span>


### <a name="target--qubit"></a><span data-ttu-id="9669c-117">cible : [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="9669c-117">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="9669c-118">Qubit auxiliaire cible ; doit être dans l’État 0</span><span class="sxs-lookup"><span data-stu-id="9669c-118">Target auxiliary qubit; must be in state 0</span></span>



## <a name="output--unit"></a><span data-ttu-id="9669c-119">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="9669c-119">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="references"></a><span data-ttu-id="9669c-120">Références</span><span class="sxs-lookup"><span data-stu-id="9669c-120">References</span></span>

- <span data-ttu-id="9669c-121">Cody Jones : « nouvelles constructions pour la porte Toffoli à tolérance de pannes », phys. Rev. A 87, 022328, 2013 [arXiv : 1212.5069](https://arxiv.org/abs/1212.5069) doi : 10.1103/PhysRevA. 87.022328</span><span class="sxs-lookup"><span data-stu-id="9669c-121">Cody Jones: "Novel constructions for the fault-tolerant Toffoli gate", Phys. Rev. A 87, 022328, 2013 [arXiv:1212.5069](https://arxiv.org/abs/1212.5069) doi:10.1103/PhysRevA.87.022328</span></span>
- <span data-ttu-id="9669c-122">Craig Gidney : « diviser le coût de l’ajout quantique », Quantum 2, page 74, 2018 [arXiv : 1709.06648](https://arxiv.org/abs/1709.06648) doi : 10.1103/PhysRevA. 85.044302</span><span class="sxs-lookup"><span data-stu-id="9669c-122">Craig Gidney: "Halving the cost of quantum addition", Quantum 2, page 74, 2018 [arXiv:1709.06648](https://arxiv.org/abs/1709.06648) doi:10.1103/PhysRevA.85.044302</span></span>
- <span data-ttu-id="9669c-123">Mathias Soeken : « circuits Oracle Quantum et modèle d’arborescence de Noël », [article de blog du 19 décembre 2019](https://msoeken.github.io/blog_qac.html) (Remarque : explique la construction à plusieurs contrôleurs)</span><span class="sxs-lookup"><span data-stu-id="9669c-123">Mathias Soeken: "Quantum Oracle Circuits and the Christmas Tree Pattern", [Blog article from December 19, 2019](https://msoeken.github.io/blog_qac.html) (note: explains the multiple controlled construction)</span></span>