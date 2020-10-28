---
uid: Microsoft.Quantum.Canon.CControlled
title: CControlled fonction)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: CControlled
qsharp.summary: Given an operation op, returns a new operation which applies the op if a classical control bit is true. If `false`, nothing happens.
ms.openlocfilehash: a155b00806b17258b3f87629659bc7d786e4e11d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92704411"
---
# <a name="ccontrolled-function"></a><span data-ttu-id="0dafa-102">CControlled fonction)</span><span class="sxs-lookup"><span data-stu-id="0dafa-102">CControlled function</span></span>

<span data-ttu-id="0dafa-103">Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="0dafa-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="0dafa-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="0dafa-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="0dafa-105">Dans le cas d’une opération op, retourne une nouvelle opération qui applique le op si un bit de contrôle classique a la valeur true.</span><span class="sxs-lookup"><span data-stu-id="0dafa-105">Given an operation op, returns a new operation which applies the op if a classical control bit is true.</span></span> <span data-ttu-id="0dafa-106">Si la `false` valeur est, rien ne se produit.</span><span class="sxs-lookup"><span data-stu-id="0dafa-106">If `false`, nothing happens.</span></span>

```qsharp
function CControlled<'T> (op : ('T => Unit)) : ((Bool, 'T) => Unit)
```


## <a name="input"></a><span data-ttu-id="0dafa-107">Entrée</span><span class="sxs-lookup"><span data-stu-id="0dafa-107">Input</span></span>

### <a name="op--t--unit"></a><span data-ttu-id="0dafa-108">OP : 't => [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="0dafa-108">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="0dafa-109">Opération à appliquer de manière conditionnelle.</span><span class="sxs-lookup"><span data-stu-id="0dafa-109">An operation to be conditionally applied.</span></span>



## <a name="output--boolt--unit"></a><span data-ttu-id="0dafa-110">Sortie : ([bool](xref:microsoft.quantum.lang-ref.bool), 't) => [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="0dafa-110">Output : ([Bool](xref:microsoft.quantum.lang-ref.bool),'T) => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="0dafa-111">Nouvelle opération qui est op si le bit de contrôle classique a la valeur true.</span><span class="sxs-lookup"><span data-stu-id="0dafa-111">A new operation which is op if the classical control bit is true.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="0dafa-112">Paramètres de type</span><span class="sxs-lookup"><span data-stu-id="0dafa-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="0dafa-113">Peut</span><span class="sxs-lookup"><span data-stu-id="0dafa-113">'T</span></span>

<span data-ttu-id="0dafa-114">Type d’entrée de l’opération à appliquer de façon conditionnelle.</span><span class="sxs-lookup"><span data-stu-id="0dafa-114">The input type of the operation to be conditionally applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="0dafa-115">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="0dafa-115">See Also</span></span>

- [<span data-ttu-id="0dafa-116">Microsoft. Quantum. Canon. CControlledC</span><span class="sxs-lookup"><span data-stu-id="0dafa-116">Microsoft.Quantum.Canon.CControlledC</span></span>](xref:Microsoft.Quantum.Canon.CControlledC)
- [<span data-ttu-id="0dafa-117">Microsoft. Quantum. Canon. CControlledA</span><span class="sxs-lookup"><span data-stu-id="0dafa-117">Microsoft.Quantum.Canon.CControlledA</span></span>](xref:Microsoft.Quantum.Canon.CControlledA)
- [<span data-ttu-id="0dafa-118">Microsoft. Quantum. Canon. CControlledCA</span><span class="sxs-lookup"><span data-stu-id="0dafa-118">Microsoft.Quantum.Canon.CControlledCA</span></span>](xref:Microsoft.Quantum.Canon.CControlledCA)