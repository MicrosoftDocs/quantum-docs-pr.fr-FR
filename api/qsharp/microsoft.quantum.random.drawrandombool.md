---
uid: Microsoft.Quantum.Random.DrawRandomBool
title: Opération DrawRandomBool
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: DrawRandomBool
qsharp.summary: Given a success probability, returns a single Bernoulli trial that is true with the given probability.
ms.openlocfilehash: dbe0836af5aa19f1bdce3cfe93be6833358c22be
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96192959"
---
# <a name="drawrandombool-operation"></a><span data-ttu-id="22291-102">Opération DrawRandomBool</span><span class="sxs-lookup"><span data-stu-id="22291-102">DrawRandomBool operation</span></span>

<span data-ttu-id="22291-103">Espace de noms : [Microsoft. Quantum. Random](xref:Microsoft.Quantum.Random)</span><span class="sxs-lookup"><span data-stu-id="22291-103">Namespace: [Microsoft.Quantum.Random](xref:Microsoft.Quantum.Random)</span></span>

<span data-ttu-id="22291-104">Package : [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="22291-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="22291-105">Pour une probabilité de réussite donnée, retourne une seule version d’essai de Bernoulli qui est vraie avec la probabilité donnée.</span><span class="sxs-lookup"><span data-stu-id="22291-105">Given a success probability, returns a single Bernoulli trial that is true with the given probability.</span></span>

```qsharp
operation DrawRandomBool (successProbability : Double) : Bool
```


## <a name="input"></a><span data-ttu-id="22291-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="22291-106">Input</span></span>

### <a name="successprobability--double"></a><span data-ttu-id="22291-107">successProbability : [double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="22291-107">successProbability : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="22291-108">Probabilité avec laquelle `true` doit être retourné.</span><span class="sxs-lookup"><span data-stu-id="22291-108">The probability with which `true` should be returned.</span></span>



## <a name="output--bool"></a><span data-ttu-id="22291-109">Sortie : [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="22291-109">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="22291-110">`true` avec la probabilité `successProbability` et `false` avec la probabilité `1.0 - successProbability` .</span><span class="sxs-lookup"><span data-stu-id="22291-110">`true` with probability `successProbability` and `false` with probability `1.0 - successProbability`.</span></span>