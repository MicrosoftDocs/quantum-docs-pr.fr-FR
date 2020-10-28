---
uid: Microsoft.Quantum.Environment.GetQubitsAvailableToBorrow
title: Opération GetQubitsAvailableToBorrow
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Environment
qsharp.name: GetQubitsAvailableToBorrow
qsharp.summary: Returns the number of qubits currently available to borrow. This includes unused qubits; that is, this includes the qubits returned by `GetQubitsAvailableToUse`.
ms.openlocfilehash: cb56ce4aefd7a03c0f0827b8d34688ef17988f56
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92702589"
---
# <a name="getqubitsavailabletoborrow-operation"></a><span data-ttu-id="d873d-102">Opération GetQubitsAvailableToBorrow</span><span class="sxs-lookup"><span data-stu-id="d873d-102">GetQubitsAvailableToBorrow operation</span></span>

<span data-ttu-id="d873d-103">Espace de noms : [Microsoft. Quantum. Environment](xref:Microsoft.Quantum.Environment)</span><span class="sxs-lookup"><span data-stu-id="d873d-103">Namespace: [Microsoft.Quantum.Environment](xref:Microsoft.Quantum.Environment)</span></span>

<span data-ttu-id="d873d-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="d873d-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="d873d-105">Retourne le nombre de qubits actuellement disponibles pour emprunter.</span><span class="sxs-lookup"><span data-stu-id="d873d-105">Returns the number of qubits currently available to borrow.</span></span>
<span data-ttu-id="d873d-106">Cela comprend les qubits inutilisés ; autrement dit, cela comprend le qubits retourné par `GetQubitsAvailableToUse` .</span><span class="sxs-lookup"><span data-stu-id="d873d-106">This includes unused qubits; that is, this includes the qubits returned by `GetQubitsAvailableToUse`.</span></span>

```qsharp
operation GetQubitsAvailableToBorrow () : Int
```


## <a name="output--int"></a><span data-ttu-id="d873d-107">Sortie : [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="d873d-107">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="d873d-108">Nombre de qubits qui peuvent être alloués dans une `borrowing` instruction.</span><span class="sxs-lookup"><span data-stu-id="d873d-108">The number of qubits that could be allocated in a `borrowing` statement.</span></span>
<span data-ttu-id="d873d-109">Si l’ordinateur cible utilisé ne fournit pas ces informations, `-1` est retourné.</span><span class="sxs-lookup"><span data-stu-id="d873d-109">If the target machine being used does not provide this information, then `-1` is returned.</span></span>

## <a name="see-also"></a><span data-ttu-id="d873d-110">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="d873d-110">See Also</span></span>

- [<span data-ttu-id="d873d-111">Microsoft. Quantum. Environment. GetQubitsAvailableToUse</span><span class="sxs-lookup"><span data-stu-id="d873d-111">Microsoft.Quantum.Environment.GetQubitsAvailableToUse</span></span>](xref:Microsoft.Quantum.Environment.GetQubitsAvailableToUse)