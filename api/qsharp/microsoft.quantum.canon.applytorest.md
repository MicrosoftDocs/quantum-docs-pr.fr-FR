---
uid: Microsoft.Quantum.Canon.ApplyToRest
title: Opération ApplyToRest
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToRest
qsharp.summary: Applies an operation to all but the first element of an array.
ms.openlocfilehash: f18536a056935220feedc4ea50531c5def61d650
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850506"
---
# <a name="applytorest-operation"></a><span data-ttu-id="31223-102">Opération ApplyToRest</span><span class="sxs-lookup"><span data-stu-id="31223-102">ApplyToRest operation</span></span>

<span data-ttu-id="31223-103">Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="31223-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="31223-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="31223-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="31223-105">Applique une opération à tous les éléments à l’exception du premier élément d’un tableau.</span><span class="sxs-lookup"><span data-stu-id="31223-105">Applies an operation to all but the first element of an array.</span></span>

```qsharp
operation ApplyToRest<'T> (op : ('T[] => Unit), targets : 'T[]) : Unit
```


## <a name="description"></a><span data-ttu-id="31223-106">Description</span><span class="sxs-lookup"><span data-stu-id="31223-106">Description</span></span>

<span data-ttu-id="31223-107">Pour une opération donnée `op` et un tableau de cibles `targets` , s’applique `op(Rest(targets))` .</span><span class="sxs-lookup"><span data-stu-id="31223-107">Given an operation `op` and an array of targets `targets`, applies `op(Rest(targets))`.</span></span>

## <a name="input"></a><span data-ttu-id="31223-108">Entrée</span><span class="sxs-lookup"><span data-stu-id="31223-108">Input</span></span>

### <a name="op--t--unit"></a><span data-ttu-id="31223-109">OP : 't [] => [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="31223-109">op : 'T[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="31223-110">Opération à appliquer.</span><span class="sxs-lookup"><span data-stu-id="31223-110">An operation to be applied.</span></span>


### <a name="targets--t"></a><span data-ttu-id="31223-111">cibles : 't []</span><span class="sxs-lookup"><span data-stu-id="31223-111">targets : 'T[]</span></span>

<span data-ttu-id="31223-112">Tableau de cibles, dont tous les sauf le premier seront appliqués `op` .</span><span class="sxs-lookup"><span data-stu-id="31223-112">An array of targets, of which all but the first will be applied to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="31223-113">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="31223-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="31223-114">Paramètres de type</span><span class="sxs-lookup"><span data-stu-id="31223-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="31223-115">Peut</span><span class="sxs-lookup"><span data-stu-id="31223-115">'T</span></span>

<span data-ttu-id="31223-116">Type d’entrée de l’opération à appliquer.</span><span class="sxs-lookup"><span data-stu-id="31223-116">The input type of the operation to be applied.</span></span>

## <a name="example"></a><span data-ttu-id="31223-117">Exemple</span><span class="sxs-lookup"><span data-stu-id="31223-117">Example</span></span>

<span data-ttu-id="31223-118">Les extraits de code Q # suivants sont équivalents :</span><span class="sxs-lookup"><span data-stu-id="31223-118">The following Q# snippets are equivalent:</span></span>

```qsharp
ApplyToRest(ApplyCNOTChain, register);
ApplyCNOTChain(Rest(register));
```

## <a name="see-also"></a><span data-ttu-id="31223-119">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="31223-119">See Also</span></span>

- [<span data-ttu-id="31223-120">Microsoft. Quantum. Canon. ApplyToRestA</span><span class="sxs-lookup"><span data-stu-id="31223-120">Microsoft.Quantum.Canon.ApplyToRestA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToRestA)
- [<span data-ttu-id="31223-121">Microsoft. Quantum. Canon. ApplyToRestC</span><span class="sxs-lookup"><span data-stu-id="31223-121">Microsoft.Quantum.Canon.ApplyToRestC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToRestC)
- [<span data-ttu-id="31223-122">Microsoft. Quantum. Canon. ApplyToRestCA</span><span class="sxs-lookup"><span data-stu-id="31223-122">Microsoft.Quantum.Canon.ApplyToRestCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToRestCA)