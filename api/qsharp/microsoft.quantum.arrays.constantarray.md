---
uid: Microsoft.Quantum.Arrays.ConstantArray
title: ConstantArray fonction)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: ConstantArray
qsharp.summary: Creates an array of given length with all elements equal to given value.
ms.openlocfilehash: a3ad8a18856888a0ca6f9dd691242156b0c044d8
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846219"
---
# <a name="constantarray-function"></a><span data-ttu-id="bbc12-102">ConstantArray fonction)</span><span class="sxs-lookup"><span data-stu-id="bbc12-102">ConstantArray function</span></span>

<span data-ttu-id="bbc12-103">Espace de noms : [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="bbc12-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="bbc12-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="bbc12-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="bbc12-105">Crée un tableau de longueur donnée avec tous les éléments égaux à la valeur donnée.</span><span class="sxs-lookup"><span data-stu-id="bbc12-105">Creates an array of given length with all elements equal to given value.</span></span>

```qsharp
function ConstantArray<'T> (length : Int, value : 'T) : 'T[]
```


## <a name="input"></a><span data-ttu-id="bbc12-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="bbc12-106">Input</span></span>

### <a name="length--int"></a><span data-ttu-id="bbc12-107">Longueur : [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="bbc12-107">length : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="bbc12-108">Longueur du nouveau tableau.</span><span class="sxs-lookup"><span data-stu-id="bbc12-108">Length of the new array.</span></span>


### <a name="value--t"></a><span data-ttu-id="bbc12-109">valeur : 't</span><span class="sxs-lookup"><span data-stu-id="bbc12-109">value : 'T</span></span>

<span data-ttu-id="bbc12-110">Valeur de chaque élément du nouveau tableau.</span><span class="sxs-lookup"><span data-stu-id="bbc12-110">The value of each element of the new array.</span></span>



## <a name="output--t"></a><span data-ttu-id="bbc12-111">Sortie : 't []</span><span class="sxs-lookup"><span data-stu-id="bbc12-111">Output : 'T[]</span></span>

<span data-ttu-id="bbc12-112">Nouveau tableau de longueur `length` , de telle sorte que chaque élément est `value` .</span><span class="sxs-lookup"><span data-stu-id="bbc12-112">A new array of length `length`, such that every element is `value`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="bbc12-113">Paramètres de type</span><span class="sxs-lookup"><span data-stu-id="bbc12-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="bbc12-114">Peut</span><span class="sxs-lookup"><span data-stu-id="bbc12-114">'T</span></span>



## <a name="example"></a><span data-ttu-id="bbc12-115">Exemple</span><span class="sxs-lookup"><span data-stu-id="bbc12-115">Example</span></span>

<span data-ttu-id="bbc12-116">Le code suivant crée un tableau de 3 valeurs booléennes, chacune d’elles étant égale à `true` :</span><span class="sxs-lookup"><span data-stu-id="bbc12-116">The following code creates an array of 3 Boolean values, each equal to `true`:</span></span>

```qsharp
let array = ConstantArray(3, true);
```