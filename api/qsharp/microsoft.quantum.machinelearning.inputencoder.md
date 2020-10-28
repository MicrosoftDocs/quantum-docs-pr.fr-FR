---
uid: Microsoft.Quantum.MachineLearning.InputEncoder
title: InputEncoder fonction)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: InputEncoder
qsharp.summary: Given a set of coefficients and a tolerance, returns a state preparation operation that prepares each coefficient as the corresponding amplitude of a computational basis state.
ms.openlocfilehash: 771cf01866498f4662864939e6946526c2b5827a
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92701374"
---
# <a name="inputencoder-function"></a><span data-ttu-id="46fcd-102">InputEncoder fonction)</span><span class="sxs-lookup"><span data-stu-id="46fcd-102">InputEncoder function</span></span>

<span data-ttu-id="46fcd-103">Espace de noms : [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="46fcd-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="46fcd-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="46fcd-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="46fcd-105">À partir d’un ensemble de coefficients et d’une tolérance, retourne une opération de préparation de l’État qui prépare chaque coefficient comme amplitude correspondante d’un état de base de calcul.</span><span class="sxs-lookup"><span data-stu-id="46fcd-105">Given a set of coefficients and a tolerance, returns a state preparation operation that prepares each coefficient as the corresponding amplitude of a computational basis state.</span></span>

```qsharp
function InputEncoder (coefficients : Double[]) : Microsoft.Quantum.MachineLearning.StateGenerator
```


## <a name="input"></a><span data-ttu-id="46fcd-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="46fcd-106">Input</span></span>

### <a name="coefficients--double"></a><span data-ttu-id="46fcd-107">coefficients : [double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="46fcd-107">coefficients : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="46fcd-108">Coefficients à encoder dans un état d’entrée.</span><span class="sxs-lookup"><span data-stu-id="46fcd-108">The coefficients to be encoded into an input state.</span></span>



## <a name="output--stategenerator"></a><span data-ttu-id="46fcd-109">Sortie : [StateGenerator](xref:Microsoft.Quantum.MachineLearning.StateGenerator)</span><span class="sxs-lookup"><span data-stu-id="46fcd-109">Output : [StateGenerator](xref:Microsoft.Quantum.MachineLearning.StateGenerator)</span></span>

<span data-ttu-id="46fcd-110">Opération de préparation de l’État qui prépare les coefficients donnés comme un état d’entrée sur un registre donné.</span><span class="sxs-lookup"><span data-stu-id="46fcd-110">A state preparation operation that prepares the given coefficients as an input state on a given register.</span></span>