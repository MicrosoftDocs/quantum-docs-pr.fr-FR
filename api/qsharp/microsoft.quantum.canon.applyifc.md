---
uid: Microsoft.Quantum.Canon.ApplyIfC
title: Opération ApplyIfC
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfC
qsharp.summary: Applies a controllable operation conditioned on a classical bit.
ms.openlocfilehash: 35430cb7cf491965b7b69ace6d3f41599dbadd51
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96218714"
---
# <a name="applyifc-operation"></a><span data-ttu-id="094cc-102">Opération ApplyIfC</span><span class="sxs-lookup"><span data-stu-id="094cc-102">ApplyIfC operation</span></span>

<span data-ttu-id="094cc-103">Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="094cc-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="094cc-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="094cc-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="094cc-105">Applique une opération contrôlable conditionnée sur un bit classique.</span><span class="sxs-lookup"><span data-stu-id="094cc-105">Applies a controllable operation conditioned on a classical bit.</span></span>

```qsharp
operation ApplyIfC<'T> (op : ('T => Unit is Ctl), bit : Bool, target : 'T) : Unit is Ctl
```


## <a name="description"></a><span data-ttu-id="094cc-106">Description</span><span class="sxs-lookup"><span data-stu-id="094cc-106">Description</span></span>

<span data-ttu-id="094cc-107">Pour une opération donnée `op` et une valeur de bit `bit` , s’applique `op` à `target` si `bit` est `true` .</span><span class="sxs-lookup"><span data-stu-id="094cc-107">Given an operation `op` and a bit value `bit`, applies `op` to the `target` if `bit` is `true`.</span></span> <span data-ttu-id="094cc-108">Si `false` , rien ne se passe au `target` .</span><span class="sxs-lookup"><span data-stu-id="094cc-108">If `false`, nothing happens to the `target`.</span></span>
<span data-ttu-id="094cc-109">Le suffixe `C` indique que l’opération à appliquer est contrôlable.</span><span class="sxs-lookup"><span data-stu-id="094cc-109">The suffix `C` indicates that the operation to be applied is controllable.</span></span>

## <a name="input"></a><span data-ttu-id="094cc-110">Entrée</span><span class="sxs-lookup"><span data-stu-id="094cc-110">Input</span></span>

### <a name="op--t--unit--is-ctl"></a><span data-ttu-id="094cc-111">OP : t => [unité](xref:microsoft.quantum.lang-ref.unit)  est CTL</span><span class="sxs-lookup"><span data-stu-id="094cc-111">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="094cc-112">Opération à appliquer de manière conditionnelle.</span><span class="sxs-lookup"><span data-stu-id="094cc-112">An operation to be conditionally applied.</span></span>


### <a name="bit--bool"></a><span data-ttu-id="094cc-113">bit : [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="094cc-113">bit : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="094cc-114">valeur booléenne qui contrôle si l’opération est appliquée ou non.</span><span class="sxs-lookup"><span data-stu-id="094cc-114">a boolean that controls whether op is applied or not.</span></span>


### <a name="target--t"></a><span data-ttu-id="094cc-115">cible : 't</span><span class="sxs-lookup"><span data-stu-id="094cc-115">target : 'T</span></span>

<span data-ttu-id="094cc-116">Entrée à laquelle l’opération est appliquée.</span><span class="sxs-lookup"><span data-stu-id="094cc-116">The input to which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="094cc-117">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="094cc-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="094cc-118">Paramètres de type</span><span class="sxs-lookup"><span data-stu-id="094cc-118">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="094cc-119">Peut</span><span class="sxs-lookup"><span data-stu-id="094cc-119">'T</span></span>

<span data-ttu-id="094cc-120">Type d’entrée de l’opération à appliquer de façon conditionnelle.</span><span class="sxs-lookup"><span data-stu-id="094cc-120">The input type of the operation to be conditionally applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="094cc-121">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="094cc-121">See Also</span></span>

- [<span data-ttu-id="094cc-122">Microsoft. Quantum. Canon. ApplyIfC</span><span class="sxs-lookup"><span data-stu-id="094cc-122">Microsoft.Quantum.Canon.ApplyIfC</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfC)
- [<span data-ttu-id="094cc-123">Microsoft. Quantum. Canon. ApplyIfA</span><span class="sxs-lookup"><span data-stu-id="094cc-123">Microsoft.Quantum.Canon.ApplyIfA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfA)
- [<span data-ttu-id="094cc-124">Microsoft. Quantum. Canon. ApplyIfCA</span><span class="sxs-lookup"><span data-stu-id="094cc-124">Microsoft.Quantum.Canon.ApplyIfCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfCA)