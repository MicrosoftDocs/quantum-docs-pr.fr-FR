---
uid: Microsoft.Quantum.Random.DrawRandomBool
title: Opération DrawRandomBool
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: DrawRandomBool
qsharp.summary: Given a success probability, returns a single Bernoulli trial that is true with the given probability.
ms.openlocfilehash: 7c13f8305756421b8d07baf22ff87764efac0418
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853690"
---
# <a name="drawrandombool-operation"></a><span data-ttu-id="7c95c-102">Opération DrawRandomBool</span><span class="sxs-lookup"><span data-stu-id="7c95c-102">DrawRandomBool operation</span></span>

<span data-ttu-id="7c95c-103">Espace de noms : [Microsoft. Quantum. Random](xref:Microsoft.Quantum.Random)</span><span class="sxs-lookup"><span data-stu-id="7c95c-103">Namespace: [Microsoft.Quantum.Random](xref:Microsoft.Quantum.Random)</span></span>

<span data-ttu-id="7c95c-104">Package : [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="7c95c-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="7c95c-105">Pour une probabilité de réussite donnée, retourne une seule version d’essai de Bernoulli qui est vraie avec la probabilité donnée.</span><span class="sxs-lookup"><span data-stu-id="7c95c-105">Given a success probability, returns a single Bernoulli trial that is true with the given probability.</span></span>

```qsharp
operation DrawRandomBool (successProbability : Double) : Bool
```


## <a name="input"></a><span data-ttu-id="7c95c-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="7c95c-106">Input</span></span>

### <a name="successprobability--double"></a><span data-ttu-id="7c95c-107">successProbability : [double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="7c95c-107">successProbability : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="7c95c-108">Probabilité avec laquelle `true` doit être retourné.</span><span class="sxs-lookup"><span data-stu-id="7c95c-108">The probability with which `true` should be returned.</span></span>



## <a name="output--bool"></a><span data-ttu-id="7c95c-109">Sortie : [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="7c95c-109">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="7c95c-110">`true` avec la probabilité `successProbability` et `false` avec la probabilité `1.0 - successProbability` .</span><span class="sxs-lookup"><span data-stu-id="7c95c-110">`true` with probability `successProbability` and `false` with probability `1.0 - successProbability`.</span></span>

## <a name="example"></a><span data-ttu-id="7c95c-111">Exemple</span><span class="sxs-lookup"><span data-stu-id="7c95c-111">Example</span></span>

<span data-ttu-id="7c95c-112">Les exemples d’extraits de code Q # suivants retournent à partir d’une pièce de monnaie biaisée :</span><span class="sxs-lookup"><span data-stu-id="7c95c-112">The following Q# snippet samples flips from a biased coin:</span></span>

```qsharp
let flips = DrawMany(DrawRandomBool, 10, 0.6);
```