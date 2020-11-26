---
uid: Microsoft.Quantum.Diagnostics.EqualityFactB
title: EqualityFactB fonction)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: EqualityFactB
qsharp.summary: Asserts that a classical Bool variable has the expected value.
ms.openlocfilehash: a87d6690e701eb1530be3134d24884a8c19357e9
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96201918"
---
# <a name="equalityfactb-function"></a><span data-ttu-id="2fb31-102">EqualityFactB fonction)</span><span class="sxs-lookup"><span data-stu-id="2fb31-102">EqualityFactB function</span></span>

<span data-ttu-id="2fb31-103">Espace de noms : [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="2fb31-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="2fb31-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="2fb31-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="2fb31-105">Déclare qu’une variable booléenne classique a la valeur attendue.</span><span class="sxs-lookup"><span data-stu-id="2fb31-105">Asserts that a classical Bool variable has the expected value.</span></span>

```qsharp
function EqualityFactB (actual : Bool, expected : Bool, message : String) : Unit
```


## <a name="input"></a><span data-ttu-id="2fb31-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="2fb31-106">Input</span></span>

### <a name="actual--bool"></a><span data-ttu-id="2fb31-107">réel : [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="2fb31-107">actual : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="2fb31-108">Variable à vérifier.</span><span class="sxs-lookup"><span data-stu-id="2fb31-108">The variable to be checked.</span></span>


### <a name="expected--bool"></a><span data-ttu-id="2fb31-109">ATTENDU : [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="2fb31-109">expected : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="2fb31-110">Valeur attendue.</span><span class="sxs-lookup"><span data-stu-id="2fb31-110">The expected value.</span></span>


### <a name="message--string"></a><span data-ttu-id="2fb31-111">message : [chaîne](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="2fb31-111">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="2fb31-112">Chaîne de message d’échec à utiliser lorsque l’assertion est déclenchée.</span><span class="sxs-lookup"><span data-stu-id="2fb31-112">Failure message string to be used when the assertion is triggered.</span></span>



## <a name="output--unit"></a><span data-ttu-id="2fb31-113">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="2fb31-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

