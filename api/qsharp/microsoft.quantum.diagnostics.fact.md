---
uid: Microsoft.Quantum.Diagnostics.Fact
title: Fonction FACT
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: Fact
qsharp.summary: Declares that a classical condition is true.
ms.openlocfilehash: 74ec020d0437d885d7cbfc98a2c9c0c1867d5d39
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96201680"
---
# <a name="fact-function"></a><span data-ttu-id="2407e-102">Fonction FACT</span><span class="sxs-lookup"><span data-stu-id="2407e-102">Fact function</span></span>

<span data-ttu-id="2407e-103">Espace de noms : [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="2407e-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="2407e-104">Package : [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="2407e-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="2407e-105">Déclare qu’une condition classique a la valeur true.</span><span class="sxs-lookup"><span data-stu-id="2407e-105">Declares that a classical condition is true.</span></span>

```qsharp
function Fact (actual : Bool, message : String) : Unit
```


## <a name="input"></a><span data-ttu-id="2407e-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="2407e-106">Input</span></span>

### <a name="actual--bool"></a><span data-ttu-id="2407e-107">réel : [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="2407e-107">actual : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="2407e-108">Condition à déclarer.</span><span class="sxs-lookup"><span data-stu-id="2407e-108">The condition to be declared.</span></span>


### <a name="message--string"></a><span data-ttu-id="2407e-109">message : [chaîne](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="2407e-109">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="2407e-110">Chaîne de message d’échec à imprimer dans le cas où la condition classique est false.</span><span class="sxs-lookup"><span data-stu-id="2407e-110">Failure message string to be printed in the case that the classical condition is false.</span></span>



## <a name="output--unit"></a><span data-ttu-id="2407e-111">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="2407e-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="2407e-112">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="2407e-112">See Also</span></span>

- [<span data-ttu-id="2407e-113">Microsoft. Quantum. Diagnostics. contradiction</span><span class="sxs-lookup"><span data-stu-id="2407e-113">Microsoft.Quantum.Diagnostics.Contradiction</span></span>](xref:Microsoft.Quantum.Diagnostics.Contradiction)