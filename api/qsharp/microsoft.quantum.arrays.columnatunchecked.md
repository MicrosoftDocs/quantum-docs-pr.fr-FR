---
uid: Microsoft.Quantum.Arrays.ColumnAtUnchecked
title: ColumnAtUnchecked fonction)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: ColumnAtUnchecked
qsharp.summary: This function does not check for matrix shape
ms.openlocfilehash: 17211c1ae1fe12fcadf34a9411f9b0cf0cdcab50
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92706163"
---
# <a name="columnatunchecked-function"></a><span data-ttu-id="22000-102">ColumnAtUnchecked fonction)</span><span class="sxs-lookup"><span data-stu-id="22000-102">ColumnAtUnchecked function</span></span>

<span data-ttu-id="22000-103">Espace de noms : [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="22000-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="22000-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="22000-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="22000-105">Cette fonction ne vérifie pas la forme de la matrice</span><span class="sxs-lookup"><span data-stu-id="22000-105">This function does not check for matrix shape</span></span>

```qsharp
function ColumnAtUnchecked<'T> (column : Int, matrix : 'T[][]) : 'T[]
```


## <a name="description"></a><span data-ttu-id="22000-106">Description</span><span class="sxs-lookup"><span data-stu-id="22000-106">Description</span></span>

<span data-ttu-id="22000-107">Cette fonction peut être utilisée dans d’autres fonctions multidimensionnelles, qui vérifient déjà la matrice d’entrée pour une forme rectangulaire valide.</span><span class="sxs-lookup"><span data-stu-id="22000-107">This function can be used in other multidimensional functions, which already check the input matrix for a valid rectangular shape.</span></span>

## <a name="input"></a><span data-ttu-id="22000-108">Entrée</span><span class="sxs-lookup"><span data-stu-id="22000-108">Input</span></span>

### <a name="column--int"></a><span data-ttu-id="22000-109">colonne : [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="22000-109">column : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>




### <a name="matrix--t"></a><span data-ttu-id="22000-110">matrice : 't [] []</span><span class="sxs-lookup"><span data-stu-id="22000-110">matrix : 'T[][]</span></span>





## <a name="output--t"></a><span data-ttu-id="22000-111">Sortie : 't []</span><span class="sxs-lookup"><span data-stu-id="22000-111">Output : 'T[]</span></span>



## <a name="type-parameters"></a><span data-ttu-id="22000-112">Paramètres de type</span><span class="sxs-lookup"><span data-stu-id="22000-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="22000-113">Peut</span><span class="sxs-lookup"><span data-stu-id="22000-113">'T</span></span>

