---
uid: Microsoft.Quantum.Canon.CControlled
title: CControlled fonction)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: CControlled
qsharp.summary: Given an operation op, returns a new operation which applies the op if a classical control bit is true. If `false`, nothing happens.
ms.openlocfilehash: 76e663e9a4b53c7ed74a1b70da516fb07958923b
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96216894"
---
# <a name="ccontrolled-function"></a><span data-ttu-id="15c7c-102">CControlled fonction)</span><span class="sxs-lookup"><span data-stu-id="15c7c-102">CControlled function</span></span>

<span data-ttu-id="15c7c-103">Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="15c7c-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="15c7c-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="15c7c-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="15c7c-105">Dans le cas d’une opération op, retourne une nouvelle opération qui applique le op si un bit de contrôle classique a la valeur true.</span><span class="sxs-lookup"><span data-stu-id="15c7c-105">Given an operation op, returns a new operation which applies the op if a classical control bit is true.</span></span> <span data-ttu-id="15c7c-106">Si la `false` valeur est, rien ne se produit.</span><span class="sxs-lookup"><span data-stu-id="15c7c-106">If `false`, nothing happens.</span></span>

```qsharp
function CControlled<'T> (op : ('T => Unit)) : ((Bool, 'T) => Unit)
```


## <a name="input"></a><span data-ttu-id="15c7c-107">Entrée</span><span class="sxs-lookup"><span data-stu-id="15c7c-107">Input</span></span>

### <a name="op--t--unit"></a><span data-ttu-id="15c7c-108">OP : 't => [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="15c7c-108">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="15c7c-109">Opération à appliquer de manière conditionnelle.</span><span class="sxs-lookup"><span data-stu-id="15c7c-109">An operation to be conditionally applied.</span></span>



## <a name="output--boolt--unit"></a><span data-ttu-id="15c7c-110">Sortie : ([bool](xref:microsoft.quantum.lang-ref.bool), 't) => [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="15c7c-110">Output : ([Bool](xref:microsoft.quantum.lang-ref.bool),'T) => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="15c7c-111">Nouvelle opération qui est op si le bit de contrôle classique a la valeur true.</span><span class="sxs-lookup"><span data-stu-id="15c7c-111">A new operation which is op if the classical control bit is true.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="15c7c-112">Paramètres de type</span><span class="sxs-lookup"><span data-stu-id="15c7c-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="15c7c-113">Peut</span><span class="sxs-lookup"><span data-stu-id="15c7c-113">'T</span></span>

<span data-ttu-id="15c7c-114">Type d’entrée de l’opération à appliquer de façon conditionnelle.</span><span class="sxs-lookup"><span data-stu-id="15c7c-114">The input type of the operation to be conditionally applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="15c7c-115">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="15c7c-115">See Also</span></span>

- [<span data-ttu-id="15c7c-116">Microsoft. Quantum. Canon. CControlledC</span><span class="sxs-lookup"><span data-stu-id="15c7c-116">Microsoft.Quantum.Canon.CControlledC</span></span>](xref:Microsoft.Quantum.Canon.CControlledC)
- [<span data-ttu-id="15c7c-117">Microsoft. Quantum. Canon. CControlledA</span><span class="sxs-lookup"><span data-stu-id="15c7c-117">Microsoft.Quantum.Canon.CControlledA</span></span>](xref:Microsoft.Quantum.Canon.CControlledA)
- [<span data-ttu-id="15c7c-118">Microsoft. Quantum. Canon. CControlledCA</span><span class="sxs-lookup"><span data-stu-id="15c7c-118">Microsoft.Quantum.Canon.CControlledCA</span></span>](xref:Microsoft.Quantum.Canon.CControlledCA)