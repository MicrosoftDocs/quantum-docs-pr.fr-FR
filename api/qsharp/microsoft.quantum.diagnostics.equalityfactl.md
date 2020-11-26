---
uid: Microsoft.Quantum.Diagnostics.EqualityFactL
title: EqualityFactL fonction)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: EqualityFactL
qsharp.summary: Asserts that a classical BigInt variable has the expected value.
ms.openlocfilehash: 2aaabf39d6ce49952466a877685776490ef438ad
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96201799"
---
# <a name="equalityfactl-function"></a><span data-ttu-id="20554-102">EqualityFactL fonction)</span><span class="sxs-lookup"><span data-stu-id="20554-102">EqualityFactL function</span></span>

<span data-ttu-id="20554-103">Espace de noms : [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="20554-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="20554-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="20554-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="20554-105">Déclare qu’une variable BigInt classique a la valeur attendue.</span><span class="sxs-lookup"><span data-stu-id="20554-105">Asserts that a classical BigInt variable has the expected value.</span></span>

```qsharp
function EqualityFactL (actual : BigInt, expected : BigInt, message : String) : Unit
```


## <a name="input"></a><span data-ttu-id="20554-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="20554-106">Input</span></span>

### <a name="actual--bigint"></a><span data-ttu-id="20554-107">réel : [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="20554-107">actual : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="20554-108">Nombre à vérifier.</span><span class="sxs-lookup"><span data-stu-id="20554-108">The number to be checked.</span></span>


### <a name="expected--bigint"></a><span data-ttu-id="20554-109">ATTENDU : [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="20554-109">expected : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="20554-110">Valeur attendue.</span><span class="sxs-lookup"><span data-stu-id="20554-110">The expected value.</span></span>


### <a name="message--string"></a><span data-ttu-id="20554-111">message : [chaîne](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="20554-111">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="20554-112">Chaîne de message d’échec à utiliser lorsque l’assertion est déclenchée.</span><span class="sxs-lookup"><span data-stu-id="20554-112">Failure message string to be used when the assertion is triggered.</span></span>



## <a name="output--unit"></a><span data-ttu-id="20554-113">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="20554-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

