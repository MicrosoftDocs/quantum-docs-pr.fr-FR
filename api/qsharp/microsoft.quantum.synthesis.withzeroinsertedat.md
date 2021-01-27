---
uid: Microsoft.Quantum.Synthesis.WithZeroInsertedAt
title: WithZeroInsertedAt fonction)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: WithZeroInsertedAt
qsharp.summary: Insert a 0-bit into an integer
ms.openlocfilehash: 7d5f8838b6ae555524fb0e82e14f93e6c77e43d4
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98855194"
---
# <a name="withzeroinsertedat-function"></a><span data-ttu-id="18f98-102">WithZeroInsertedAt fonction)</span><span class="sxs-lookup"><span data-stu-id="18f98-102">WithZeroInsertedAt function</span></span>

<span data-ttu-id="18f98-103">Espace de noms : [Microsoft. Quantum. Synthesis](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="18f98-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="18f98-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="18f98-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="18f98-105">Insérer un bit 0 dans un entier</span><span class="sxs-lookup"><span data-stu-id="18f98-105">Insert a 0-bit into an integer</span></span>

```qsharp
function WithZeroInsertedAt (position : Int, value : Int) : Int
```


## <a name="description"></a><span data-ttu-id="18f98-106">Description</span><span class="sxs-lookup"><span data-stu-id="18f98-106">Description</span></span>

<span data-ttu-id="18f98-107">Cette opération prend un entier, insère un 0 au bit `position` et retourne la valeur mise à jour sous la forme d’un entier.</span><span class="sxs-lookup"><span data-stu-id="18f98-107">This operation takes an integer, inserts a 0 at bit `position`, and returns the updated value as an integer.</span></span>  <span data-ttu-id="18f98-108">Par exemple, l’insertion de 0 à la position 2 dans le nombre 10 (10$ _ {10} = 1010_ {2} $) retourne le nombre 18 ($18 _ {10} = 10010_ {2} $).</span><span class="sxs-lookup"><span data-stu-id="18f98-108">For example, inserting a 0 at position 2 in the number 10 ($10_{10} = 1010_{2}$) returns the number 18 ($18_{10} = 10010_{2}$).</span></span>

## <a name="input"></a><span data-ttu-id="18f98-109">Entrée</span><span class="sxs-lookup"><span data-stu-id="18f98-109">Input</span></span>

### <a name="position--int"></a><span data-ttu-id="18f98-110">position : [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="18f98-110">position : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="18f98-111">Position à laquelle 0 est inséré</span><span class="sxs-lookup"><span data-stu-id="18f98-111">The position at which 0 is inserted</span></span>


### <a name="value--int"></a><span data-ttu-id="18f98-112">valeur : [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="18f98-112">value : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="18f98-113">Valeur modifiée</span><span class="sxs-lookup"><span data-stu-id="18f98-113">The value that is modified</span></span>



## <a name="output--int"></a><span data-ttu-id="18f98-114">Sortie : [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="18f98-114">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="18f98-115">Valeur modifiée</span><span class="sxs-lookup"><span data-stu-id="18f98-115">Modified value</span></span>