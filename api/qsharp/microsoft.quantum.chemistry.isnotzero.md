---
uid: Microsoft.Quantum.Chemistry.IsNotZero
title: IsNotZero fonction)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry
qsharp.name: IsNotZero
qsharp.summary: Checks whether a `Double` number is not approximately zero.
ms.openlocfilehash: 3c0f9c6695e8c9ec4a0953d5217c28c512ac7de1
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92703549"
---
# <a name="isnotzero-function"></a><span data-ttu-id="82a07-102">IsNotZero fonction)</span><span class="sxs-lookup"><span data-stu-id="82a07-102">IsNotZero function</span></span>

<span data-ttu-id="82a07-103">Espace de noms : [Microsoft. Quantum. chimie](xref:Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="82a07-103">Namespace: [Microsoft.Quantum.Chemistry](xref:Microsoft.Quantum.Chemistry)</span></span>

<span data-ttu-id="82a07-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="82a07-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="82a07-105">Vérifie si un `Double` nombre n’est pas approximativement égal à zéro.</span><span class="sxs-lookup"><span data-stu-id="82a07-105">Checks whether a `Double` number is not approximately zero.</span></span>

```qsharp
function IsNotZero (number : Double) : Bool
```


## <a name="input"></a><span data-ttu-id="82a07-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="82a07-106">Input</span></span>

### <a name="number--double"></a><span data-ttu-id="82a07-107">nombre : [double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="82a07-107">number : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="82a07-108">Nombre à vérifier</span><span class="sxs-lookup"><span data-stu-id="82a07-108">Number to be checked</span></span>



## <a name="output--bool"></a><span data-ttu-id="82a07-109">Sortie : [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="82a07-109">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="82a07-110">Retourne la valeur true si `number` a une valeur absolue supérieure à `1e-15` .</span><span class="sxs-lookup"><span data-stu-id="82a07-110">Returns true if `number` has an absolute value greater than `1e-15`.</span></span>