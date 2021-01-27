---
uid: Microsoft.Quantum.Canon.CControlledA
title: CControlledA fonction)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: CControlledA
qsharp.summary: Given an operation op, returns a new operation which applies the op if a classical control bit is true. If `false`, nothing happens. The modifier `A` indicates that the operation is adjointable.
ms.openlocfilehash: 823d80182621691f4fa6f42246b3d671f3adfc3a
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840988"
---
# <a name="ccontrolleda-function"></a><span data-ttu-id="2a9d2-102">CControlledA fonction)</span><span class="sxs-lookup"><span data-stu-id="2a9d2-102">CControlledA function</span></span>

<span data-ttu-id="2a9d2-103">Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="2a9d2-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="2a9d2-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="2a9d2-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="2a9d2-105">Dans le cas d’une opération op, retourne une nouvelle opération qui applique le op si un bit de contrôle classique a la valeur true.</span><span class="sxs-lookup"><span data-stu-id="2a9d2-105">Given an operation op, returns a new operation which applies the op if a classical control bit is true.</span></span> <span data-ttu-id="2a9d2-106">Si la `false` valeur est, rien ne se produit.</span><span class="sxs-lookup"><span data-stu-id="2a9d2-106">If `false`, nothing happens.</span></span>
<span data-ttu-id="2a9d2-107">Le modificateur `A` indique que l’opération est adjointable.</span><span class="sxs-lookup"><span data-stu-id="2a9d2-107">The modifier `A` indicates that the operation is adjointable.</span></span>

```qsharp
function CControlledA<'T> (op : ('T => Unit is Adj)) : ((Bool, 'T) => Unit is Adj)
```


## <a name="input"></a><span data-ttu-id="2a9d2-108">Entrée</span><span class="sxs-lookup"><span data-stu-id="2a9d2-108">Input</span></span>

### <a name="op--t--unit--is-adj"></a><span data-ttu-id="2a9d2-109">OP : 'o => [unité](xref:microsoft.quantum.lang-ref.unit)  est adj</span><span class="sxs-lookup"><span data-stu-id="2a9d2-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="2a9d2-110">Opération à appliquer de manière conditionnelle.</span><span class="sxs-lookup"><span data-stu-id="2a9d2-110">An operation to be conditionally applied.</span></span>



## <a name="output--boolt--unit--is-adj"></a><span data-ttu-id="2a9d2-111">Sortie : ([bool](xref:microsoft.quantum.lang-ref.bool), 't) => [unité](xref:microsoft.quantum.lang-ref.unit)  est adj</span><span class="sxs-lookup"><span data-stu-id="2a9d2-111">Output : ([Bool](xref:microsoft.quantum.lang-ref.bool),'T) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="2a9d2-112">Nouvelle opération qui est op si le bit de contrôle classique a la valeur true.</span><span class="sxs-lookup"><span data-stu-id="2a9d2-112">A new operation which is op if the classical control bit is true.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="2a9d2-113">Paramètres de type</span><span class="sxs-lookup"><span data-stu-id="2a9d2-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="2a9d2-114">Peut</span><span class="sxs-lookup"><span data-stu-id="2a9d2-114">'T</span></span>

<span data-ttu-id="2a9d2-115">Type d’entrée de l’opération à appliquer de façon conditionnelle.</span><span class="sxs-lookup"><span data-stu-id="2a9d2-115">The input type of the operation to be conditionally applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="2a9d2-116">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="2a9d2-116">See Also</span></span>

- [<span data-ttu-id="2a9d2-117">Microsoft. Quantum. Canon. CControlled</span><span class="sxs-lookup"><span data-stu-id="2a9d2-117">Microsoft.Quantum.Canon.CControlled</span></span>](xref:Microsoft.Quantum.Canon.CControlled)