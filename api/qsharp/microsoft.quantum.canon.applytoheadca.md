---
uid: Microsoft.Quantum.Canon.ApplyToHeadCA
title: Opération ApplyToHeadCA
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToHeadCA
qsharp.summary: Applies an operation to the first element of an array.
ms.openlocfilehash: 1bb24006a2d52167dfc7a7871cfbf5a4378d1cb7
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850611"
---
# <a name="applytoheadca-operation"></a><span data-ttu-id="965c7-102">Opération ApplyToHeadCA</span><span class="sxs-lookup"><span data-stu-id="965c7-102">ApplyToHeadCA operation</span></span>

<span data-ttu-id="965c7-103">Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="965c7-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="965c7-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="965c7-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="965c7-105">Applique une opération au premier élément d’un tableau.</span><span class="sxs-lookup"><span data-stu-id="965c7-105">Applies an operation to the first element of an array.</span></span>

```qsharp
operation ApplyToHeadCA<'T> (op : ('T => Unit is Adj + Ctl), targets : 'T[]) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="965c7-106">Description</span><span class="sxs-lookup"><span data-stu-id="965c7-106">Description</span></span>

<span data-ttu-id="965c7-107">Pour une opération donnée `op` et un tableau de cibles `targets` , s’applique `op(Head(targets))` .</span><span class="sxs-lookup"><span data-stu-id="965c7-107">Given an operation `op` and an array of targets `targets`, applies `op(Head(targets))`.</span></span>

## <a name="input"></a><span data-ttu-id="965c7-108">Entrée</span><span class="sxs-lookup"><span data-stu-id="965c7-108">Input</span></span>

### <a name="op--t--unit--is-adj--ctl"></a><span data-ttu-id="965c7-109">OP : 't => [unité](xref:microsoft.quantum.lang-ref.unit)  est Adj + CTL</span><span class="sxs-lookup"><span data-stu-id="965c7-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="965c7-110">Opération à appliquer.</span><span class="sxs-lookup"><span data-stu-id="965c7-110">An operation to be applied.</span></span>


### <a name="targets--t"></a><span data-ttu-id="965c7-111">cibles : 't []</span><span class="sxs-lookup"><span data-stu-id="965c7-111">targets : 'T[]</span></span>

<span data-ttu-id="965c7-112">Tableau de cibles, auquel le premier sera appliqué `op` .</span><span class="sxs-lookup"><span data-stu-id="965c7-112">An array of targets, of which the first will be applied to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="965c7-113">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="965c7-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="965c7-114">Paramètres de type</span><span class="sxs-lookup"><span data-stu-id="965c7-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="965c7-115">Peut</span><span class="sxs-lookup"><span data-stu-id="965c7-115">'T</span></span>

<span data-ttu-id="965c7-116">Type d’entrée de l’opération à appliquer.</span><span class="sxs-lookup"><span data-stu-id="965c7-116">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="965c7-117">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="965c7-117">See Also</span></span>

- [<span data-ttu-id="965c7-118">Microsoft. Quantum. Canon. ApplyToHead</span><span class="sxs-lookup"><span data-stu-id="965c7-118">Microsoft.Quantum.Canon.ApplyToHead</span></span>](xref:Microsoft.Quantum.Canon.ApplyToHead)
- [<span data-ttu-id="965c7-119">Microsoft. Quantum. Canon. ApplyToHeadA</span><span class="sxs-lookup"><span data-stu-id="965c7-119">Microsoft.Quantum.Canon.ApplyToHeadA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToHeadA)
- [<span data-ttu-id="965c7-120">Microsoft. Quantum. Canon. ApplyToHeadC</span><span class="sxs-lookup"><span data-stu-id="965c7-120">Microsoft.Quantum.Canon.ApplyToHeadC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToHeadC)