---
uid: Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerEncodingData
title: Type défini par l’utilisateur JordanWignerEncodingData
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: JordanWignerEncodingData
qsharp.summary: Format of data passed from C# to Q# to represent all information for Hamiltonian simulation. The meaning of the data represented is determined by the algorithm that receives it.
ms.openlocfilehash: 2acb33c8dab229264273ff23606c47322df740a4
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96214787"
---
# <a name="jordanwignerencodingdata-user-defined-type"></a><span data-ttu-id="3674f-102">Type défini par l’utilisateur JordanWignerEncodingData</span><span class="sxs-lookup"><span data-stu-id="3674f-102">JordanWignerEncodingData user defined type</span></span>

<span data-ttu-id="3674f-103">Espace de noms : [Microsoft. Quantum. chimie. JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span><span class="sxs-lookup"><span data-stu-id="3674f-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span></span>

<span data-ttu-id="3674f-104">Package : [Microsoft. Quantum. chimie](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="3674f-104">Package: [Microsoft.Quantum.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span></span>


<span data-ttu-id="3674f-105">Format des données passées de C# à Q # pour représenter toutes les informations pour la simulation de la Hamilton.</span><span class="sxs-lookup"><span data-stu-id="3674f-105">Format of data passed from C# to Q# to represent all information for Hamiltonian simulation.</span></span>
<span data-ttu-id="3674f-106">La signification des données représentées est déterminée par l’algorithme qui la reçoit.</span><span class="sxs-lookup"><span data-stu-id="3674f-106">The meaning of the data represented is determined by the algorithm that receives it.</span></span>

```qsharp

newtype JordanWignerEncodingData = (Int, Microsoft.Quantum.Chemistry.JordanWigner.JWOptimizedHTerms, (Int, Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerInputState[]), Double);
```

