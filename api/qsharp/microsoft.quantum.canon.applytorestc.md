---
uid: Microsoft.Quantum.Canon.ApplyToRestC
title: Opération ApplyToRestC
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToRestC
qsharp.summary: Applies an operation to all but the first element of an array.
ms.openlocfilehash: 55e534b7b7673f300b607a8213418c45c8c7c92c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92704699"
---
# <a name="applytorestc-operation"></a><span data-ttu-id="6e353-102">Opération ApplyToRestC</span><span class="sxs-lookup"><span data-stu-id="6e353-102">ApplyToRestC operation</span></span>

<span data-ttu-id="6e353-103">Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="6e353-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="6e353-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="6e353-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="6e353-105">Applique une opération à tous les éléments à l’exception du premier élément d’un tableau.</span><span class="sxs-lookup"><span data-stu-id="6e353-105">Applies an operation to all but the first element of an array.</span></span>

```qsharp
operation ApplyToRestC<'T> (op : ('T[] => Unit is Ctl), targets : 'T[]) : Unit
```


## <a name="description"></a><span data-ttu-id="6e353-106">Description</span><span class="sxs-lookup"><span data-stu-id="6e353-106">Description</span></span>

<span data-ttu-id="6e353-107">Pour une opération donnée `op` et un tableau de cibles `targets` , s’applique `op(Rest(targets))` .</span><span class="sxs-lookup"><span data-stu-id="6e353-107">Given an operation `op` and an array of targets `targets`, applies `op(Rest(targets))`.</span></span>

## <a name="input"></a><span data-ttu-id="6e353-108">Entrée</span><span class="sxs-lookup"><span data-stu-id="6e353-108">Input</span></span>

### <a name="op--t--unit-ctl"></a><span data-ttu-id="6e353-109">OP : 't [] => CTL de l' [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="6e353-109">op : 'T[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>

<span data-ttu-id="6e353-110">Opération à appliquer.</span><span class="sxs-lookup"><span data-stu-id="6e353-110">An operation to be applied.</span></span>


### <a name="targets--t"></a><span data-ttu-id="6e353-111">cibles : 't []</span><span class="sxs-lookup"><span data-stu-id="6e353-111">targets : 'T[]</span></span>

<span data-ttu-id="6e353-112">Tableau de cibles, dont tous les sauf le premier seront appliqués `op` .</span><span class="sxs-lookup"><span data-stu-id="6e353-112">An array of targets, of which all but the first will be applied to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="6e353-113">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="6e353-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="6e353-114">Paramètres de type</span><span class="sxs-lookup"><span data-stu-id="6e353-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="6e353-115">Peut</span><span class="sxs-lookup"><span data-stu-id="6e353-115">'T</span></span>

<span data-ttu-id="6e353-116">Type d’entrée de l’opération à appliquer.</span><span class="sxs-lookup"><span data-stu-id="6e353-116">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="6e353-117">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="6e353-117">See Also</span></span>

- [<span data-ttu-id="6e353-118">Microsoft. Quantum. Canon. ApplyToRest</span><span class="sxs-lookup"><span data-stu-id="6e353-118">Microsoft.Quantum.Canon.ApplyToRest</span></span>](xref:Microsoft.Quantum.Canon.ApplyToRest)
- [<span data-ttu-id="6e353-119">Microsoft. Quantum. Canon. ApplyToRestA</span><span class="sxs-lookup"><span data-stu-id="6e353-119">Microsoft.Quantum.Canon.ApplyToRestA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToRestA)
- [<span data-ttu-id="6e353-120">Microsoft. Quantum. Canon. ApplyToRestCA</span><span class="sxs-lookup"><span data-stu-id="6e353-120">Microsoft.Quantum.Canon.ApplyToRestCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToRestCA)