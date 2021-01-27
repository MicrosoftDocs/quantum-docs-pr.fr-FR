---
uid: Microsoft.Quantum.Diagnostics.FormattedFailure
title: FormattedFailure fonction)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: FormattedFailure
qsharp.summary: Internal function used to fail with meaningful error messages.
ms.openlocfilehash: 6b1202c8897d67e3089a88a0855c8008b3a8c2ba
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98828277"
---
# <a name="formattedfailure-function"></a><span data-ttu-id="e5798-102">FormattedFailure fonction)</span><span class="sxs-lookup"><span data-stu-id="e5798-102">FormattedFailure function</span></span>

<span data-ttu-id="e5798-103">Espace de noms : [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="e5798-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="e5798-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="e5798-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="e5798-105">Fonction interne utilisée pour échouer avec des messages d’erreur significatifs.</span><span class="sxs-lookup"><span data-stu-id="e5798-105">Internal function used to fail with meaningful error messages.</span></span>

```qsharp
function FormattedFailure<'T> (actual : 'T, expected : 'T, message : String) : Unit
```


## <a name="input"></a><span data-ttu-id="e5798-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="e5798-106">Input</span></span>

### <a name="actual--t"></a><span data-ttu-id="e5798-107">réel : 't</span><span class="sxs-lookup"><span data-stu-id="e5798-107">actual : 'T</span></span>




### <a name="expected--t"></a><span data-ttu-id="e5798-108">ATTENDU : 't</span><span class="sxs-lookup"><span data-stu-id="e5798-108">expected : 'T</span></span>




### <a name="message--string"></a><span data-ttu-id="e5798-109">message : [chaîne](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="e5798-109">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>





## <a name="output--unit"></a><span data-ttu-id="e5798-110">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="e5798-110">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="e5798-111">Paramètres de type</span><span class="sxs-lookup"><span data-stu-id="e5798-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="e5798-112">Peut</span><span class="sxs-lookup"><span data-stu-id="e5798-112">'T</span></span>



## <a name="remarks"></a><span data-ttu-id="e5798-113">Notes</span><span class="sxs-lookup"><span data-stu-id="e5798-113">Remarks</span></span>

<span data-ttu-id="e5798-114">Cette fonction est destinée à être émulée par les runtimes de simulation, afin de permettre le transfert des contradictions mises en forme.</span><span class="sxs-lookup"><span data-stu-id="e5798-114">This function is intended to be emulated by simulation runtimes, so as to allow forwarding formatted contradictions.</span></span>