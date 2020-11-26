---
uid: Microsoft.Quantum.Diagnostics.EqualityFactCP
title: EqualityFactCP fonction)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: EqualityFactCP
qsharp.summary: Asserts that a complex number has the expected value.
ms.openlocfilehash: 39b55e17302f9d2e5049169e9c1a74e53a8b1115
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96201850"
---
# <a name="equalityfactcp-function"></a><span data-ttu-id="886a3-102">EqualityFactCP fonction)</span><span class="sxs-lookup"><span data-stu-id="886a3-102">EqualityFactCP function</span></span>

<span data-ttu-id="886a3-103">Espace de noms : [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="886a3-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="886a3-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="886a3-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="886a3-105">Déclare qu’un nombre complexe a la valeur attendue.</span><span class="sxs-lookup"><span data-stu-id="886a3-105">Asserts that a complex number has the expected value.</span></span>

```qsharp
function EqualityFactCP (actual : Microsoft.Quantum.Math.ComplexPolar, expected : Microsoft.Quantum.Math.ComplexPolar, message : String) : Unit
```


## <a name="input"></a><span data-ttu-id="886a3-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="886a3-106">Input</span></span>

### <a name="actual--complexpolar"></a><span data-ttu-id="886a3-107">réel : [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span><span class="sxs-lookup"><span data-stu-id="886a3-107">actual : [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span></span>

<span data-ttu-id="886a3-108">Valeur à vérifier.</span><span class="sxs-lookup"><span data-stu-id="886a3-108">The value to be checked.</span></span>


### <a name="expected--complexpolar"></a><span data-ttu-id="886a3-109">ATTENDU : [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span><span class="sxs-lookup"><span data-stu-id="886a3-109">expected : [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span></span>

<span data-ttu-id="886a3-110">Valeur attendue.</span><span class="sxs-lookup"><span data-stu-id="886a3-110">The expected value.</span></span>


### <a name="message--string"></a><span data-ttu-id="886a3-111">message : [chaîne](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="886a3-111">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="886a3-112">Chaîne de message d’échec à utiliser lorsque l’assertion est déclenchée.</span><span class="sxs-lookup"><span data-stu-id="886a3-112">Failure message string to be used when the assertion is triggered.</span></span>



## <a name="output--unit"></a><span data-ttu-id="886a3-113">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="886a3-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

