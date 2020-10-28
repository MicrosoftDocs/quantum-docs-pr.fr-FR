---
uid: Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerEncodingData
title: Type défini par l’utilisateur JordanWignerEncodingData
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: JordanWignerEncodingData
qsharp.summary: Format of data passed from C# to Q# to represent all information for Hamiltonian simulation. The meaning of the data represented is determined by the algorithm that receives it.
ms.openlocfilehash: 62988eefa57d8a9e4ed9dcfbdbc6c3b630c6faa2
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92703216"
---
# <a name="jordanwignerencodingdata-user-defined-type"></a><span data-ttu-id="08f75-102">Type défini par l’utilisateur JordanWignerEncodingData</span><span class="sxs-lookup"><span data-stu-id="08f75-102">JordanWignerEncodingData user defined type</span></span>

<span data-ttu-id="08f75-103">Espace de noms : [Microsoft. Quantum. chimie. JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span><span class="sxs-lookup"><span data-stu-id="08f75-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span></span>

<span data-ttu-id="08f75-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="08f75-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="08f75-105">Format des données passées de C# à Q # pour représenter toutes les informations pour la simulation de la Hamilton.</span><span class="sxs-lookup"><span data-stu-id="08f75-105">Format of data passed from C# to Q# to represent all information for Hamiltonian simulation.</span></span>
<span data-ttu-id="08f75-106">La signification des données représentées est déterminée par l’algorithme qui la reçoit.</span><span class="sxs-lookup"><span data-stu-id="08f75-106">The meaning of the data represented is determined by the algorithm that receives it.</span></span>

```qsharp

newtype JordanWignerEncodingData = (Int, Microsoft.Quantum.Chemistry.JordanWigner.JWOptimizedHTerms, (Int, Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerInputState[]), Double);
```

