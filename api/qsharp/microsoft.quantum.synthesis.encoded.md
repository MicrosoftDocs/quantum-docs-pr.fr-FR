---
uid: Microsoft.Quantum.Synthesis.Encoded
title: Fonction encodée
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: Encoded
qsharp.summary: Encode truth table in {1,-1} coding
ms.openlocfilehash: 6b9d21969ee90f3928b65a1c97a5b0f15157e381
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92709167"
---
# <a name="encoded-function"></a><span data-ttu-id="64a69-102">Fonction encodée</span><span class="sxs-lookup"><span data-stu-id="64a69-102">Encoded function</span></span>

<span data-ttu-id="64a69-103">Espace de noms : [Microsoft. Quantum. Synthesis](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="64a69-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="64a69-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="64a69-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="64a69-105">Coder la table de vérité en {1,-1} codage</span><span class="sxs-lookup"><span data-stu-id="64a69-105">Encode truth table in {1,-1} coding</span></span>

```qsharp
function Encoded (table : Bool[]) : Int[]
```


## <a name="input"></a><span data-ttu-id="64a69-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="64a69-106">Input</span></span>

### <a name="table--bool"></a><span data-ttu-id="64a69-107">table : [bool](xref:microsoft.quantum.lang-ref.bool)[]</span><span class="sxs-lookup"><span data-stu-id="64a69-107">table : [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span></span>

<span data-ttu-id="64a69-108">Table de vérité en tant que tableau de valeurs de vérité</span><span class="sxs-lookup"><span data-stu-id="64a69-108">Truth table as array of truth values</span></span>



## <a name="output--int"></a><span data-ttu-id="64a69-109">Sortie : [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="64a69-109">Output : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="64a69-110">Table de vérité en tant que tableau d' {1,-1} entiers</span><span class="sxs-lookup"><span data-stu-id="64a69-110">Truth table as array of {1,-1} integers</span></span>