---
uid: Microsoft.Quantum.Random.DrawRandomBool
title: Opération DrawRandomBool
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: DrawRandomBool
qsharp.summary: Given a success probability, returns a single Bernoulli trial that is true with the given probability.
ms.openlocfilehash: 05cf8ad939691aac90625c5d056ea79aa062f553
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92706715"
---
# <a name="drawrandombool-operation"></a><span data-ttu-id="b4455-102">Opération DrawRandomBool</span><span class="sxs-lookup"><span data-stu-id="b4455-102">DrawRandomBool operation</span></span>

<span data-ttu-id="b4455-103">Espace de noms : [Microsoft. Quantum. Random](xref:Microsoft.Quantum.Random)</span><span class="sxs-lookup"><span data-stu-id="b4455-103">Namespace: [Microsoft.Quantum.Random](xref:Microsoft.Quantum.Random)</span></span>

<span data-ttu-id="b4455-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="b4455-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="b4455-105">Pour une probabilité de réussite donnée, retourne une seule version d’essai de Bernoulli qui est vraie avec la probabilité donnée.</span><span class="sxs-lookup"><span data-stu-id="b4455-105">Given a success probability, returns a single Bernoulli trial that is true with the given probability.</span></span>

```qsharp
operation DrawRandomBool (successProbability : Double) : Bool
```


## <a name="input"></a><span data-ttu-id="b4455-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="b4455-106">Input</span></span>

### <a name="successprobability--double"></a><span data-ttu-id="b4455-107">successProbability : [double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="b4455-107">successProbability : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="b4455-108">Probabilité avec laquelle `true` doit être retourné.</span><span class="sxs-lookup"><span data-stu-id="b4455-108">The probability with which `true` should be returned.</span></span>



## <a name="output--bool"></a><span data-ttu-id="b4455-109">Sortie : [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="b4455-109">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="b4455-110">`true` avec la probabilité `successProbability` et `false` avec la probabilité `1.0 - successProbability` .</span><span class="sxs-lookup"><span data-stu-id="b4455-110">`true` with probability `successProbability` and `false` with probability `1.0 - successProbability`.</span></span>