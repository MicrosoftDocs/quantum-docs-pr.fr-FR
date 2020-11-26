---
uid: Microsoft.Quantum.Diagnostics.Contradiction
title: Fonction de contradiction
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: Contradiction
qsharp.summary: Declares that a classical condition is false.
ms.openlocfilehash: f9ad9a7d67bda8e50c76f679f535ad55ba07698e
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96202139"
---
# <a name="contradiction-function"></a><span data-ttu-id="262fc-102">Fonction de contradiction</span><span class="sxs-lookup"><span data-stu-id="262fc-102">Contradiction function</span></span>

<span data-ttu-id="262fc-103">Espace de noms : [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="262fc-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="262fc-104">Package : [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="262fc-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="262fc-105">Déclare qu’une condition classique est false.</span><span class="sxs-lookup"><span data-stu-id="262fc-105">Declares that a classical condition is false.</span></span>

```qsharp
function Contradiction (actual : Bool, message : String) : Unit
```


## <a name="input"></a><span data-ttu-id="262fc-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="262fc-106">Input</span></span>

### <a name="actual--bool"></a><span data-ttu-id="262fc-107">réel : [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="262fc-107">actual : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="262fc-108">Condition à déclarer.</span><span class="sxs-lookup"><span data-stu-id="262fc-108">The condition to be declared.</span></span>


### <a name="message--string"></a><span data-ttu-id="262fc-109">message : [chaîne](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="262fc-109">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="262fc-110">Chaîne de message d’échec à imprimer dans le cas où la condition classique est true.</span><span class="sxs-lookup"><span data-stu-id="262fc-110">Failure message string to be printed in the case that the classical condition is true.</span></span>



## <a name="output--unit"></a><span data-ttu-id="262fc-111">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="262fc-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="262fc-112">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="262fc-112">See Also</span></span>

- [<span data-ttu-id="262fc-113">Microsoft. Quantum. Diagnostics. Fact</span><span class="sxs-lookup"><span data-stu-id="262fc-113">Microsoft.Quantum.Diagnostics.Fact</span></span>](xref:Microsoft.Quantum.Diagnostics.Fact)