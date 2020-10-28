---
uid: Microsoft.Quantum.MachineLearning.ControlledRotation
title: Type défini par l’utilisateur ControlledRotation
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: ControlledRotation
qsharp.summary: Describes a controlled rotation in terms of its target and control indices, rotation axis, and index into a model parameter vector.
ms.openlocfilehash: afc425c16ab550fd414e656484c9ff6f0f8f3ef4
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92702064"
---
# <a name="controlledrotation-user-defined-type"></a><span data-ttu-id="aaed5-102">Type défini par l’utilisateur ControlledRotation</span><span class="sxs-lookup"><span data-stu-id="aaed5-102">ControlledRotation user defined type</span></span>

<span data-ttu-id="aaed5-103">Espace de noms : [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="aaed5-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="aaed5-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="aaed5-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="aaed5-105">Décrit une rotation contrôlée en termes de l’index de la cible et du contrôle, de l’axe de rotation et de l’index dans un vecteur de paramètre de modèle.</span><span class="sxs-lookup"><span data-stu-id="aaed5-105">Describes a controlled rotation in terms of its target and control indices, rotation axis, and index into a model parameter vector.</span></span>

```qsharp

newtype ControlledRotation = ((TargetIndex : Int, ControlIndices : Int[]), Axis : Pauli, ParameterIndex : Int);
```



## <a name="named-items"></a><span data-ttu-id="aaed5-106">Éléments nommés</span><span class="sxs-lookup"><span data-stu-id="aaed5-106">Named Items</span></span>

### <a name="targetindex--int"></a><span data-ttu-id="aaed5-107">TargetIndex : [entier](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="aaed5-107">TargetIndex : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="aaed5-108">Index du qubit cible pour cette rotation contrôlée.</span><span class="sxs-lookup"><span data-stu-id="aaed5-108">Index of the target qubit for this controlled rotation.</span></span>
### <a name="controlindices--int"></a><span data-ttu-id="aaed5-109">ControlIndices : [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="aaed5-109">ControlIndices : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="aaed5-110">Tableau des index de qubit de contrôle pour cette rotation.</span><span class="sxs-lookup"><span data-stu-id="aaed5-110">An array of the control qubit indices for this rotation.</span></span>
### <a name="axis--pauli"></a><span data-ttu-id="aaed5-111">Axe : [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span><span class="sxs-lookup"><span data-stu-id="aaed5-111">Axis : [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span></span>

<span data-ttu-id="aaed5-112">Axe pour cette rotation.</span><span class="sxs-lookup"><span data-stu-id="aaed5-112">The axis for this rotation.</span></span>
### <a name="parameterindex--int"></a><span data-ttu-id="aaed5-113">ParameterIndex : [entier](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="aaed5-113">ParameterIndex : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="aaed5-114">Index dans un vecteur de paramètre de modèle décrivant l’angle de cette rotation.</span><span class="sxs-lookup"><span data-stu-id="aaed5-114">An index into a model parameter vector describing the angle for this rotation.</span></span>

## <a name="remarks"></a><span data-ttu-id="aaed5-115">Notes</span><span class="sxs-lookup"><span data-stu-id="aaed5-115">Remarks</span></span>

<span data-ttu-id="aaed5-116">Une rotation non contrôlée peut être représentée en affectant `ControlIndices` à un tableau vide d’index, `new Int[0]` .</span><span class="sxs-lookup"><span data-stu-id="aaed5-116">An uncontrolled rotation can be represented by setting `ControlIndices` to an empty array of indexes, `new Int[0]`.</span></span>