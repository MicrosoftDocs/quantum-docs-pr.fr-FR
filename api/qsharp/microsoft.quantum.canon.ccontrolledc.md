---
uid: Microsoft.Quantum.Canon.CControlledC
title: CControlledC fonction)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: CControlledC
qsharp.summary: Given an operation op, returns a new operation which applies the op if a classical control bit is true. If `false`, nothing happens. The modifier `C` indicates that the operation is controllable.
ms.openlocfilehash: 25ac2b35047b1c33a89149eae6d40f6f7ae3b454
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96216912"
---
# <a name="ccontrolledc-function"></a><span data-ttu-id="ae21e-102">CControlledC fonction)</span><span class="sxs-lookup"><span data-stu-id="ae21e-102">CControlledC function</span></span>

<span data-ttu-id="ae21e-103">Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="ae21e-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="ae21e-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="ae21e-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="ae21e-105">Dans le cas d’une opération op, retourne une nouvelle opération qui applique le op si un bit de contrôle classique a la valeur true.</span><span class="sxs-lookup"><span data-stu-id="ae21e-105">Given an operation op, returns a new operation which applies the op if a classical control bit is true.</span></span> <span data-ttu-id="ae21e-106">Si la `false` valeur est, rien ne se produit.</span><span class="sxs-lookup"><span data-stu-id="ae21e-106">If `false`, nothing happens.</span></span>
<span data-ttu-id="ae21e-107">Le modificateur `C` indique que l’opération est contrôlable.</span><span class="sxs-lookup"><span data-stu-id="ae21e-107">The modifier `C` indicates that the operation is controllable.</span></span>

```qsharp
function CControlledC<'T> (op : ('T => Unit is Ctl)) : ((Bool, 'T) => Unit is Ctl)
```


## <a name="input"></a><span data-ttu-id="ae21e-108">Entrée</span><span class="sxs-lookup"><span data-stu-id="ae21e-108">Input</span></span>

### <a name="op--t--unit--is-ctl"></a><span data-ttu-id="ae21e-109">OP : t => [unité](xref:microsoft.quantum.lang-ref.unit)  est CTL</span><span class="sxs-lookup"><span data-stu-id="ae21e-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="ae21e-110">Opération à appliquer de manière conditionnelle.</span><span class="sxs-lookup"><span data-stu-id="ae21e-110">An operation to be conditionally applied.</span></span>



## <a name="output--boolt--unit--is-ctl"></a><span data-ttu-id="ae21e-111">Sortie : ([bool](xref:microsoft.quantum.lang-ref.bool), 't) => [unité](xref:microsoft.quantum.lang-ref.unit)  est CTL</span><span class="sxs-lookup"><span data-stu-id="ae21e-111">Output : ([Bool](xref:microsoft.quantum.lang-ref.bool),'T) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="ae21e-112">Nouvelle opération qui est op si le bit de contrôle classique a la valeur true.</span><span class="sxs-lookup"><span data-stu-id="ae21e-112">A new operation which is op if the classical control bit is true.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="ae21e-113">Paramètres de type</span><span class="sxs-lookup"><span data-stu-id="ae21e-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="ae21e-114">Peut</span><span class="sxs-lookup"><span data-stu-id="ae21e-114">'T</span></span>

<span data-ttu-id="ae21e-115">Type d’entrée de l’opération à appliquer de façon conditionnelle.</span><span class="sxs-lookup"><span data-stu-id="ae21e-115">The input type of the operation to be conditionally applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="ae21e-116">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="ae21e-116">See Also</span></span>

- [<span data-ttu-id="ae21e-117">Microsoft. Quantum. Canon. CControlled</span><span class="sxs-lookup"><span data-stu-id="ae21e-117">Microsoft.Quantum.Canon.CControlled</span></span>](xref:Microsoft.Quantum.Canon.CControlled)