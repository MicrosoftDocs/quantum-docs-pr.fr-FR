---
uid: Microsoft.Quantum.Chemistry.HTermToGenIdx
title: HTermToGenIdx fonction)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry
qsharp.name: HTermToGenIdx
qsharp.summary: Converts a Hamiltonian term in `HTerm` data format to a GeneratorIndex.
ms.openlocfilehash: 59391a882fdbc55172ee93a7428c1735bbb29500
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96216028"
---
# <a name="htermtogenidx-function"></a><span data-ttu-id="b7cdf-102">HTermToGenIdx fonction)</span><span class="sxs-lookup"><span data-stu-id="b7cdf-102">HTermToGenIdx function</span></span>

<span data-ttu-id="b7cdf-103">Espace de noms : [Microsoft. Quantum. chimie](xref:Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="b7cdf-103">Namespace: [Microsoft.Quantum.Chemistry](xref:Microsoft.Quantum.Chemistry)</span></span>

<span data-ttu-id="b7cdf-104">Package : [Microsoft. Quantum. chimie](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="b7cdf-104">Package: [Microsoft.Quantum.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span></span>


<span data-ttu-id="b7cdf-105">Convertit un terme de la `HTerm` structure de données en GeneratorIndex.</span><span class="sxs-lookup"><span data-stu-id="b7cdf-105">Converts a Hamiltonian term in `HTerm` data format to a GeneratorIndex.</span></span>

```qsharp
function HTermToGenIdx (term : Microsoft.Quantum.Chemistry.HTerm, termType : Int[]) : Microsoft.Quantum.Simulation.GeneratorIndex
```


## <a name="input"></a><span data-ttu-id="b7cdf-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="b7cdf-106">Input</span></span>

### <a name="term--hterm"></a><span data-ttu-id="b7cdf-107">terme : [HTerm](xref:Microsoft.Quantum.Chemistry.HTerm)</span><span class="sxs-lookup"><span data-stu-id="b7cdf-107">term : [HTerm](xref:Microsoft.Quantum.Chemistry.HTerm)</span></span>

<span data-ttu-id="b7cdf-108">Données d’entrée au `HTerm` format.</span><span class="sxs-lookup"><span data-stu-id="b7cdf-108">Input data in `HTerm` format.</span></span>


### <a name="termtype--int"></a><span data-ttu-id="b7cdf-109">termType : [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="b7cdf-109">termType : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="b7cdf-110">Informations supplémentaires ajoutées à GeneratorIndex.</span><span class="sxs-lookup"><span data-stu-id="b7cdf-110">Additional information added to GeneratorIndex.</span></span>



## <a name="output--generatorindex"></a><span data-ttu-id="b7cdf-111">Sortie : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="b7cdf-111">Output : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="b7cdf-112">GeneratorIndex représentant un terme de Hamilton représenté par `term` , ainsi que des informations supplémentaires ajoutées par `termType` .</span><span class="sxs-lookup"><span data-stu-id="b7cdf-112">A GeneratorIndex representing a Hamiltonian term represented by `term`, together with additional information added by `termType`.</span></span>