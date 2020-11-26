---
uid: Microsoft.Quantum.Canon.ApplyIfOneC
title: Opération ApplyIfOneC
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfOneC
qsharp.summary: Applies a controllable operation conditioned on a classical result value being one.
ms.openlocfilehash: 24a00d83c1bbe6b07adb27c58fc70bc76af0a910
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96209415"
---
# <a name="applyifonec-operation"></a><span data-ttu-id="4b695-102">Opération ApplyIfOneC</span><span class="sxs-lookup"><span data-stu-id="4b695-102">ApplyIfOneC operation</span></span>

<span data-ttu-id="4b695-103">Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="4b695-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="4b695-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="4b695-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="4b695-105">Applique une opération contrôlable conditionnée sur une valeur de résultat classique qui en est une.</span><span class="sxs-lookup"><span data-stu-id="4b695-105">Applies a controllable operation conditioned on a classical result value being one.</span></span>

```qsharp
operation ApplyIfOneC<'T> (result : Result, (op : ('T => Unit is Ctl), target : 'T)) : Unit is Ctl
```


## <a name="description"></a><span data-ttu-id="4b695-106">Description</span><span class="sxs-lookup"><span data-stu-id="4b695-106">Description</span></span>

<span data-ttu-id="4b695-107">Pour une opération donnée `op` et une valeur de résultat `result` , s’applique `op` à `target` si `result` est `One` .</span><span class="sxs-lookup"><span data-stu-id="4b695-107">Given an operation `op` and a result value `result`, applies `op` to the `target` if `result` is `One`.</span></span> <span data-ttu-id="4b695-108">Si `Zero` , rien ne se passe au `target` .</span><span class="sxs-lookup"><span data-stu-id="4b695-108">If `Zero`, nothing happens to the `target`.</span></span>
<span data-ttu-id="4b695-109">Le suffixe `C` indique que l’opération à appliquer est contrôlable.</span><span class="sxs-lookup"><span data-stu-id="4b695-109">The suffix `C` indicates that the operation to be applied is controllable.</span></span>

## <a name="input"></a><span data-ttu-id="4b695-110">Entrée</span><span class="sxs-lookup"><span data-stu-id="4b695-110">Input</span></span>

### <a name="result--__invalidresult__"></a><span data-ttu-id="4b695-111">résultat : __non <Result> valide__</span><span class="sxs-lookup"><span data-stu-id="4b695-111">result : __invalid<Result>__</span></span>

<span data-ttu-id="4b695-112">Résultat de mesure qui contrôle si l’opération est appliquée ou non.</span><span class="sxs-lookup"><span data-stu-id="4b695-112">A measurement result that controls whether op is applied or not.</span></span>


### <a name="op--t--unit--is-ctl"></a><span data-ttu-id="4b695-113">OP : t => [unité](xref:microsoft.quantum.lang-ref.unit)  est CTL</span><span class="sxs-lookup"><span data-stu-id="4b695-113">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="4b695-114">Opération à appliquer de manière conditionnelle.</span><span class="sxs-lookup"><span data-stu-id="4b695-114">An operation to be conditionally applied.</span></span>


### <a name="target--t"></a><span data-ttu-id="4b695-115">cible : 't</span><span class="sxs-lookup"><span data-stu-id="4b695-115">target : 'T</span></span>

<span data-ttu-id="4b695-116">Entrée à laquelle l’opération est appliquée.</span><span class="sxs-lookup"><span data-stu-id="4b695-116">The input to which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="4b695-117">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="4b695-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="4b695-118">Paramètres de type</span><span class="sxs-lookup"><span data-stu-id="4b695-118">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="4b695-119">Peut</span><span class="sxs-lookup"><span data-stu-id="4b695-119">'T</span></span>

<span data-ttu-id="4b695-120">Type d’entrée de l’opération à appliquer de façon conditionnelle.</span><span class="sxs-lookup"><span data-stu-id="4b695-120">The input type of the operation to be conditionally applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="4b695-121">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="4b695-121">See Also</span></span>

- [<span data-ttu-id="4b695-122">Microsoft. Quantum. Canon. ApplyIfOneC</span><span class="sxs-lookup"><span data-stu-id="4b695-122">Microsoft.Quantum.Canon.ApplyIfOneC</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfOneC)
- [<span data-ttu-id="4b695-123">Microsoft. Quantum. Canon. ApplyIfOneA</span><span class="sxs-lookup"><span data-stu-id="4b695-123">Microsoft.Quantum.Canon.ApplyIfOneA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfOneA)
- [<span data-ttu-id="4b695-124">Microsoft. Quantum. Canon. ApplyIfOneCA</span><span class="sxs-lookup"><span data-stu-id="4b695-124">Microsoft.Quantum.Canon.ApplyIfOneCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfOneCA)