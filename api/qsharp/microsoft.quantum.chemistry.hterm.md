---
uid: Microsoft.Quantum.Chemistry.HTerm
title: Type défini par l’utilisateur HTerm
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Chemistry
qsharp.name: HTerm
qsharp.summary: Format of data passed from C# to Q# to represent a term of the Hamiltonian. The meaning of the data represented is determined by the algorithm that receives it.
ms.openlocfilehash: 7a18db539e55e4c1086b3d83725e3d4ba87f0117
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92703567"
---
# <a name="hterm-user-defined-type"></a><span data-ttu-id="e0365-102">Type défini par l’utilisateur HTerm</span><span class="sxs-lookup"><span data-stu-id="e0365-102">HTerm user defined type</span></span>

<span data-ttu-id="e0365-103">Espace de noms : [Microsoft. Quantum. chimie](xref:Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="e0365-103">Namespace: [Microsoft.Quantum.Chemistry](xref:Microsoft.Quantum.Chemistry)</span></span>

<span data-ttu-id="e0365-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="e0365-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="e0365-105">Format des données passées de C# à Q # pour représenter un terme de la même façon.</span><span class="sxs-lookup"><span data-stu-id="e0365-105">Format of data passed from C# to Q# to represent a term of the Hamiltonian.</span></span>
<span data-ttu-id="e0365-106">La signification des données représentées est déterminée par l’algorithme qui la reçoit.</span><span class="sxs-lookup"><span data-stu-id="e0365-106">The meaning of the data represented is determined by the algorithm that receives it.</span></span>

```qsharp

newtype HTerm = (Int[], Double[]);
```

