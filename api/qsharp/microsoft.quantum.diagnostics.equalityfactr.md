---
uid: Microsoft.Quantum.Diagnostics.EqualityFactR
title: EqualityFactR fonction)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: EqualityFactR
qsharp.summary: Asserts that a classical Result variable has the expected value.
ms.openlocfilehash: 2b293dc581ed58f7e3864a952fb3ecafa68e759c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92702655"
---
# <a name="equalityfactr-function"></a><span data-ttu-id="02220-102">EqualityFactR fonction)</span><span class="sxs-lookup"><span data-stu-id="02220-102">EqualityFactR function</span></span>

<span data-ttu-id="02220-103">Espace de noms : [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="02220-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="02220-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="02220-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="02220-105">Déclare qu’une variable de résultat classique a la valeur attendue.</span><span class="sxs-lookup"><span data-stu-id="02220-105">Asserts that a classical Result variable has the expected value.</span></span>

```qsharp
function EqualityFactR (actual : Result, expected : Result, message : String) : Unit
```


## <a name="input"></a><span data-ttu-id="02220-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="02220-106">Input</span></span>

### <a name="actual--__invalidresult__"></a><span data-ttu-id="02220-107">réel : __non <Result> valide__</span><span class="sxs-lookup"><span data-stu-id="02220-107">actual : __invalid<Result>__</span></span>

<span data-ttu-id="02220-108">Variable à vérifier.</span><span class="sxs-lookup"><span data-stu-id="02220-108">The variable to be checked.</span></span>


### <a name="expected--__invalidresult__"></a><span data-ttu-id="02220-109">ATTENDU : __non <Result> valide__</span><span class="sxs-lookup"><span data-stu-id="02220-109">expected : __invalid<Result>__</span></span>

<span data-ttu-id="02220-110">Valeur attendue.</span><span class="sxs-lookup"><span data-stu-id="02220-110">The expected value.</span></span>


### <a name="message--string"></a><span data-ttu-id="02220-111">message : [chaîne](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="02220-111">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="02220-112">Chaîne de message d’échec à utiliser lorsque l’assertion est déclenchée.</span><span class="sxs-lookup"><span data-stu-id="02220-112">Failure message string to be used when the assertion is triggered.</span></span>



## <a name="output--unit"></a><span data-ttu-id="02220-113">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="02220-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>
