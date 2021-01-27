---
uid: Microsoft.Quantum.Synthesis.IntegerBits
title: IntegerBits fonction)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: IntegerBits
qsharp.summary: Returns all positions in which bits of an integer are set.
ms.openlocfilehash: 3352c1b3003ee387fb03b72461fedb400e29046d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98855398"
---
# <a name="integerbits-function"></a><span data-ttu-id="97ded-102">IntegerBits fonction)</span><span class="sxs-lookup"><span data-stu-id="97ded-102">IntegerBits function</span></span>

<span data-ttu-id="97ded-103">Espace de noms : [Microsoft. Quantum. Synthesis](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="97ded-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="97ded-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="97ded-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="97ded-105">Retourne toutes les positions dans lesquelles les bits d’un entier sont définis.</span><span class="sxs-lookup"><span data-stu-id="97ded-105">Returns all positions in which bits of an integer are set.</span></span>

```qsharp
function IntegerBits (value : Int, length : Int) : Int[]
```


## <a name="input"></a><span data-ttu-id="97ded-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="97ded-106">Input</span></span>

### <a name="value--int"></a><span data-ttu-id="97ded-107">valeur : [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="97ded-107">value : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="97ded-108">Nombre non négatif.</span><span class="sxs-lookup"><span data-stu-id="97ded-108">A nonnegative number.</span></span>


### <a name="length--int"></a><span data-ttu-id="97ded-109">Longueur : [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="97ded-109">length : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="97ded-110">Nombre de bits dans l’expansion binaire de `value` .</span><span class="sxs-lookup"><span data-stu-id="97ded-110">The number of bits in the binary expansion of `value`.</span></span>



## <a name="output--int"></a><span data-ttu-id="97ded-111">Sortie : [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="97ded-111">Output : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="97ded-112">Tableau qui contient toutes les positions de bits (à partir de 0) qui sont égales à 1 dans l’expansion binaire de la prise `value` en compte de tous les bits jusqu’à la position `length - 1` .</span><span class="sxs-lookup"><span data-stu-id="97ded-112">An array containing all bit positions (starting from 0) that are 1 in the binary expansion of `value` considering all bits up to position `length - 1`.</span></span>  <span data-ttu-id="97ded-113">Toutes les positions sont classées dans le tableau par position dans un ordre de croisement.</span><span class="sxs-lookup"><span data-stu-id="97ded-113">All positions are ordered in the array by position in an increasing order.</span></span>

## <a name="example"></a><span data-ttu-id="97ded-114">Exemple</span><span class="sxs-lookup"><span data-stu-id="97ded-114">Example</span></span>

```qsharp
IntegerBits(23, 5); // [0, 1, 2, 4]
IntegerBits(10, 4); // [1, 3]
```