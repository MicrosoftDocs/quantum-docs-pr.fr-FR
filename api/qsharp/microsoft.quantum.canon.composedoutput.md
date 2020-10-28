---
uid: Microsoft.Quantum.Canon.ComposedOutput
title: ComposedOutput fonction)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ComposedOutput
qsharp.summary: Returns the output of the composition of `inner` and `outer` for a given input.
ms.openlocfilehash: 4da66616692055a7d60abbf1fac6e6799806675d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92704350"
---
# <a name="composedoutput-function"></a><span data-ttu-id="27493-102">ComposedOutput fonction)</span><span class="sxs-lookup"><span data-stu-id="27493-102">ComposedOutput function</span></span>

<span data-ttu-id="27493-103">Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="27493-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="27493-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="27493-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="27493-105">Retourne la sortie de la composition de `inner` et `outer` pour une entrée donnée.</span><span class="sxs-lookup"><span data-stu-id="27493-105">Returns the output of the composition of `inner` and `outer` for a given input.</span></span>

```qsharp
function ComposedOutput<'T, 'U, 'V> (outer : ('U -> 'V), inner : ('T -> 'U), target : 'T) : 'V
```


## <a name="input"></a><span data-ttu-id="27493-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="27493-106">Input</span></span>

### <a name="outer--u---v"></a><span data-ttu-id="27493-107">externe : 'U-> 'V</span><span class="sxs-lookup"><span data-stu-id="27493-107">outer : 'U -> 'V</span></span>




### <a name="inner--t---u"></a><span data-ttu-id="27493-108">interne : t-> 'U</span><span class="sxs-lookup"><span data-stu-id="27493-108">inner : 'T -> 'U</span></span>




### <a name="target--t"></a><span data-ttu-id="27493-109">cible : 't</span><span class="sxs-lookup"><span data-stu-id="27493-109">target : 'T</span></span>





## <a name="output--v"></a><span data-ttu-id="27493-110">Sortie : 'V</span><span class="sxs-lookup"><span data-stu-id="27493-110">Output : 'V</span></span>



## <a name="type-parameters"></a><span data-ttu-id="27493-111">Paramètres de type</span><span class="sxs-lookup"><span data-stu-id="27493-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="27493-112">Peut</span><span class="sxs-lookup"><span data-stu-id="27493-112">'T</span></span>


### <a name="u"></a><span data-ttu-id="27493-113">'U</span><span class="sxs-lookup"><span data-stu-id="27493-113">'U</span></span>


### <a name="v"></a><span data-ttu-id="27493-114">'V</span><span class="sxs-lookup"><span data-stu-id="27493-114">'V</span></span>

