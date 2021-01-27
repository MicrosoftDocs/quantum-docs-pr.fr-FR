---
uid: Microsoft.Quantum.Diagnostics.EqualityFactB
title: EqualityFactB fonction)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: EqualityFactB
qsharp.summary: Asserts that a classical Bool variable has the expected value.
ms.openlocfilehash: cb1d4c471c528d2d3c08c92619fafd532a88c8f0
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98829204"
---
# <a name="equalityfactb-function"></a><span data-ttu-id="a4eea-102">EqualityFactB fonction)</span><span class="sxs-lookup"><span data-stu-id="a4eea-102">EqualityFactB function</span></span>

<span data-ttu-id="a4eea-103">Espace de noms : [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="a4eea-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="a4eea-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="a4eea-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="a4eea-105">Déclare qu’une variable booléenne classique a la valeur attendue.</span><span class="sxs-lookup"><span data-stu-id="a4eea-105">Asserts that a classical Bool variable has the expected value.</span></span>

```qsharp
function EqualityFactB (actual : Bool, expected : Bool, message : String) : Unit
```


## <a name="input"></a><span data-ttu-id="a4eea-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="a4eea-106">Input</span></span>

### <a name="actual--bool"></a><span data-ttu-id="a4eea-107">réel : [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="a4eea-107">actual : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="a4eea-108">Variable à vérifier.</span><span class="sxs-lookup"><span data-stu-id="a4eea-108">The variable to be checked.</span></span>


### <a name="expected--bool"></a><span data-ttu-id="a4eea-109">ATTENDU : [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="a4eea-109">expected : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="a4eea-110">Valeur attendue.</span><span class="sxs-lookup"><span data-stu-id="a4eea-110">The expected value.</span></span>


### <a name="message--string"></a><span data-ttu-id="a4eea-111">message : [chaîne](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="a4eea-111">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="a4eea-112">Chaîne de message d’échec à utiliser lorsque l’assertion est déclenchée.</span><span class="sxs-lookup"><span data-stu-id="a4eea-112">Failure message string to be used when the assertion is triggered.</span></span>



## <a name="output--unit"></a><span data-ttu-id="a4eea-113">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="a4eea-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

