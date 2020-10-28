---
uid: Microsoft.Quantum.Canon.ApplyIfOneA
title: Opération ApplyIfOneA
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfOneA
qsharp.summary: Applies an adjointable operation conditioned on a classical result value being one.
ms.openlocfilehash: 76c15aba6042c2801ecfe8470e82099c54ba3846
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92705270"
---
# <a name="applyifonea-operation"></a><span data-ttu-id="a06d8-102">Opération ApplyIfOneA</span><span class="sxs-lookup"><span data-stu-id="a06d8-102">ApplyIfOneA operation</span></span>

<span data-ttu-id="a06d8-103">Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="a06d8-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="a06d8-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="a06d8-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="a06d8-105">Applique une opération adjointable conditionnée sur une valeur de résultat classique qui en est une.</span><span class="sxs-lookup"><span data-stu-id="a06d8-105">Applies an adjointable operation conditioned on a classical result value being one.</span></span>

```qsharp
operation ApplyIfOneA<'T> (result : Result, (op : ('T => Unit is Adj), target : 'T)) : Unit
```


## <a name="description"></a><span data-ttu-id="a06d8-106">Description</span><span class="sxs-lookup"><span data-stu-id="a06d8-106">Description</span></span>

<span data-ttu-id="a06d8-107">Pour une opération donnée `op` et une valeur de résultat `result` , s’applique `op` à `target` si `result` est `One` .</span><span class="sxs-lookup"><span data-stu-id="a06d8-107">Given an operation `op` and a result value `result`, applies `op` to the `target` if `result` is `One`.</span></span> <span data-ttu-id="a06d8-108">Si `Zero` , rien ne se passe au `target` .</span><span class="sxs-lookup"><span data-stu-id="a06d8-108">If `Zero`, nothing happens to the `target`.</span></span>
<span data-ttu-id="a06d8-109">Le suffixe `A` indique que l’opération à appliquer est adjointable.</span><span class="sxs-lookup"><span data-stu-id="a06d8-109">The suffix `A` indicates that the operation to be applied is adjointable.</span></span>

## <a name="input"></a><span data-ttu-id="a06d8-110">Entrée</span><span class="sxs-lookup"><span data-stu-id="a06d8-110">Input</span></span>

### <a name="result--__invalidresult__"></a><span data-ttu-id="a06d8-111">résultat : __non <Result> valide__</span><span class="sxs-lookup"><span data-stu-id="a06d8-111">result : __invalid<Result>__</span></span>

<span data-ttu-id="a06d8-112">Résultat de mesure qui contrôle si l’opération est appliquée ou non.</span><span class="sxs-lookup"><span data-stu-id="a06d8-112">A measurement result that controls whether op is applied or not.</span></span>


### <a name="op--t--unit-adj"></a><span data-ttu-id="a06d8-113">OP : t => ajustement d' [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="a06d8-113">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="a06d8-114">Opération à appliquer de manière conditionnelle.</span><span class="sxs-lookup"><span data-stu-id="a06d8-114">An operation to be conditionally applied.</span></span>


### <a name="target--t"></a><span data-ttu-id="a06d8-115">cible : 't</span><span class="sxs-lookup"><span data-stu-id="a06d8-115">target : 'T</span></span>

<span data-ttu-id="a06d8-116">Entrée à laquelle l’opération est appliquée.</span><span class="sxs-lookup"><span data-stu-id="a06d8-116">The input to which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="a06d8-117">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="a06d8-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="a06d8-118">Paramètres de type</span><span class="sxs-lookup"><span data-stu-id="a06d8-118">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="a06d8-119">Peut</span><span class="sxs-lookup"><span data-stu-id="a06d8-119">'T</span></span>

<span data-ttu-id="a06d8-120">Type d’entrée de l’opération à appliquer de façon conditionnelle.</span><span class="sxs-lookup"><span data-stu-id="a06d8-120">The input type of the operation to be conditionally applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="a06d8-121">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="a06d8-121">See Also</span></span>

- [<span data-ttu-id="a06d8-122">Microsoft. Quantum. Canon. ApplyIfOneC</span><span class="sxs-lookup"><span data-stu-id="a06d8-122">Microsoft.Quantum.Canon.ApplyIfOneC</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfOneC)
- [<span data-ttu-id="a06d8-123">Microsoft. Quantum. Canon. ApplyIfOneA</span><span class="sxs-lookup"><span data-stu-id="a06d8-123">Microsoft.Quantum.Canon.ApplyIfOneA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfOneA)
- [<span data-ttu-id="a06d8-124">Microsoft. Quantum. Canon. ApplyIfOneCA</span><span class="sxs-lookup"><span data-stu-id="a06d8-124">Microsoft.Quantum.Canon.ApplyIfOneCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfOneCA)