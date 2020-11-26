---
uid: Microsoft.Quantum.Canon.ApplyIfOneCA
title: Opération ApplyIfOneCA
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfOneCA
qsharp.summary: Applies a unitary operation conditioned on a classical result value being one.
ms.openlocfilehash: 29801ed0bec08d0ab818f237feb17c2a2a7af1e4
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96218578"
---
# <a name="applyifoneca-operation"></a><span data-ttu-id="1ac7a-102">Opération ApplyIfOneCA</span><span class="sxs-lookup"><span data-stu-id="1ac7a-102">ApplyIfOneCA operation</span></span>

<span data-ttu-id="1ac7a-103">Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="1ac7a-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="1ac7a-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="1ac7a-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="1ac7a-105">Applique une opération unitaire conditionnée sur une valeur de résultat classique qui en est une.</span><span class="sxs-lookup"><span data-stu-id="1ac7a-105">Applies a unitary operation conditioned on a classical result value being one.</span></span>

```qsharp
operation ApplyIfOneCA<'T> (result : Result, (op : ('T => Unit is Adj + Ctl), target : 'T)) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="1ac7a-106">Description</span><span class="sxs-lookup"><span data-stu-id="1ac7a-106">Description</span></span>

<span data-ttu-id="1ac7a-107">Pour une opération donnée `op` et une valeur de résultat `result` , s’applique `op` à `target` si `result` est `One` .</span><span class="sxs-lookup"><span data-stu-id="1ac7a-107">Given an operation `op` and a result value `result`, applies `op` to the `target` if `result` is `One`.</span></span> <span data-ttu-id="1ac7a-108">Si `Zero` , rien ne se passe au `target` .</span><span class="sxs-lookup"><span data-stu-id="1ac7a-108">If `Zero`, nothing happens to the `target`.</span></span>
<span data-ttu-id="1ac7a-109">Le suffixe `CA` indique que l’opération à appliquer est unitaire (contrôlable et adjointable).</span><span class="sxs-lookup"><span data-stu-id="1ac7a-109">The suffix `CA` indicates that the operation to be applied is unitary (controllable and adjointable).</span></span>

## <a name="input"></a><span data-ttu-id="1ac7a-110">Entrée</span><span class="sxs-lookup"><span data-stu-id="1ac7a-110">Input</span></span>

### <a name="result--__invalidresult__"></a><span data-ttu-id="1ac7a-111">résultat : __non <Result> valide__</span><span class="sxs-lookup"><span data-stu-id="1ac7a-111">result : __invalid<Result>__</span></span>

<span data-ttu-id="1ac7a-112">Résultat de mesure qui contrôle si l’opération est appliquée ou non.</span><span class="sxs-lookup"><span data-stu-id="1ac7a-112">A measurement result that controls whether op is applied or not.</span></span>


### <a name="op--t--unit--is-adj--ctl"></a><span data-ttu-id="1ac7a-113">OP : 't => [unité](xref:microsoft.quantum.lang-ref.unit)  est Adj + CTL</span><span class="sxs-lookup"><span data-stu-id="1ac7a-113">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="1ac7a-114">Opération à appliquer de manière conditionnelle.</span><span class="sxs-lookup"><span data-stu-id="1ac7a-114">An operation to be conditionally applied.</span></span>


### <a name="target--t"></a><span data-ttu-id="1ac7a-115">cible : 't</span><span class="sxs-lookup"><span data-stu-id="1ac7a-115">target : 'T</span></span>

<span data-ttu-id="1ac7a-116">Entrée à laquelle l’opération est appliquée.</span><span class="sxs-lookup"><span data-stu-id="1ac7a-116">The input to which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="1ac7a-117">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="1ac7a-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="1ac7a-118">Paramètres de type</span><span class="sxs-lookup"><span data-stu-id="1ac7a-118">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="1ac7a-119">Peut</span><span class="sxs-lookup"><span data-stu-id="1ac7a-119">'T</span></span>

<span data-ttu-id="1ac7a-120">Type d’entrée de l’opération à appliquer de façon conditionnelle.</span><span class="sxs-lookup"><span data-stu-id="1ac7a-120">The input type of the operation to be conditionally applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="1ac7a-121">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="1ac7a-121">See Also</span></span>

- [<span data-ttu-id="1ac7a-122">Microsoft. Quantum. Canon. ApplyIfOneC</span><span class="sxs-lookup"><span data-stu-id="1ac7a-122">Microsoft.Quantum.Canon.ApplyIfOneC</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfOneC)
- [<span data-ttu-id="1ac7a-123">Microsoft. Quantum. Canon. ApplyIfOneA</span><span class="sxs-lookup"><span data-stu-id="1ac7a-123">Microsoft.Quantum.Canon.ApplyIfOneA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfOneA)
- [<span data-ttu-id="1ac7a-124">Microsoft. Quantum. Canon. ApplyIfOneCA</span><span class="sxs-lookup"><span data-stu-id="1ac7a-124">Microsoft.Quantum.Canon.ApplyIfOneCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfOneCA)