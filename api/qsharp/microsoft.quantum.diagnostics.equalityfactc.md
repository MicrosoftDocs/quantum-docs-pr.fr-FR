---
uid: Microsoft.Quantum.Diagnostics.EqualityFactC
title: EqualityFactC fonction)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: EqualityFactC
qsharp.summary: Asserts that a complex number has the expected value.
ms.openlocfilehash: e33d25899580a127171fb45a92d77cfdb5003a21
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96201901"
---
# <a name="equalityfactc-function"></a><span data-ttu-id="ae616-102">EqualityFactC fonction)</span><span class="sxs-lookup"><span data-stu-id="ae616-102">EqualityFactC function</span></span>

<span data-ttu-id="ae616-103">Espace de noms : [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="ae616-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="ae616-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="ae616-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="ae616-105">Déclare qu’un nombre complexe a la valeur attendue.</span><span class="sxs-lookup"><span data-stu-id="ae616-105">Asserts that a complex number has the expected value.</span></span>

```qsharp
function EqualityFactC (actual : Microsoft.Quantum.Math.Complex, expected : Microsoft.Quantum.Math.Complex, message : String) : Unit
```


## <a name="input"></a><span data-ttu-id="ae616-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="ae616-106">Input</span></span>

### <a name="actual--complex"></a><span data-ttu-id="ae616-107">réel : [complexe](xref:Microsoft.Quantum.Math.Complex)</span><span class="sxs-lookup"><span data-stu-id="ae616-107">actual : [Complex](xref:Microsoft.Quantum.Math.Complex)</span></span>

<span data-ttu-id="ae616-108">Valeur à vérifier.</span><span class="sxs-lookup"><span data-stu-id="ae616-108">The value to be checked.</span></span>


### <a name="expected--complex"></a><span data-ttu-id="ae616-109">ATTENDU : [complexe](xref:Microsoft.Quantum.Math.Complex)</span><span class="sxs-lookup"><span data-stu-id="ae616-109">expected : [Complex](xref:Microsoft.Quantum.Math.Complex)</span></span>

<span data-ttu-id="ae616-110">Valeur attendue.</span><span class="sxs-lookup"><span data-stu-id="ae616-110">The expected value.</span></span>


### <a name="message--string"></a><span data-ttu-id="ae616-111">message : [chaîne](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="ae616-111">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="ae616-112">Chaîne de message d’échec à utiliser lorsque l’assertion est déclenchée.</span><span class="sxs-lookup"><span data-stu-id="ae616-112">Failure message string to be used when the assertion is triggered.</span></span>



## <a name="output--unit"></a><span data-ttu-id="ae616-113">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="ae616-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

