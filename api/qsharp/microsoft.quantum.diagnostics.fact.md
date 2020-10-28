---
uid: Microsoft.Quantum.Diagnostics.Fact
title: Fonction FACT
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: Fact
qsharp.summary: Declares that a classical condition is true.
ms.openlocfilehash: 6a08703f68f9f38f2224fe4c6a4d255b00756908
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92702631"
---
# <a name="fact-function"></a><span data-ttu-id="01140-102">Fonction FACT</span><span class="sxs-lookup"><span data-stu-id="01140-102">Fact function</span></span>

<span data-ttu-id="01140-103">Espace de noms : [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="01140-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="01140-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="01140-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="01140-105">Déclare qu’une condition classique a la valeur true.</span><span class="sxs-lookup"><span data-stu-id="01140-105">Declares that a classical condition is true.</span></span>

```qsharp
function Fact (actual : Bool, message : String) : Unit
```


## <a name="input"></a><span data-ttu-id="01140-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="01140-106">Input</span></span>

### <a name="actual--bool"></a><span data-ttu-id="01140-107">réel : [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="01140-107">actual : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="01140-108">Condition à déclarer.</span><span class="sxs-lookup"><span data-stu-id="01140-108">The condition to be declared.</span></span>


### <a name="message--string"></a><span data-ttu-id="01140-109">message : [chaîne](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="01140-109">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="01140-110">Chaîne de message d’échec à imprimer dans le cas où la condition classique est false.</span><span class="sxs-lookup"><span data-stu-id="01140-110">Failure message string to be printed in the case that the classical condition is false.</span></span>



## <a name="output--unit"></a><span data-ttu-id="01140-111">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="01140-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="01140-112">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="01140-112">See Also</span></span>

- [<span data-ttu-id="01140-113">Microsoft. Quantum. Diagnostics. contradiction</span><span class="sxs-lookup"><span data-stu-id="01140-113">Microsoft.Quantum.Diagnostics.Contradiction</span></span>](xref:Microsoft.Quantum.Diagnostics.Contradiction)