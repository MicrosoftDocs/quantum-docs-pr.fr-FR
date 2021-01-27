---
uid: Microsoft.Quantum.Chemistry.IsNotZero
title: IsNotZero fonction)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry
qsharp.name: IsNotZero
qsharp.summary: Checks whether a `Double` number is not approximately zero.
ms.openlocfilehash: 9384e5dafd4b5b7d44cb348c9537ebc2c621466d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98839601"
---
# <a name="isnotzero-function"></a><span data-ttu-id="6b6f8-102">IsNotZero fonction)</span><span class="sxs-lookup"><span data-stu-id="6b6f8-102">IsNotZero function</span></span>

<span data-ttu-id="6b6f8-103">Espace de noms : [Microsoft. Quantum. chimie](xref:Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="6b6f8-103">Namespace: [Microsoft.Quantum.Chemistry](xref:Microsoft.Quantum.Chemistry)</span></span>

<span data-ttu-id="6b6f8-104">Package : [Microsoft. Quantum. chimie](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="6b6f8-104">Package: [Microsoft.Quantum.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span></span>


<span data-ttu-id="6b6f8-105">Vérifie si un `Double` nombre n’est pas approximativement égal à zéro.</span><span class="sxs-lookup"><span data-stu-id="6b6f8-105">Checks whether a `Double` number is not approximately zero.</span></span>

```qsharp
function IsNotZero (number : Double) : Bool
```


## <a name="input"></a><span data-ttu-id="6b6f8-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="6b6f8-106">Input</span></span>

### <a name="number--double"></a><span data-ttu-id="6b6f8-107">nombre : [double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="6b6f8-107">number : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="6b6f8-108">Nombre à vérifier</span><span class="sxs-lookup"><span data-stu-id="6b6f8-108">Number to be checked</span></span>



## <a name="output--bool"></a><span data-ttu-id="6b6f8-109">Sortie : [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="6b6f8-109">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="6b6f8-110">Retourne la valeur true si `number` a une valeur absolue supérieure à `1e-15` .</span><span class="sxs-lookup"><span data-stu-id="6b6f8-110">Returns true if `number` has an absolute value greater than `1e-15`.</span></span>