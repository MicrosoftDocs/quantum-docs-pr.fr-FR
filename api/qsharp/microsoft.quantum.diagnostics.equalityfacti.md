---
uid: Microsoft.Quantum.Diagnostics.EqualityFactI
title: EqualityFactI fonction)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: EqualityFactI
qsharp.summary: Asserts that a classical Int variable has the expected value.
ms.openlocfilehash: c41cb5548e8dfebb4d1c1a1c052306878c85e821
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853352"
---
# <a name="equalityfacti-function"></a><span data-ttu-id="cd69b-102">EqualityFactI fonction)</span><span class="sxs-lookup"><span data-stu-id="cd69b-102">EqualityFactI function</span></span>

<span data-ttu-id="cd69b-103">Espace de noms : [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="cd69b-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="cd69b-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="cd69b-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="cd69b-105">Déclare qu’une variable int classique a la valeur attendue.</span><span class="sxs-lookup"><span data-stu-id="cd69b-105">Asserts that a classical Int variable has the expected value.</span></span>

```qsharp
function EqualityFactI (actual : Int, expected : Int, message : String) : Unit
```


## <a name="input"></a><span data-ttu-id="cd69b-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="cd69b-106">Input</span></span>

### <a name="actual--int"></a><span data-ttu-id="cd69b-107">réel : [entier](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="cd69b-107">actual : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="cd69b-108">Nombre à vérifier.</span><span class="sxs-lookup"><span data-stu-id="cd69b-108">The number to be checked.</span></span>


### <a name="expected--int"></a><span data-ttu-id="cd69b-109">ATTENDU : [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="cd69b-109">expected : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="cd69b-110">Valeur attendue.</span><span class="sxs-lookup"><span data-stu-id="cd69b-110">The expected value.</span></span>


### <a name="message--string"></a><span data-ttu-id="cd69b-111">message : [chaîne](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="cd69b-111">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="cd69b-112">Chaîne de message d’échec à utiliser lorsque l’assertion est déclenchée.</span><span class="sxs-lookup"><span data-stu-id="cd69b-112">Failure message string to be used when the assertion is triggered.</span></span>



## <a name="output--unit"></a><span data-ttu-id="cd69b-113">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="cd69b-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

