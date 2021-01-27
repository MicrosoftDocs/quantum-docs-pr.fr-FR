---
uid: Microsoft.Quantum.Chemistry.HTermsToGenIdx
title: HTermsToGenIdx fonction)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry
qsharp.name: HTermsToGenIdx
qsharp.summary: Converts an index to a Hamiltonian term in `HTerm[]` data format to a GeneratorIndex.
ms.openlocfilehash: 84dc132528f8fd1c45fb2f7345111a05626ee686
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98839631"
---
# <a name="htermstogenidx-function"></a><span data-ttu-id="7592e-102">HTermsToGenIdx fonction)</span><span class="sxs-lookup"><span data-stu-id="7592e-102">HTermsToGenIdx function</span></span>

<span data-ttu-id="7592e-103">Espace de noms : [Microsoft. Quantum. chimie](xref:Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="7592e-103">Namespace: [Microsoft.Quantum.Chemistry](xref:Microsoft.Quantum.Chemistry)</span></span>

<span data-ttu-id="7592e-104">Package : [Microsoft. Quantum. chimie](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="7592e-104">Package: [Microsoft.Quantum.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span></span>


<span data-ttu-id="7592e-105">Convertit un index en un terme de `HTerm[]` données au format de données en GeneratorIndex.</span><span class="sxs-lookup"><span data-stu-id="7592e-105">Converts an index to a Hamiltonian term in `HTerm[]` data format to a GeneratorIndex.</span></span>

```qsharp
function HTermsToGenIdx (data : Microsoft.Quantum.Chemistry.HTerm[], termType : Int[], idx : Int) : Microsoft.Quantum.Simulation.GeneratorIndex
```


## <a name="input"></a><span data-ttu-id="7592e-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="7592e-106">Input</span></span>

### <a name="data--hterm"></a><span data-ttu-id="7592e-107">données : [HTerm](xref:Microsoft.Quantum.Chemistry.HTerm)[]</span><span class="sxs-lookup"><span data-stu-id="7592e-107">data : [HTerm](xref:Microsoft.Quantum.Chemistry.HTerm)[]</span></span>

<span data-ttu-id="7592e-108">Données d’entrée au `HTerm[]` format.</span><span class="sxs-lookup"><span data-stu-id="7592e-108">Input data in `HTerm[]` format.</span></span>


### <a name="termtype--int"></a><span data-ttu-id="7592e-109">termType : [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="7592e-109">termType : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="7592e-110">Informations supplémentaires ajoutées à GeneratorIndex.</span><span class="sxs-lookup"><span data-stu-id="7592e-110">Additional information added to GeneratorIndex.</span></span>


### <a name="idx--int"></a><span data-ttu-id="7592e-111">idx : [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="7592e-111">idx : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="7592e-112">Indexer sur un terme de la « Hamilton »</span><span class="sxs-lookup"><span data-stu-id="7592e-112">Index to a term of the Hamiltonian</span></span>



## <a name="output--generatorindex"></a><span data-ttu-id="7592e-113">Sortie : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="7592e-113">Output : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="7592e-114">GeneratorIndex représentant un terme de Hamilton représenté par `data[idx]` , ainsi que des informations supplémentaires ajoutées par `termType` .</span><span class="sxs-lookup"><span data-stu-id="7592e-114">A GeneratorIndex representing a Hamiltonian term represented by `data[idx]`, together with additional information added by `termType`.</span></span>