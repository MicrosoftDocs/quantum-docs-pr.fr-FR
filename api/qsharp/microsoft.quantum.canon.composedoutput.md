---
uid: Microsoft.Quantum.Canon.ComposedOutput
title: ComposedOutput fonction)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ComposedOutput
qsharp.summary: Returns the output of the composition of `inner` and `outer` for a given input.
ms.openlocfilehash: d39fcd6b2987b3a4f69df13fa83b69a199d6eddb
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840887"
---
# <a name="composedoutput-function"></a><span data-ttu-id="c165b-102">ComposedOutput fonction)</span><span class="sxs-lookup"><span data-stu-id="c165b-102">ComposedOutput function</span></span>

<span data-ttu-id="c165b-103">Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="c165b-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="c165b-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="c165b-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="c165b-105">Retourne la sortie de la composition de `inner` et `outer` pour une entrée donnée.</span><span class="sxs-lookup"><span data-stu-id="c165b-105">Returns the output of the composition of `inner` and `outer` for a given input.</span></span>

```qsharp
function ComposedOutput<'T, 'U, 'V> (outer : ('U -> 'V), inner : ('T -> 'U), target : 'T) : 'V
```


## <a name="input"></a><span data-ttu-id="c165b-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="c165b-106">Input</span></span>

### <a name="outer--u---v"></a><span data-ttu-id="c165b-107">externe : 'U-> 'V</span><span class="sxs-lookup"><span data-stu-id="c165b-107">outer : 'U -> 'V</span></span>




### <a name="inner--t---u"></a><span data-ttu-id="c165b-108">interne : t-> 'U</span><span class="sxs-lookup"><span data-stu-id="c165b-108">inner : 'T -> 'U</span></span>




### <a name="target--t"></a><span data-ttu-id="c165b-109">cible : 't</span><span class="sxs-lookup"><span data-stu-id="c165b-109">target : 'T</span></span>





## <a name="output--v"></a><span data-ttu-id="c165b-110">Sortie : 'V</span><span class="sxs-lookup"><span data-stu-id="c165b-110">Output : 'V</span></span>



## <a name="type-parameters"></a><span data-ttu-id="c165b-111">Paramètres de type</span><span class="sxs-lookup"><span data-stu-id="c165b-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="c165b-112">Peut</span><span class="sxs-lookup"><span data-stu-id="c165b-112">'T</span></span>


### <a name="u"></a><span data-ttu-id="c165b-113">'U</span><span class="sxs-lookup"><span data-stu-id="c165b-113">'U</span></span>


### <a name="v"></a><span data-ttu-id="c165b-114">'V</span><span class="sxs-lookup"><span data-stu-id="c165b-114">'V</span></span>

