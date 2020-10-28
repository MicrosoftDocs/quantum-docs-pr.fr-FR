---
uid: Microsoft.Quantum.Chemistry.JordanWigner.JWOptimizedHTerms
title: Type défini par l’utilisateur JWOptimizedHTerms
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: JWOptimizedHTerms
qsharp.summary: Format of data passed from C# to Q# to represent terms of the Hamiltonian. The meaning of the data represented is determined by the algorithm that receives it.
ms.openlocfilehash: d75737f23db84f2a21daff7a0ebcb8ae51feb642
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92703180"
---
# <a name="jwoptimizedhterms-user-defined-type"></a><span data-ttu-id="af917-102">Type défini par l’utilisateur JWOptimizedHTerms</span><span class="sxs-lookup"><span data-stu-id="af917-102">JWOptimizedHTerms user defined type</span></span>

<span data-ttu-id="af917-103">Espace de noms : [Microsoft. Quantum. chimie. JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span><span class="sxs-lookup"><span data-stu-id="af917-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span></span>

<span data-ttu-id="af917-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="af917-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="af917-105">Format des données passées de C# à Q # pour représenter les termes du niveau de la Hamilton.</span><span class="sxs-lookup"><span data-stu-id="af917-105">Format of data passed from C# to Q# to represent terms of the Hamiltonian.</span></span>
<span data-ttu-id="af917-106">La signification des données représentées est déterminée par l’algorithme qui la reçoit.</span><span class="sxs-lookup"><span data-stu-id="af917-106">The meaning of the data represented is determined by the algorithm that receives it.</span></span>

```qsharp

newtype JWOptimizedHTerms = (Microsoft.Quantum.Chemistry.HTerm[], Microsoft.Quantum.Chemistry.HTerm[], Microsoft.Quantum.Chemistry.HTerm[], Microsoft.Quantum.Chemistry.HTerm[]);
```

