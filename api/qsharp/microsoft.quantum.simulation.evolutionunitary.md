---
uid: Microsoft.Quantum.Simulation.EvolutionUnitary
title: Type défini par l’utilisateur EvolutionUnitary
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: EvolutionUnitary
qsharp.summary: >-
  Represents a unitary time-evolution operator.

  The first parameter is is duration of time-evolution, and the second parameter is the qubit register acted upon by the unitary.
ms.openlocfilehash: 28ab492573b67e4aa42392e4ee499596b9c0225f
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92709017"
---
# <a name="evolutionunitary-user-defined-type"></a><span data-ttu-id="3ce35-102">Type défini par l’utilisateur EvolutionUnitary</span><span class="sxs-lookup"><span data-stu-id="3ce35-102">EvolutionUnitary user defined type</span></span>

<span data-ttu-id="3ce35-103">Espace de noms : [Microsoft. Quantum. simulation](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="3ce35-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="3ce35-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="3ce35-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="3ce35-105">Représente un opérateur d’évolution temporelle.</span><span class="sxs-lookup"><span data-stu-id="3ce35-105">Represents a unitary time-evolution operator.</span></span>

<span data-ttu-id="3ce35-106">Le premier paramètre est la durée de l’évolution et le deuxième paramètre est le registre qubit traité par l’unité.</span><span class="sxs-lookup"><span data-stu-id="3ce35-106">The first parameter is is duration of time-evolution, and the second parameter is the qubit register acted upon by the unitary.</span></span>

```qsharp

newtype EvolutionUnitary = (((Double, Qubit[]) => Unit is Adj + Ctl));
```

