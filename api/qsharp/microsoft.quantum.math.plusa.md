---
uid: Microsoft.Quantum.Math.PlusA
title: Fonction plus
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: PlusA
qsharp.summary: Returns the sum (concatenation) of two inputs.
ms.openlocfilehash: 14e9bfdbe4b70b4730e5bfc64a0ee81ab3cecaaf
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842713"
---
# <a name="plusa-function"></a><span data-ttu-id="2734f-102">Fonction plus</span><span class="sxs-lookup"><span data-stu-id="2734f-102">PlusA function</span></span>

<span data-ttu-id="2734f-103">Espace de noms : [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="2734f-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="2734f-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="2734f-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="2734f-105">Retourne la somme (concaténation) de deux entrées.</span><span class="sxs-lookup"><span data-stu-id="2734f-105">Returns the sum (concatenation) of two inputs.</span></span>

```qsharp
function PlusA<'Element> (a : 'Element[], b : 'Element[]) : 'Element[]
```


## <a name="input"></a><span data-ttu-id="2734f-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="2734f-106">Input</span></span>

### <a name="a--element"></a><span data-ttu-id="2734f-107">r : 'élément []</span><span class="sxs-lookup"><span data-stu-id="2734f-107">a : 'Element[]</span></span>

<span data-ttu-id="2734f-108">Première entrée $a $ à additionner.</span><span class="sxs-lookup"><span data-stu-id="2734f-108">The first input $a$ to be summed.</span></span>


### <a name="b--element"></a><span data-ttu-id="2734f-109">b : 'élément []</span><span class="sxs-lookup"><span data-stu-id="2734f-109">b : 'Element[]</span></span>

<span data-ttu-id="2734f-110">Deuxième entrée $b $ à additionner.</span><span class="sxs-lookup"><span data-stu-id="2734f-110">The second input $b$ to be summed.</span></span>



## <a name="output--element"></a><span data-ttu-id="2734f-111">Sortie : 'Element []</span><span class="sxs-lookup"><span data-stu-id="2734f-111">Output : 'Element[]</span></span>

<span data-ttu-id="2734f-112">Somme $a + b $.</span><span class="sxs-lookup"><span data-stu-id="2734f-112">The sum $a + b$.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="2734f-113">Paramètres de type</span><span class="sxs-lookup"><span data-stu-id="2734f-113">Type Parameters</span></span>

### <a name="element"></a><span data-ttu-id="2734f-114">', Élément</span><span class="sxs-lookup"><span data-stu-id="2734f-114">'Element</span></span>

<span data-ttu-id="2734f-115">Type de chaque élément dans chacun des deux tableaux d’entrée.</span><span class="sxs-lookup"><span data-stu-id="2734f-115">The type of each element in each of the two input arrays.</span></span>