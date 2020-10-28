---
uid: Microsoft.Quantum.MachineLearning.ApproximateInputEncoder
title: ApproximateInputEncoder fonction)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: ApproximateInputEncoder
qsharp.summary: Given a set of coefficients and a tolerance, returns a state preparation operation that prepares each coefficient as the corresponding amplitude of a computational basis state, up to the given tolerance.
ms.openlocfilehash: 67ef7a47a2e036f0953d946b4ace0e6673b173bd
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92706886"
---
# <a name="approximateinputencoder-function"></a><span data-ttu-id="1f42c-102">ApproximateInputEncoder fonction)</span><span class="sxs-lookup"><span data-stu-id="1f42c-102">ApproximateInputEncoder function</span></span>

<span data-ttu-id="1f42c-103">Espace de noms : [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="1f42c-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="1f42c-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="1f42c-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="1f42c-105">À partir d’un ensemble de coefficients et d’une tolérance, retourne une opération de préparation de l’État qui prépare chaque coefficient comme amplitude correspondante d’un état de base de calcul, jusqu’à la tolérance donnée.</span><span class="sxs-lookup"><span data-stu-id="1f42c-105">Given a set of coefficients and a tolerance, returns a state preparation operation that prepares each coefficient as the corresponding amplitude of a computational basis state, up to the given tolerance.</span></span>

```qsharp
function ApproximateInputEncoder (tolerance : Double, coefficients : Double[]) : Microsoft.Quantum.MachineLearning.StateGenerator
```


## <a name="input"></a><span data-ttu-id="1f42c-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="1f42c-106">Input</span></span>

### <a name="tolerance--double"></a><span data-ttu-id="1f42c-107">tolérance : [double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="1f42c-107">tolerance : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="1f42c-108">Tolérance approximative à utiliser pour encoder les coefficients donnés dans un état d’entrée.</span><span class="sxs-lookup"><span data-stu-id="1f42c-108">The approximation tolerance to be used in encoding the given coefficients into an input state.</span></span>


### <a name="coefficients--double"></a><span data-ttu-id="1f42c-109">coefficients : [double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="1f42c-109">coefficients : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="1f42c-110">Coefficients à encoder dans un état d’entrée.</span><span class="sxs-lookup"><span data-stu-id="1f42c-110">The coefficients to be encoded into an input state.</span></span>



## <a name="output--stategenerator"></a><span data-ttu-id="1f42c-111">Sortie : [StateGenerator](xref:Microsoft.Quantum.MachineLearning.StateGenerator)</span><span class="sxs-lookup"><span data-stu-id="1f42c-111">Output : [StateGenerator](xref:Microsoft.Quantum.MachineLearning.StateGenerator)</span></span>

<span data-ttu-id="1f42c-112">Opération de préparation de l’État qui prépare les coefficients donnés comme un état d’entrée sur un registre donné.</span><span class="sxs-lookup"><span data-stu-id="1f42c-112">A state preparation operation that prepares the given coefficients as an input state on a given register.</span></span>