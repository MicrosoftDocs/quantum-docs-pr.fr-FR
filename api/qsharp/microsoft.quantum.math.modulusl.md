---
uid: Microsoft.Quantum.Math.ModulusL
title: Fonction modulo
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ModulusL
qsharp.summary: Computes the canonical residue of `value` modulo `modulus`.
ms.openlocfilehash: 6be2edb052cf55f8e8465c76b5dcadeb61ff11ea
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842741"
---
# <a name="modulusl-function"></a><span data-ttu-id="b2b76-102">Fonction modulo</span><span class="sxs-lookup"><span data-stu-id="b2b76-102">ModulusL function</span></span>

<span data-ttu-id="b2b76-103">Espace de noms : [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="b2b76-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="b2b76-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="b2b76-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="b2b76-105">Calcule le résidu canonique du `value` modulo `modulus` .</span><span class="sxs-lookup"><span data-stu-id="b2b76-105">Computes the canonical residue of `value` modulo `modulus`.</span></span>

```qsharp
function ModulusL (value : BigInt, modulus : BigInt) : BigInt
```


## <a name="input"></a><span data-ttu-id="b2b76-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="b2b76-106">Input</span></span>

### <a name="value--bigint"></a><span data-ttu-id="b2b76-107">valeur : [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="b2b76-107">value : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="b2b76-108">Valeur de laquelle le résidu est calculé</span><span class="sxs-lookup"><span data-stu-id="b2b76-108">The value of which residue is computed</span></span>


### <a name="modulus--bigint"></a><span data-ttu-id="b2b76-109">modulo : [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="b2b76-109">modulus : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="b2b76-110">Le modulo par lequel les résidus sont précédés doit être positif</span><span class="sxs-lookup"><span data-stu-id="b2b76-110">The modulus by which residues are take, must be positive</span></span>



## <a name="output--bigint"></a><span data-ttu-id="b2b76-111">Sortie : [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="b2b76-111">Output : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="b2b76-112">Entier $r $ entre 0 et `modulus - 1` qui `value - r` est divisible par le modulo</span><span class="sxs-lookup"><span data-stu-id="b2b76-112">Integer $r$ between 0 and `modulus - 1` such that `value - r` is divisible by modulus</span></span>

## <a name="remarks"></a><span data-ttu-id="b2b76-113">Notes</span><span class="sxs-lookup"><span data-stu-id="b2b76-113">Remarks</span></span>

<span data-ttu-id="b2b76-114">Cette fonction se comporte différemment de la façon dont l’opérateur `%` se comporte en C# et Q # comme dans le résultat est toujours un entier non négatif compris entre 0 et `modulus - 1` , même si la valeur est négative.</span><span class="sxs-lookup"><span data-stu-id="b2b76-114">This function behaves different to how the operator `%` behaves in C# and Q# as in the result is always a non-negative integer between 0 and `modulus - 1`, even if value is negative.</span></span>