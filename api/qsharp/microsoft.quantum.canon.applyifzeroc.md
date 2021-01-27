---
uid: Microsoft.Quantum.Canon.ApplyIfZeroC
title: Opération ApplyIfZeroC
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfZeroC
qsharp.summary: Applies a controllable operation conditioned on a classical result value being zero.
ms.openlocfilehash: 3876e2baf1b3ad5bbfa0097d468b1e88adf05db4
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841715"
---
# <a name="applyifzeroc-operation"></a><span data-ttu-id="66b57-102">Opération ApplyIfZeroC</span><span class="sxs-lookup"><span data-stu-id="66b57-102">ApplyIfZeroC operation</span></span>

<span data-ttu-id="66b57-103">Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="66b57-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="66b57-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="66b57-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="66b57-105">Applique une opération contrôlable conditionnée sur une valeur de résultat classique égale à zéro.</span><span class="sxs-lookup"><span data-stu-id="66b57-105">Applies a controllable operation conditioned on a classical result value being zero.</span></span>

```qsharp
operation ApplyIfZeroC<'T> (result : Result, (op : ('T => Unit is Ctl), target : 'T)) : Unit is Ctl
```


## <a name="description"></a><span data-ttu-id="66b57-106">Description</span><span class="sxs-lookup"><span data-stu-id="66b57-106">Description</span></span>

<span data-ttu-id="66b57-107">Pour une opération donnée `op` et une valeur de résultat `result` , s’applique `op` à `target` si `result` est `Zero` .</span><span class="sxs-lookup"><span data-stu-id="66b57-107">Given an operation `op` and a result value `result`, applies `op` to the `target` if `result` is `Zero`.</span></span> <span data-ttu-id="66b57-108">Si `One` , rien ne se passe au `target` .</span><span class="sxs-lookup"><span data-stu-id="66b57-108">If `One`, nothing happens to the `target`.</span></span>
<span data-ttu-id="66b57-109">Le suffixe `C` indique que l’opération à appliquer est contrôlable.</span><span class="sxs-lookup"><span data-stu-id="66b57-109">The suffix `C` indicates that the operation to be applied is controllable.</span></span>

## <a name="input"></a><span data-ttu-id="66b57-110">Entrée</span><span class="sxs-lookup"><span data-stu-id="66b57-110">Input</span></span>

### <a name="result--__invalidresult__"></a><span data-ttu-id="66b57-111">résultat : __non <Result> valide__</span><span class="sxs-lookup"><span data-stu-id="66b57-111">result : __invalid<Result>__</span></span>

<span data-ttu-id="66b57-112">Résultat de mesure qui contrôle si l’opération est appliquée ou non.</span><span class="sxs-lookup"><span data-stu-id="66b57-112">A measurement result that controls whether op is applied or not.</span></span>


### <a name="op--t--unit--is-ctl"></a><span data-ttu-id="66b57-113">OP : t => [unité](xref:microsoft.quantum.lang-ref.unit)  est CTL</span><span class="sxs-lookup"><span data-stu-id="66b57-113">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="66b57-114">Opération à appliquer de manière conditionnelle.</span><span class="sxs-lookup"><span data-stu-id="66b57-114">An operation to be conditionally applied.</span></span>


### <a name="target--t"></a><span data-ttu-id="66b57-115">cible : 't</span><span class="sxs-lookup"><span data-stu-id="66b57-115">target : 'T</span></span>

<span data-ttu-id="66b57-116">Entrée à laquelle l’opération est appliquée.</span><span class="sxs-lookup"><span data-stu-id="66b57-116">The input to which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="66b57-117">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="66b57-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="66b57-118">Paramètres de type</span><span class="sxs-lookup"><span data-stu-id="66b57-118">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="66b57-119">Peut</span><span class="sxs-lookup"><span data-stu-id="66b57-119">'T</span></span>

<span data-ttu-id="66b57-120">Type d’entrée de l’opération à appliquer de façon conditionnelle.</span><span class="sxs-lookup"><span data-stu-id="66b57-120">The input type of the operation to be conditionally applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="66b57-121">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="66b57-121">See Also</span></span>

- [<span data-ttu-id="66b57-122">Microsoft. Quantum. Canon. ApplyIfZeroC</span><span class="sxs-lookup"><span data-stu-id="66b57-122">Microsoft.Quantum.Canon.ApplyIfZeroC</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfZeroC)
- [<span data-ttu-id="66b57-123">Microsoft. Quantum. Canon. ApplyIfZeroA</span><span class="sxs-lookup"><span data-stu-id="66b57-123">Microsoft.Quantum.Canon.ApplyIfZeroA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfZeroA)
- [<span data-ttu-id="66b57-124">Microsoft. Quantum. Canon. ApplyIfZeroCA</span><span class="sxs-lookup"><span data-stu-id="66b57-124">Microsoft.Quantum.Canon.ApplyIfZeroCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfZeroCA)