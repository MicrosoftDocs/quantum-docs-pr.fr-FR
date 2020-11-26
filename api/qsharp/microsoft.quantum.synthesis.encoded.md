---
uid: Microsoft.Quantum.Synthesis.Encoded
title: Fonction encodée
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: Encoded
qsharp.summary: Encode truth table in {1,-1} coding
ms.openlocfilehash: 803f35b9e7af547bc34f21de74684fba885bfda9
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96203176"
---
# <a name="encoded-function"></a><span data-ttu-id="6fe41-102">Fonction encodée</span><span class="sxs-lookup"><span data-stu-id="6fe41-102">Encoded function</span></span>

<span data-ttu-id="6fe41-103">Espace de noms : [Microsoft. Quantum. Synthesis](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="6fe41-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="6fe41-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="6fe41-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="6fe41-105">Coder la table de vérité en {1,-1} codage</span><span class="sxs-lookup"><span data-stu-id="6fe41-105">Encode truth table in {1,-1} coding</span></span>

```qsharp
function Encoded (table : Bool[]) : Int[]
```


## <a name="input"></a><span data-ttu-id="6fe41-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="6fe41-106">Input</span></span>

### <a name="table--bool"></a><span data-ttu-id="6fe41-107">table : [bool](xref:microsoft.quantum.lang-ref.bool)[]</span><span class="sxs-lookup"><span data-stu-id="6fe41-107">table : [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span></span>

<span data-ttu-id="6fe41-108">Table de vérité en tant que tableau de valeurs de vérité</span><span class="sxs-lookup"><span data-stu-id="6fe41-108">Truth table as array of truth values</span></span>



## <a name="output--int"></a><span data-ttu-id="6fe41-109">Sortie : [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="6fe41-109">Output : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="6fe41-110">Table de vérité en tant que tableau d' {1,-1} entiers</span><span class="sxs-lookup"><span data-stu-id="6fe41-110">Truth table as array of {1,-1} integers</span></span>