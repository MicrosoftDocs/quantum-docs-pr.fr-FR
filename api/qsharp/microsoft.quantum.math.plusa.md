---
uid: Microsoft.Quantum.Math.PlusA
title: Fonction plus
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: PlusA
qsharp.summary: Returns the sum (concatenation) of two inputs.
ms.openlocfilehash: 0c6fdcf7c59dc5d89bf83e285339046b5ad5a57e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92701311"
---
# <a name="plusa-function"></a><span data-ttu-id="33c02-102">Fonction plus</span><span class="sxs-lookup"><span data-stu-id="33c02-102">PlusA function</span></span>

<span data-ttu-id="33c02-103">Espace de noms : [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="33c02-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="33c02-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="33c02-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="33c02-105">Retourne la somme (concaténation) de deux entrées.</span><span class="sxs-lookup"><span data-stu-id="33c02-105">Returns the sum (concatenation) of two inputs.</span></span>

```qsharp
function PlusA<'Element> (a : 'Element[], b : 'Element[]) : 'Element[]
```


## <a name="input"></a><span data-ttu-id="33c02-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="33c02-106">Input</span></span>

### <a name="a--element"></a><span data-ttu-id="33c02-107">r : 'élément []</span><span class="sxs-lookup"><span data-stu-id="33c02-107">a : 'Element[]</span></span>

<span data-ttu-id="33c02-108">Première entrée $a $ à additionner.</span><span class="sxs-lookup"><span data-stu-id="33c02-108">The first input $a$ to be summed.</span></span>


### <a name="b--element"></a><span data-ttu-id="33c02-109">b : 'élément []</span><span class="sxs-lookup"><span data-stu-id="33c02-109">b : 'Element[]</span></span>

<span data-ttu-id="33c02-110">Deuxième entrée $b $ à additionner.</span><span class="sxs-lookup"><span data-stu-id="33c02-110">The second input $b$ to be summed.</span></span>



## <a name="output--element"></a><span data-ttu-id="33c02-111">Sortie : 'Element []</span><span class="sxs-lookup"><span data-stu-id="33c02-111">Output : 'Element[]</span></span>

<span data-ttu-id="33c02-112">Somme $a + b $.</span><span class="sxs-lookup"><span data-stu-id="33c02-112">The sum $a + b$.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="33c02-113">Paramètres de type</span><span class="sxs-lookup"><span data-stu-id="33c02-113">Type Parameters</span></span>

### <a name="element"></a><span data-ttu-id="33c02-114">', Élément</span><span class="sxs-lookup"><span data-stu-id="33c02-114">'Element</span></span>

<span data-ttu-id="33c02-115">Type de chaque élément dans chacun des deux tableaux d’entrée.</span><span class="sxs-lookup"><span data-stu-id="33c02-115">The type of each element in each of the two input arrays.</span></span>