---
uid: Microsoft.Quantum.Diagnostics.EqualityFactL
title: EqualityFactL fonction)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: EqualityFactL
qsharp.summary: Asserts that a classical BigInt variable has the expected value.
ms.openlocfilehash: 5e590af581be4e41df9d2081260409c454e3be4b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92702661"
---
# <a name="equalityfactl-function"></a><span data-ttu-id="cf1bf-102">EqualityFactL fonction)</span><span class="sxs-lookup"><span data-stu-id="cf1bf-102">EqualityFactL function</span></span>

<span data-ttu-id="cf1bf-103">Espace de noms : [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="cf1bf-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="cf1bf-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="cf1bf-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="cf1bf-105">Déclare qu’une variable BigInt classique a la valeur attendue.</span><span class="sxs-lookup"><span data-stu-id="cf1bf-105">Asserts that a classical BigInt variable has the expected value.</span></span>

```qsharp
function EqualityFactL (actual : BigInt, expected : BigInt, message : String) : Unit
```


## <a name="input"></a><span data-ttu-id="cf1bf-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="cf1bf-106">Input</span></span>

### <a name="actual--bigint"></a><span data-ttu-id="cf1bf-107">réel : [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="cf1bf-107">actual : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="cf1bf-108">Nombre à vérifier.</span><span class="sxs-lookup"><span data-stu-id="cf1bf-108">The number to be checked.</span></span>


### <a name="expected--bigint"></a><span data-ttu-id="cf1bf-109">ATTENDU : [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="cf1bf-109">expected : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="cf1bf-110">Valeur attendue.</span><span class="sxs-lookup"><span data-stu-id="cf1bf-110">The expected value.</span></span>


### <a name="message--string"></a><span data-ttu-id="cf1bf-111">message : [chaîne](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="cf1bf-111">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="cf1bf-112">Chaîne de message d’échec à utiliser lorsque l’assertion est déclenchée.</span><span class="sxs-lookup"><span data-stu-id="cf1bf-112">Failure message string to be used when the assertion is triggered.</span></span>



## <a name="output--unit"></a><span data-ttu-id="cf1bf-113">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="cf1bf-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

