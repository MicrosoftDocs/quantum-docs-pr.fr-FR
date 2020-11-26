---
uid: Microsoft.Quantum.Synthesis.SizeAdjustedTruthTable
title: SizeAdjustedTruthTable fonction)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: SizeAdjustedTruthTable
qsharp.summary: >-
  Adjusts truth table from array of Booleans according to number of variables

  A new array is returned of length `2^numVars`, possibly requiring to extend `table`'s size with `false` entries or truncating it to `2^numVars` elements.
ms.openlocfilehash: c53ac3f2c46bca955847fc7b380337e3910390ac
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96202921"
---
# <a name="sizeadjustedtruthtable-function"></a><span data-ttu-id="9646d-102">SizeAdjustedTruthTable fonction)</span><span class="sxs-lookup"><span data-stu-id="9646d-102">SizeAdjustedTruthTable function</span></span>

<span data-ttu-id="9646d-103">Espace de noms : [Microsoft. Quantum. Synthesis](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="9646d-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="9646d-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="9646d-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="9646d-105">Ajuste la table de vérité à partir d’un tableau de valeurs booléennes en fonction du nombre de variables</span><span class="sxs-lookup"><span data-stu-id="9646d-105">Adjusts truth table from array of Booleans according to number of variables</span></span>

<span data-ttu-id="9646d-106">Un nouveau tableau est retourné de longueur `2^numVars` , ce qui peut nécessiter l’extension de `table` la taille de dans les `false` entrées ou sa troncation aux `2^numVars` éléments.</span><span class="sxs-lookup"><span data-stu-id="9646d-106">A new array is returned of length `2^numVars`, possibly requiring to extend `table`'s size with `false` entries or truncating it to `2^numVars` elements.</span></span>

```qsharp
function SizeAdjustedTruthTable (table : Bool[], numVars : Int) : Bool[]
```


## <a name="input"></a><span data-ttu-id="9646d-107">Entrée</span><span class="sxs-lookup"><span data-stu-id="9646d-107">Input</span></span>

### <a name="table--bool"></a><span data-ttu-id="9646d-108">table : [bool](xref:microsoft.quantum.lang-ref.bool)[]</span><span class="sxs-lookup"><span data-stu-id="9646d-108">table : [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span></span>

<span data-ttu-id="9646d-109">Table de vérité en tant que tableau de valeurs de vérité</span><span class="sxs-lookup"><span data-stu-id="9646d-109">Truth table as array of truth values</span></span>


### <a name="numvars--int"></a><span data-ttu-id="9646d-110">numVars : [entier](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="9646d-110">numVars : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="9646d-111">Nombre de variables</span><span class="sxs-lookup"><span data-stu-id="9646d-111">Number of variables</span></span>



## <a name="output--bool"></a><span data-ttu-id="9646d-112">Sortie : [bool](xref:microsoft.quantum.lang-ref.bool)[]</span><span class="sxs-lookup"><span data-stu-id="9646d-112">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span></span>

<span data-ttu-id="9646d-113">Table de vérité à taille ajustée</span><span class="sxs-lookup"><span data-stu-id="9646d-113">Size adjusted truth table</span></span>