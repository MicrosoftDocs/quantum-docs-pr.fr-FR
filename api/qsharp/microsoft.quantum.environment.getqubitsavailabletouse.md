---
uid: Microsoft.Quantum.Environment.GetQubitsAvailableToUse
title: Opération GetQubitsAvailableToUse
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Environment
qsharp.name: GetQubitsAvailableToUse
qsharp.summary: Returns the number of qubits currently available to use.
ms.openlocfilehash: 25d43d369193fc7453fd5ce9c50769c438a69afb
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92702586"
---
# <a name="getqubitsavailabletouse-operation"></a><span data-ttu-id="bc74e-102">Opération GetQubitsAvailableToUse</span><span class="sxs-lookup"><span data-stu-id="bc74e-102">GetQubitsAvailableToUse operation</span></span>

<span data-ttu-id="bc74e-103">Espace de noms : [Microsoft. Quantum. Environment](xref:Microsoft.Quantum.Environment)</span><span class="sxs-lookup"><span data-stu-id="bc74e-103">Namespace: [Microsoft.Quantum.Environment](xref:Microsoft.Quantum.Environment)</span></span>

<span data-ttu-id="bc74e-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="bc74e-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="bc74e-105">Retourne le nombre de qubits actuellement disponibles à utiliser.</span><span class="sxs-lookup"><span data-stu-id="bc74e-105">Returns the number of qubits currently available to use.</span></span>

```qsharp
operation GetQubitsAvailableToUse () : Int
```


## <a name="output--int"></a><span data-ttu-id="bc74e-106">Sortie : [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="bc74e-106">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="bc74e-107">Nombre de qubits qui peuvent être alloués dans une `using` instruction.</span><span class="sxs-lookup"><span data-stu-id="bc74e-107">The number of qubits that could be allocated in a `using` statement.</span></span>
<span data-ttu-id="bc74e-108">Si l’ordinateur cible utilisé ne fournit pas ces informations, `-1` est retourné.</span><span class="sxs-lookup"><span data-stu-id="bc74e-108">If the target machine being used does not provide this information, then `-1` is returned.</span></span>

## <a name="see-also"></a><span data-ttu-id="bc74e-109">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="bc74e-109">See Also</span></span>

- [<span data-ttu-id="bc74e-110">Microsoft. Quantum. Environment. GetQubitsAvailableToBorrow</span><span class="sxs-lookup"><span data-stu-id="bc74e-110">Microsoft.Quantum.Environment.GetQubitsAvailableToBorrow</span></span>](xref:Microsoft.Quantum.Environment.GetQubitsAvailableToBorrow)