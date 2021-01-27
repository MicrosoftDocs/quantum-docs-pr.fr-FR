---
uid: Microsoft.Quantum.Environment.GetQubitsAvailableToUse
title: Opération GetQubitsAvailableToUse
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Environment
qsharp.name: GetQubitsAvailableToUse
qsharp.summary: Returns the number of qubits currently available to use.
ms.openlocfilehash: 2ed8c3789331a15b351769be960d06f6364d8047
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98827802"
---
# <a name="getqubitsavailabletouse-operation"></a><span data-ttu-id="dd50d-102">Opération GetQubitsAvailableToUse</span><span class="sxs-lookup"><span data-stu-id="dd50d-102">GetQubitsAvailableToUse operation</span></span>

<span data-ttu-id="dd50d-103">Espace de noms : [Microsoft. Quantum. Environment](xref:Microsoft.Quantum.Environment)</span><span class="sxs-lookup"><span data-stu-id="dd50d-103">Namespace: [Microsoft.Quantum.Environment](xref:Microsoft.Quantum.Environment)</span></span>

<span data-ttu-id="dd50d-104">Package : [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="dd50d-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="dd50d-105">Retourne le nombre de qubits actuellement disponibles à utiliser.</span><span class="sxs-lookup"><span data-stu-id="dd50d-105">Returns the number of qubits currently available to use.</span></span>

```qsharp
operation GetQubitsAvailableToUse () : Int
```


## <a name="output--int"></a><span data-ttu-id="dd50d-106">Sortie : [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="dd50d-106">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="dd50d-107">Nombre de qubits qui peuvent être alloués dans une `using` instruction.</span><span class="sxs-lookup"><span data-stu-id="dd50d-107">The number of qubits that could be allocated in a `using` statement.</span></span>
<span data-ttu-id="dd50d-108">Si l’ordinateur cible utilisé ne fournit pas ces informations, `-1` est retourné.</span><span class="sxs-lookup"><span data-stu-id="dd50d-108">If the target machine being used does not provide this information, then `-1` is returned.</span></span>

## <a name="see-also"></a><span data-ttu-id="dd50d-109">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="dd50d-109">See Also</span></span>

- [<span data-ttu-id="dd50d-110">Microsoft. Quantum. Environment. GetQubitsAvailableToBorrow</span><span class="sxs-lookup"><span data-stu-id="dd50d-110">Microsoft.Quantum.Environment.GetQubitsAvailableToBorrow</span></span>](xref:Microsoft.Quantum.Environment.GetQubitsAvailableToBorrow)