---
uid: Microsoft.Quantum.Diagnostics.FormattedFailure
title: FormattedFailure fonction)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: FormattedFailure
qsharp.summary: Internal function used to fail with meaningful error messages.
ms.openlocfilehash: 0d7fb01ddf23cd6d79f722c8f6b691afa74a8885
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92702628"
---
# <a name="formattedfailure-function"></a><span data-ttu-id="6442a-102">FormattedFailure fonction)</span><span class="sxs-lookup"><span data-stu-id="6442a-102">FormattedFailure function</span></span>

<span data-ttu-id="6442a-103">Espace de noms : [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="6442a-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="6442a-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="6442a-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="6442a-105">Fonction interne utilisée pour échouer avec des messages d’erreur significatifs.</span><span class="sxs-lookup"><span data-stu-id="6442a-105">Internal function used to fail with meaningful error messages.</span></span>

```qsharp
function FormattedFailure<'T> (actual : 'T, expected : 'T, message : String) : Unit
```


## <a name="input"></a><span data-ttu-id="6442a-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="6442a-106">Input</span></span>

### <a name="actual--t"></a><span data-ttu-id="6442a-107">réel : 't</span><span class="sxs-lookup"><span data-stu-id="6442a-107">actual : 'T</span></span>




### <a name="expected--t"></a><span data-ttu-id="6442a-108">ATTENDU : 't</span><span class="sxs-lookup"><span data-stu-id="6442a-108">expected : 'T</span></span>




### <a name="message--string"></a><span data-ttu-id="6442a-109">message : [chaîne](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="6442a-109">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>





## <a name="output--unit"></a><span data-ttu-id="6442a-110">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="6442a-110">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="6442a-111">Paramètres de type</span><span class="sxs-lookup"><span data-stu-id="6442a-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="6442a-112">Peut</span><span class="sxs-lookup"><span data-stu-id="6442a-112">'T</span></span>



## <a name="remarks"></a><span data-ttu-id="6442a-113">Notes</span><span class="sxs-lookup"><span data-stu-id="6442a-113">Remarks</span></span>

<span data-ttu-id="6442a-114">Cette fonction est destinée à être émulée par les runtimes de simulation, afin de permettre le transfert des contradictions mises en forme.</span><span class="sxs-lookup"><span data-stu-id="6442a-114">This function is intended to be emulated by simulation runtimes, so as to allow forwarding formatted contradictions.</span></span>