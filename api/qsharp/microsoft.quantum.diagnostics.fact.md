---
uid: Microsoft.Quantum.Diagnostics.Fact
title: Fonction FACT
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: Fact
qsharp.summary: Declares that a classical condition is true.
ms.openlocfilehash: 8e86000f04c01040d420c2f682fc1b4ccf35cf39
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853318"
---
# <a name="fact-function"></a><span data-ttu-id="3f685-102">Fonction FACT</span><span class="sxs-lookup"><span data-stu-id="3f685-102">Fact function</span></span>

<span data-ttu-id="3f685-103">Espace de noms : [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="3f685-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="3f685-104">Package : [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="3f685-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="3f685-105">Déclare qu’une condition classique a la valeur true.</span><span class="sxs-lookup"><span data-stu-id="3f685-105">Declares that a classical condition is true.</span></span>

```qsharp
function Fact (actual : Bool, message : String) : Unit
```


## <a name="input"></a><span data-ttu-id="3f685-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="3f685-106">Input</span></span>

### <a name="actual--bool"></a><span data-ttu-id="3f685-107">réel : [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="3f685-107">actual : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="3f685-108">Condition à déclarer.</span><span class="sxs-lookup"><span data-stu-id="3f685-108">The condition to be declared.</span></span>


### <a name="message--string"></a><span data-ttu-id="3f685-109">message : [chaîne](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="3f685-109">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="3f685-110">Chaîne de message d’échec à imprimer dans le cas où la condition classique est false.</span><span class="sxs-lookup"><span data-stu-id="3f685-110">Failure message string to be printed in the case that the classical condition is false.</span></span>



## <a name="output--unit"></a><span data-ttu-id="3f685-111">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="3f685-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="example"></a><span data-ttu-id="3f685-112">Exemple</span><span class="sxs-lookup"><span data-stu-id="3f685-112">Example</span></span>

<span data-ttu-id="3f685-113">L’extrait de code Q # suivant échoue :</span><span class="sxs-lookup"><span data-stu-id="3f685-113">The following Q# snippet will fail:</span></span>

```qsharp
Fact(false, "Expected true.");
```

## <a name="see-also"></a><span data-ttu-id="3f685-114">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="3f685-114">See Also</span></span>

- [<span data-ttu-id="3f685-115">Microsoft. Quantum. Diagnostics. contradiction</span><span class="sxs-lookup"><span data-stu-id="3f685-115">Microsoft.Quantum.Diagnostics.Contradiction</span></span>](xref:Microsoft.Quantum.Diagnostics.Contradiction)