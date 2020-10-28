---
uid: Microsoft.Quantum.Chemistry.HTermsToGenSys
title: HTermsToGenSys fonction)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry
qsharp.name: HTermsToGenSys
qsharp.summary: Converts a Hamiltonian in `HTerm[]` data format to a GeneratorSystem.
ms.openlocfilehash: b78ff393fa1e51c38028ef56bb3c61b8f1d5e478
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92703555"
---
# <a name="htermstogensys-function"></a><span data-ttu-id="718de-102">HTermsToGenSys fonction)</span><span class="sxs-lookup"><span data-stu-id="718de-102">HTermsToGenSys function</span></span>

<span data-ttu-id="718de-103">Espace de noms : [Microsoft. Quantum. chimie](xref:Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="718de-103">Namespace: [Microsoft.Quantum.Chemistry](xref:Microsoft.Quantum.Chemistry)</span></span>

<span data-ttu-id="718de-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="718de-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="718de-105">Convertit un GeneratorSystem de l’un au `HTerm[]` format de données en un.</span><span class="sxs-lookup"><span data-stu-id="718de-105">Converts a Hamiltonian in `HTerm[]` data format to a GeneratorSystem.</span></span>

```qsharp
function HTermsToGenSys (data : Microsoft.Quantum.Chemistry.HTerm[], termType : Int[]) : Microsoft.Quantum.Simulation.GeneratorSystem
```


## <a name="input"></a><span data-ttu-id="718de-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="718de-106">Input</span></span>

### <a name="data--hterm"></a><span data-ttu-id="718de-107">données : [HTerm](xref:Microsoft.Quantum.Chemistry.HTerm)[]</span><span class="sxs-lookup"><span data-stu-id="718de-107">data : [HTerm](xref:Microsoft.Quantum.Chemistry.HTerm)[]</span></span>

<span data-ttu-id="718de-108">Données d’entrée au `HTerm[]` format.</span><span class="sxs-lookup"><span data-stu-id="718de-108">Input data in `HTerm[]` format.</span></span>


### <a name="termtype--int"></a><span data-ttu-id="718de-109">termType : [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="718de-109">termType : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="718de-110">Informations supplémentaires ajoutées à GeneratorIndex.</span><span class="sxs-lookup"><span data-stu-id="718de-110">Additional information added to GeneratorIndex.</span></span>



## <a name="output--generatorsystem"></a><span data-ttu-id="718de-111">Sortie : [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span><span class="sxs-lookup"><span data-stu-id="718de-111">Output : [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span></span>

<span data-ttu-id="718de-112">GeneratorSystem représentant un sous-Hamilton représenté par l’entrée `data` .</span><span class="sxs-lookup"><span data-stu-id="718de-112">A GeneratorSystem representing a Hamiltonian represented by the input `data`.</span></span>