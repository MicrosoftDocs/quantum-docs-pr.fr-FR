---
uid: Microsoft.Quantum.Canon.CControlledC
title: CControlledC fonction)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: CControlledC
qsharp.summary: Given an operation op, returns a new operation which applies the op if a classical control bit is true. If `false`, nothing happens. The modifier `C` indicates that the operation is controllable.
ms.openlocfilehash: e5975455385e182236d7e2864e26ca00795a40c6
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92704403"
---
# <a name="ccontrolledc-function"></a><span data-ttu-id="c829c-102">CControlledC fonction)</span><span class="sxs-lookup"><span data-stu-id="c829c-102">CControlledC function</span></span>

<span data-ttu-id="c829c-103">Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="c829c-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="c829c-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="c829c-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="c829c-105">Dans le cas d’une opération op, retourne une nouvelle opération qui applique le op si un bit de contrôle classique a la valeur true.</span><span class="sxs-lookup"><span data-stu-id="c829c-105">Given an operation op, returns a new operation which applies the op if a classical control bit is true.</span></span> <span data-ttu-id="c829c-106">Si la `false` valeur est, rien ne se produit.</span><span class="sxs-lookup"><span data-stu-id="c829c-106">If `false`, nothing happens.</span></span>
<span data-ttu-id="c829c-107">Le modificateur `C` indique que l’opération est contrôlable.</span><span class="sxs-lookup"><span data-stu-id="c829c-107">The modifier `C` indicates that the operation is controllable.</span></span>

```qsharp
function CControlledC<'T> (op : ('T => Unit is Ctl)) : ((Bool, 'T) => Unit is Ctl)
```


## <a name="input"></a><span data-ttu-id="c829c-108">Entrée</span><span class="sxs-lookup"><span data-stu-id="c829c-108">Input</span></span>

### <a name="op--t--unit-ctl"></a><span data-ttu-id="c829c-109">OP : t => CTL de l' [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="c829c-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>

<span data-ttu-id="c829c-110">Opération à appliquer de manière conditionnelle.</span><span class="sxs-lookup"><span data-stu-id="c829c-110">An operation to be conditionally applied.</span></span>



## <a name="output--boolt--unit-ctl"></a><span data-ttu-id="c829c-111">Sortie : ([bool](xref:microsoft.quantum.lang-ref.bool), 't) => CTL de l' [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="c829c-111">Output : ([Bool](xref:microsoft.quantum.lang-ref.bool),'T) => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>

<span data-ttu-id="c829c-112">Nouvelle opération qui est op si le bit de contrôle classique a la valeur true.</span><span class="sxs-lookup"><span data-stu-id="c829c-112">A new operation which is op if the classical control bit is true.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="c829c-113">Paramètres de type</span><span class="sxs-lookup"><span data-stu-id="c829c-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="c829c-114">Peut</span><span class="sxs-lookup"><span data-stu-id="c829c-114">'T</span></span>

<span data-ttu-id="c829c-115">Type d’entrée de l’opération à appliquer de façon conditionnelle.</span><span class="sxs-lookup"><span data-stu-id="c829c-115">The input type of the operation to be conditionally applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="c829c-116">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="c829c-116">See Also</span></span>

- [<span data-ttu-id="c829c-117">Microsoft. Quantum. Canon. CControlled</span><span class="sxs-lookup"><span data-stu-id="c829c-117">Microsoft.Quantum.Canon.CControlled</span></span>](xref:Microsoft.Quantum.Canon.CControlled)