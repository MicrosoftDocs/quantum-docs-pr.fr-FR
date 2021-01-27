---
uid: Microsoft.Quantum.Diagnostics.EqualityFactL
title: EqualityFactL fonction)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: EqualityFactL
qsharp.summary: Asserts that a classical BigInt variable has the expected value.
ms.openlocfilehash: b7d37b5115c51596c1b3ed93c53a29e9f36b811d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98829142"
---
# <a name="equalityfactl-function"></a><span data-ttu-id="d22a0-102">EqualityFactL fonction)</span><span class="sxs-lookup"><span data-stu-id="d22a0-102">EqualityFactL function</span></span>

<span data-ttu-id="d22a0-103">Espace de noms : [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="d22a0-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="d22a0-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="d22a0-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="d22a0-105">Déclare qu’une variable BigInt classique a la valeur attendue.</span><span class="sxs-lookup"><span data-stu-id="d22a0-105">Asserts that a classical BigInt variable has the expected value.</span></span>

```qsharp
function EqualityFactL (actual : BigInt, expected : BigInt, message : String) : Unit
```


## <a name="input"></a><span data-ttu-id="d22a0-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="d22a0-106">Input</span></span>

### <a name="actual--bigint"></a><span data-ttu-id="d22a0-107">réel : [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="d22a0-107">actual : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="d22a0-108">Nombre à vérifier.</span><span class="sxs-lookup"><span data-stu-id="d22a0-108">The number to be checked.</span></span>


### <a name="expected--bigint"></a><span data-ttu-id="d22a0-109">ATTENDU : [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="d22a0-109">expected : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="d22a0-110">Valeur attendue.</span><span class="sxs-lookup"><span data-stu-id="d22a0-110">The expected value.</span></span>


### <a name="message--string"></a><span data-ttu-id="d22a0-111">message : [chaîne](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="d22a0-111">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="d22a0-112">Chaîne de message d’échec à utiliser lorsque l’assertion est déclenchée.</span><span class="sxs-lookup"><span data-stu-id="d22a0-112">Failure message string to be used when the assertion is triggered.</span></span>



## <a name="output--unit"></a><span data-ttu-id="d22a0-113">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="d22a0-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

