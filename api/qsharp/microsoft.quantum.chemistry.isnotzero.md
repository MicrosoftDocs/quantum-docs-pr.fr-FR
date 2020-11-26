---
uid: Microsoft.Quantum.Chemistry.IsNotZero
title: IsNotZero fonction)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry
qsharp.name: IsNotZero
qsharp.summary: Checks whether a `Double` number is not approximately zero.
ms.openlocfilehash: f80dbba6a51e62970e87c2782faba558340d2bd8
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96204060"
---
# <a name="isnotzero-function"></a><span data-ttu-id="5f1d2-102">IsNotZero fonction)</span><span class="sxs-lookup"><span data-stu-id="5f1d2-102">IsNotZero function</span></span>

<span data-ttu-id="5f1d2-103">Espace de noms : [Microsoft. Quantum. chimie](xref:Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="5f1d2-103">Namespace: [Microsoft.Quantum.Chemistry](xref:Microsoft.Quantum.Chemistry)</span></span>

<span data-ttu-id="5f1d2-104">Package : [Microsoft. Quantum. chimie](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="5f1d2-104">Package: [Microsoft.Quantum.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span></span>


<span data-ttu-id="5f1d2-105">Vérifie si un `Double` nombre n’est pas approximativement égal à zéro.</span><span class="sxs-lookup"><span data-stu-id="5f1d2-105">Checks whether a `Double` number is not approximately zero.</span></span>

```qsharp
function IsNotZero (number : Double) : Bool
```


## <a name="input"></a><span data-ttu-id="5f1d2-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="5f1d2-106">Input</span></span>

### <a name="number--double"></a><span data-ttu-id="5f1d2-107">nombre : [double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="5f1d2-107">number : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="5f1d2-108">Nombre à vérifier</span><span class="sxs-lookup"><span data-stu-id="5f1d2-108">Number to be checked</span></span>



## <a name="output--bool"></a><span data-ttu-id="5f1d2-109">Sortie : [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="5f1d2-109">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="5f1d2-110">Retourne la valeur true si `number` a une valeur absolue supérieure à `1e-15` .</span><span class="sxs-lookup"><span data-stu-id="5f1d2-110">Returns true if `number` has an absolute value greater than `1e-15`.</span></span>