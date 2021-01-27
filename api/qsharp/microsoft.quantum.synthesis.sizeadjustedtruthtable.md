---
uid: Microsoft.Quantum.Synthesis.SizeAdjustedTruthTable
title: SizeAdjustedTruthTable fonction)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: SizeAdjustedTruthTable
qsharp.summary: >-
  Adjusts truth table from array of Booleans according to number of variables

  A new array is returned of length `2^numVars`, possibly requiring to extend `table`'s size with `false` entries or truncating it to `2^numVars` elements.
ms.openlocfilehash: 8d69aa119c25a0f64743fec36c00ecdef2450c44
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98855321"
---
# <a name="sizeadjustedtruthtable-function"></a><span data-ttu-id="eca28-102">SizeAdjustedTruthTable fonction)</span><span class="sxs-lookup"><span data-stu-id="eca28-102">SizeAdjustedTruthTable function</span></span>

<span data-ttu-id="eca28-103">Espace de noms : [Microsoft. Quantum. Synthesis](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="eca28-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="eca28-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="eca28-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="eca28-105">Ajuste la table de vérité à partir d’un tableau de valeurs booléennes en fonction du nombre de variables</span><span class="sxs-lookup"><span data-stu-id="eca28-105">Adjusts truth table from array of Booleans according to number of variables</span></span>

<span data-ttu-id="eca28-106">Un nouveau tableau est retourné de longueur `2^numVars` , ce qui peut nécessiter l’extension de `table` la taille de dans les `false` entrées ou sa troncation aux `2^numVars` éléments.</span><span class="sxs-lookup"><span data-stu-id="eca28-106">A new array is returned of length `2^numVars`, possibly requiring to extend `table`'s size with `false` entries or truncating it to `2^numVars` elements.</span></span>

```qsharp
function SizeAdjustedTruthTable (table : Bool[], numVars : Int) : Bool[]
```


## <a name="input"></a><span data-ttu-id="eca28-107">Entrée</span><span class="sxs-lookup"><span data-stu-id="eca28-107">Input</span></span>

### <a name="table--bool"></a><span data-ttu-id="eca28-108">table : [bool](xref:microsoft.quantum.lang-ref.bool)[]</span><span class="sxs-lookup"><span data-stu-id="eca28-108">table : [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span></span>

<span data-ttu-id="eca28-109">Table de vérité en tant que tableau de valeurs de vérité</span><span class="sxs-lookup"><span data-stu-id="eca28-109">Truth table as array of truth values</span></span>


### <a name="numvars--int"></a><span data-ttu-id="eca28-110">numVars : [entier](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="eca28-110">numVars : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="eca28-111">Nombre de variables</span><span class="sxs-lookup"><span data-stu-id="eca28-111">Number of variables</span></span>



## <a name="output--bool"></a><span data-ttu-id="eca28-112">Sortie : [bool](xref:microsoft.quantum.lang-ref.bool)[]</span><span class="sxs-lookup"><span data-stu-id="eca28-112">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span></span>

<span data-ttu-id="eca28-113">Table de vérité à taille ajustée</span><span class="sxs-lookup"><span data-stu-id="eca28-113">Size adjusted truth table</span></span>