---
uid: Microsoft.Quantum.Diagnostics.EqualityFactR
title: EqualityFactR fonction)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: EqualityFactR
qsharp.summary: Asserts that a classical Result variable has the expected value.
ms.openlocfilehash: 166dff211d6db9da5d39c607af1924ffd6d276dd
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96201765"
---
# <a name="equalityfactr-function"></a><span data-ttu-id="b1f49-102">EqualityFactR fonction)</span><span class="sxs-lookup"><span data-stu-id="b1f49-102">EqualityFactR function</span></span>

<span data-ttu-id="b1f49-103">Espace de noms : [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="b1f49-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="b1f49-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="b1f49-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="b1f49-105">Déclare qu’une variable de résultat classique a la valeur attendue.</span><span class="sxs-lookup"><span data-stu-id="b1f49-105">Asserts that a classical Result variable has the expected value.</span></span>

```qsharp
function EqualityFactR (actual : Result, expected : Result, message : String) : Unit
```


## <a name="input"></a><span data-ttu-id="b1f49-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="b1f49-106">Input</span></span>

### <a name="actual--__invalidresult__"></a><span data-ttu-id="b1f49-107">réel : __non <Result> valide__</span><span class="sxs-lookup"><span data-stu-id="b1f49-107">actual : __invalid<Result>__</span></span>

<span data-ttu-id="b1f49-108">Variable à vérifier.</span><span class="sxs-lookup"><span data-stu-id="b1f49-108">The variable to be checked.</span></span>


### <a name="expected--__invalidresult__"></a><span data-ttu-id="b1f49-109">ATTENDU : __non <Result> valide__</span><span class="sxs-lookup"><span data-stu-id="b1f49-109">expected : __invalid<Result>__</span></span>

<span data-ttu-id="b1f49-110">Valeur attendue.</span><span class="sxs-lookup"><span data-stu-id="b1f49-110">The expected value.</span></span>


### <a name="message--string"></a><span data-ttu-id="b1f49-111">message : [chaîne](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="b1f49-111">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="b1f49-112">Chaîne de message d’échec à utiliser lorsque l’assertion est déclenchée.</span><span class="sxs-lookup"><span data-stu-id="b1f49-112">Failure message string to be used when the assertion is triggered.</span></span>



## <a name="output--unit"></a><span data-ttu-id="b1f49-113">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="b1f49-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

