---
uid: Microsoft.Quantum.Diagnostics.EqualityFactCP
title: EqualityFactCP fonction)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: EqualityFactCP
qsharp.summary: Asserts that a complex number has the expected value.
ms.openlocfilehash: 1ea790debb5a9123fb8bee3a5f8a1fde0a050b37
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92702667"
---
# <a name="equalityfactcp-function"></a><span data-ttu-id="47bab-102">EqualityFactCP fonction)</span><span class="sxs-lookup"><span data-stu-id="47bab-102">EqualityFactCP function</span></span>

<span data-ttu-id="47bab-103">Espace de noms : [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="47bab-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="47bab-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="47bab-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="47bab-105">Déclare qu’un nombre complexe a la valeur attendue.</span><span class="sxs-lookup"><span data-stu-id="47bab-105">Asserts that a complex number has the expected value.</span></span>

```qsharp
function EqualityFactCP (actual : Microsoft.Quantum.Math.ComplexPolar, expected : Microsoft.Quantum.Math.ComplexPolar, message : String) : Unit
```


## <a name="input"></a><span data-ttu-id="47bab-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="47bab-106">Input</span></span>

### <a name="actual--complexpolar"></a><span data-ttu-id="47bab-107">réel : [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span><span class="sxs-lookup"><span data-stu-id="47bab-107">actual : [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span></span>

<span data-ttu-id="47bab-108">Valeur à vérifier.</span><span class="sxs-lookup"><span data-stu-id="47bab-108">The value to be checked.</span></span>


### <a name="expected--complexpolar"></a><span data-ttu-id="47bab-109">ATTENDU : [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span><span class="sxs-lookup"><span data-stu-id="47bab-109">expected : [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span></span>

<span data-ttu-id="47bab-110">Valeur attendue.</span><span class="sxs-lookup"><span data-stu-id="47bab-110">The expected value.</span></span>


### <a name="message--string"></a><span data-ttu-id="47bab-111">message : [chaîne](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="47bab-111">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="47bab-112">Chaîne de message d’échec à utiliser lorsque l’assertion est déclenchée.</span><span class="sxs-lookup"><span data-stu-id="47bab-112">Failure message string to be used when the assertion is triggered.</span></span>



## <a name="output--unit"></a><span data-ttu-id="47bab-113">Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="47bab-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

