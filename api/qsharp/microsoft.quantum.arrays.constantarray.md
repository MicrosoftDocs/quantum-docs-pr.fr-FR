---
uid: Microsoft.Quantum.Arrays.ConstantArray
title: ConstantArray fonction)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: ConstantArray
qsharp.summary: Creates an array of given length with all elements equal to given value.
ms.openlocfilehash: 848f18944829d08a10ec602dcb5d99c100c81f76
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92706139"
---
# <a name="constantarray-function"></a><span data-ttu-id="b5980-102">ConstantArray fonction)</span><span class="sxs-lookup"><span data-stu-id="b5980-102">ConstantArray function</span></span>

<span data-ttu-id="b5980-103">Espace de noms : [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="b5980-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="b5980-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="b5980-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="b5980-105">Crée un tableau de longueur donnée avec tous les éléments égaux à la valeur donnée.</span><span class="sxs-lookup"><span data-stu-id="b5980-105">Creates an array of given length with all elements equal to given value.</span></span>

```qsharp
function ConstantArray<'T> (length : Int, value : 'T) : 'T[]
```


## <a name="input"></a><span data-ttu-id="b5980-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="b5980-106">Input</span></span>

### <a name="length--int"></a><span data-ttu-id="b5980-107">Longueur : [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="b5980-107">length : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="b5980-108">Longueur du nouveau tableau.</span><span class="sxs-lookup"><span data-stu-id="b5980-108">Length of the new array.</span></span>


### <a name="value--t"></a><span data-ttu-id="b5980-109">valeur : 't</span><span class="sxs-lookup"><span data-stu-id="b5980-109">value : 'T</span></span>

<span data-ttu-id="b5980-110">Valeur de chaque élément du nouveau tableau.</span><span class="sxs-lookup"><span data-stu-id="b5980-110">The value of each element of the new array.</span></span>



## <a name="output--t"></a><span data-ttu-id="b5980-111">Sortie : 't []</span><span class="sxs-lookup"><span data-stu-id="b5980-111">Output : 'T[]</span></span>

<span data-ttu-id="b5980-112">Nouveau tableau de longueur `length` , de telle sorte que chaque élément est `value` .</span><span class="sxs-lookup"><span data-stu-id="b5980-112">A new array of length `length`, such that every element is `value`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="b5980-113">Paramètres de type</span><span class="sxs-lookup"><span data-stu-id="b5980-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="b5980-114">Peut</span><span class="sxs-lookup"><span data-stu-id="b5980-114">'T</span></span>

