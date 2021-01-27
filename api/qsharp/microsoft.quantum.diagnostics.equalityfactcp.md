---
uid: Microsoft.Quantum.Diagnostics.EqualityFactCP
title: EqualityFactCP fonction)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: EqualityFactCP
qsharp.summary: Asserts that a complex number has the expected value.
ms.openlocfilehash: a207ba1c4d08ec58095f5db34ee32c7341002920
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98829170"
---
# <a name="equalityfactcp-function"></a><span data-ttu-id="71113-102">EqualityFactCP fonction)</span><span class="sxs-lookup"><span data-stu-id="71113-102">EqualityFactCP function</span></span>

<span data-ttu-id="71113-103">Espace de noms : [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="71113-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="71113-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="71113-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="71113-105">Déclare qu’un nombre complexe a la valeur attendue.</span><span class="sxs-lookup"><span data-stu-id="71113-105">Asserts that a complex number has the expected value.</span></span>

```qsharp
function EqualityFactCP (actual : Microsoft.Quantum.Math.ComplexPolar, expected : Microsoft.Quantum.Math.ComplexPolar, message : String) : Unit
```


## <a name="input"></a><span data-ttu-id="71113-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="71113-106">Input</span></span>

### <a name="actual--complexpolar"></a><span data-ttu-id="71113-107">réel : [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span><span class="sxs-lookup"><span data-stu-id="71113-107">actual : [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span></span>

<span data-ttu-id="71113-108">Valeur à vérifier.</span><span class="sxs-lookup"><span data-stu-id="71113-108">The value to be checked.</span></span>


### <a name="expected--complexpolar"></a><span data-ttu-id="71113-109">ATTENDU : [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span><span class="sxs-lookup"><span data-stu-id="71113-109">expected : [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span></span>

<span data-ttu-id="71113-110">Valeur attendue.</span><span class="sxs-lookup"><span data-stu-id="71113-110">The expected value.</span></span>


### <a name="message--string"></a><span data-ttu-id="71113-111">message : [chaîne](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="71113-111">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="71113-112">Chaîne de message d’échec à utiliser lorsque l’assertion est déclenchée.</span><span class="sxs-lookup"><span data-stu-id="71113-112">Failure message string to be used when the assertion is triggered.</span></span>



## <a name="output--unit"></a><span data-ttu-id="71113-113">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="71113-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

