---
uid: Microsoft.Quantum.Diagnostics.EqualityFactB
title: EqualityFactB fonction)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: EqualityFactB
qsharp.summary: Asserts that a classical Bool variable has the expected value.
ms.openlocfilehash: d3163281772bda392fbdd61ad58543e22022a600
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92702670"
---
# <a name="equalityfactb-function"></a><span data-ttu-id="603c7-102">EqualityFactB fonction)</span><span class="sxs-lookup"><span data-stu-id="603c7-102">EqualityFactB function</span></span>

<span data-ttu-id="603c7-103">Espace de noms : [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="603c7-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="603c7-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="603c7-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="603c7-105">Déclare qu’une variable booléenne classique a la valeur attendue.</span><span class="sxs-lookup"><span data-stu-id="603c7-105">Asserts that a classical Bool variable has the expected value.</span></span>

```qsharp
function EqualityFactB (actual : Bool, expected : Bool, message : String) : Unit
```


## <a name="input"></a><span data-ttu-id="603c7-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="603c7-106">Input</span></span>

### <a name="actual--bool"></a><span data-ttu-id="603c7-107">réel : [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="603c7-107">actual : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="603c7-108">Variable à vérifier.</span><span class="sxs-lookup"><span data-stu-id="603c7-108">The variable to be checked.</span></span>


### <a name="expected--bool"></a><span data-ttu-id="603c7-109">ATTENDU : [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="603c7-109">expected : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="603c7-110">Valeur attendue.</span><span class="sxs-lookup"><span data-stu-id="603c7-110">The expected value.</span></span>


### <a name="message--string"></a><span data-ttu-id="603c7-111">message : [chaîne](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="603c7-111">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="603c7-112">Chaîne de message d’échec à utiliser lorsque l’assertion est déclenchée.</span><span class="sxs-lookup"><span data-stu-id="603c7-112">Failure message string to be used when the assertion is triggered.</span></span>



## <a name="output--unit"></a><span data-ttu-id="603c7-113">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="603c7-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

