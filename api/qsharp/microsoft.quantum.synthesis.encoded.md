---
uid: Microsoft.Quantum.Synthesis.Encoded
title: Fonction encodée
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: Encoded
qsharp.summary: Encode truth table in {1,-1} coding
ms.openlocfilehash: 44f6b247e6bfab7b55c46146cb63f8b6d219955b
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98855496"
---
# <a name="encoded-function"></a><span data-ttu-id="d9ca9-102">Fonction encodée</span><span class="sxs-lookup"><span data-stu-id="d9ca9-102">Encoded function</span></span>

<span data-ttu-id="d9ca9-103">Espace de noms : [Microsoft. Quantum. Synthesis](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="d9ca9-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="d9ca9-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="d9ca9-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="d9ca9-105">Coder la table de vérité en {1,-1} codage</span><span class="sxs-lookup"><span data-stu-id="d9ca9-105">Encode truth table in {1,-1} coding</span></span>

```qsharp
function Encoded (table : Bool[]) : Int[]
```


## <a name="input"></a><span data-ttu-id="d9ca9-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="d9ca9-106">Input</span></span>

### <a name="table--bool"></a><span data-ttu-id="d9ca9-107">table : [bool](xref:microsoft.quantum.lang-ref.bool)[]</span><span class="sxs-lookup"><span data-stu-id="d9ca9-107">table : [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span></span>

<span data-ttu-id="d9ca9-108">Table de vérité en tant que tableau de valeurs de vérité</span><span class="sxs-lookup"><span data-stu-id="d9ca9-108">Truth table as array of truth values</span></span>



## <a name="output--int"></a><span data-ttu-id="d9ca9-109">Sortie : [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="d9ca9-109">Output : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="d9ca9-110">Table de vérité en tant que tableau d' {1,-1} entiers</span><span class="sxs-lookup"><span data-stu-id="d9ca9-110">Truth table as array of {1,-1} integers</span></span>

## <a name="example"></a><span data-ttu-id="d9ca9-111">Exemple</span><span class="sxs-lookup"><span data-stu-id="d9ca9-111">Example</span></span>

```qsharp
Encoded([false, false, false, true]); // [1, 1, 1, -1]
```